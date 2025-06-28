---
project: Nimbus
stars: 1294
description: An open source alternative to Google Drive, One Drive, iCloud, etc.
url: https://github.com/nimbusdotstorage/Nimbus
---

Nimbus cloud storage
====================

A better cloud

Quickstart
----------

### 1\. Clone the Repository

git clone https://github.com/nimbusdotstorage/Nimbus.git
cd Nimbus

### 2\. Install Dependencies

bun i

### 3\. Set Up Postgres and Valkey with Docker

We use Docker to run a PostgreSQL database and Valkey for local development. Follow these steps to set it up:

1.  Copy .env.development.example to .env

cp .env.development.example .env

Copy .env to child directories

bun run env:sync

1.  **Start the database and valkey**:
    
    bun db:up
    bun cache:up
    
    This will start a Postgres container with default credentials:
    
    -   Host: `localhost`
    -   Port: `5432`
    -   Database: `nimbus`
    -   Username: `postgres`
    -   Password: `postgres`
    
    And a Valkey container with credentials:
    
    -   Host: `localhost`
    -   Port: `6379`
    -   Username: `valkey`
    -   Password: `valkey`
2.  **Verify the database and valkey is running if running a detached container**:
    
    docker ps
    
    You should see the `nimbus-db-local-compose` and `nimbus-cache-local-compose` containers in the list with a status of "Up".
    
3.  **Connect to the database** (optional):
    
    # Using psql client inside the container
    docker compose exec postgres psql -U postgres -d nimbus
    
4.  **Connect to the valkey** (optional):
    
    # Using valkey-cli inside the container
    docker compose exec valkey valkey-cli --user valkey --pass valkey
    

### 4\. Environment Setup

Follow the instructions on the first step of this guide.

How to setup Google keys?  

-   Navigate to Google Cloud console.
    
-   Create a new project and navigate to its dashboard.
    
-   Under **API & Services**, navigate to **Oauth Consent Screen** and enter the details.
    
-   Now create a client. Add **Authorised Javascript origin** as `http://localhost:3000` and **Authorised redirect uri** as `http://localhost:1284/api/auth/callback/google` and get your `client_id` and `client_secret`.
    
-   Now navigate to **Audience** and add **Test users**.
    

How to setup Microsoft keys?  

-   Go to the **Microsoft Azure Portal**.
    
-   Navigate to **Azure Active Directory** → **App registrations** → click **New registration**.
    
-   Enter a name for your app.
    
-   Under **Supported account types**, choose:  
    **Accounts in any organizational directory and personal Microsoft accounts**  
    (i.e. all Microsoft account users).
    
-   Under **Redirect URI**, select **Web** and enter:  
    `http://localhost:1284/api/auth/callback/microsoft`  
    (Also add `http://localhost:3000` under front-end origins if needed.)
    
-   After registration, go to the app's **Overview** to copy your **Application (client) ID**.
    
-   Then go to **Certificates & secrets** → **New client secret** → add a description and expiry → click **Add** → copy the generated secret value.
    
-   Now, go to **API permissions** and make sure these **delegated Microsoft Graph** permissions are added and granted:
    
    -   `email` – View users' email address
    -   `offline_access` – Maintain access to data you have given it access to
    -   `openid` – Sign users in
    -   `profile` – View users' basic profile
    -   `User.Read` – Sign in and read user profile
    -   `Files.ReadWrite` – Have full access to user files (OneDrive access)
-   Click **Grant admin consent** to apply the permissions.
    

GOOGLE\_CLIENT\_ID=
GOOGLE\_CLIENT\_SECRET=

MICROSOFT\_CLIENT\_ID=
MICROSOFT\_CLIENT\_SECRET=

# To generate a secret, just run \`openssl rand -base64 32\`
BETTER\_AUTH\_SECRET=

How to get a Resend API Key?  

1.  Go to Resend.com and sign up or log in to your account.
    
2.  From the dashboard, click on **"API Keys"** in the sidebar.
    
3.  Click the **"Create API Key"** button.
    
4.  Enter a name for your key (e.g., `nimbus-dev`) and confirm.
    
5.  Copy the generated API key.
    
6.  Add it to your `.env` file:
    

RESEND\_API\_KEY=your-api-key-here

### 5\. Run Database Migrations

After setting up the database, run the migrations:

bun db:push

### 6\. Enable Google Drive API

To ensure the application works correctly and can fetch data from Google Drive, you must enable the Google Drive API in the same Google Cloud project where your OAuth credentials are configured.

Steps To Enable Drive API  

1.  Go to the Google Cloud Console.
2.  Select the project you're using for OAuth.
3.  Navigate to **APIs & Services > Library**.
4.  Search for **Google Drive API** or Click Here.
5.  Click **Enable**.

> Note: This step is **required** for the application to access Google Drive data via OAuth.

### 7\. Start the Development Server

In a new terminal, start the development server:

> NOTE: this starts both the web and server development servers, to run just one, use `bun dev:web` or `bun dev:server`. Both will need the db running to work.

bun dev

The application should now be running at http://localhost:3000

### 8\. Access Authentication

Once the development server is running, you can access the authentication pages:

-   **Sign In**: Navigate to http://localhost:3000/signin
-   **Sign Up**: Navigate to http://localhost:3000/signup

Make sure you have configured the Google OAuth credentials in your `.env` file as described in step 4 for authentication to work properly. Additionally, configure your Resend API key for the forgot password functionality to work.

If you want to contribute, please refer to the contributing guide

Deploying Docker images (ex. Fly.io)
------------------------------------

Follow the DEPLOYMENT.md file for instructions on how to deploy to Fly.

Our Amazing Contributors
------------------------
