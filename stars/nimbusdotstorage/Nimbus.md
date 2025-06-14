---
project: Nimbus
stars: 1167
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

### 3\. Set Up Postgres with Docker

We use Docker to run a PostgreSQL database for local development. Follow these steps to set it up:

1.  **Start the database**:
    
    bun db:up
    
    This will start a Postgres container with default credentials:
    
    -   Host: `localhost`
    -   Port: `5432`
    -   Database: `nimbus`
    -   Username: `postgres`
    -   Password: `postgres`
2.  **Verify the database is running if running a detached container**:
    
    docker compose ps
    
    You should see the `nimbus-db` container in the list with a status of "Up".
    
3.  **Connect to the database** (optional):
    
    # Using psql client inside the container
    docker compose exec postgres psql -U postgres -d nimbus
    

### 4\. Environment Setup

Copy the `.env.example` file to `.env` using this command, `cp .env.example .env` and fill in these values:

How to setup Google keys?  

-   Navigate to Google Cloud console.
    
-   Create a new project and navigate to its dashboard.
    
-   Under **API & Services**, navigate to **Oauth Consent Screen** and enter the details.
    
-   Now create a client. Add **Authorised Javascript origin** as `http://localhost:3000` and **Authorised redirect uri** as `http://localhost:1284/api/auth/callback/google` and get your `client_id` and `client_secret`.
    
-   Now navigate to **Audience** and add **Test users**.
    

GOOGLE\_CLIENT\_ID=
GOOGLE\_CLIENT\_SECRET=

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

bun db:migrate

### 6\. Start the Development Server

In a new terminal, start the development server:

> NOTE: this starts both the web and server development servers, to run just one, use `bun dev:web` or `bun dev:server`. Both will need the db running to work.

bun dev

The application should now be running at http://localhost:3000

### 7\. Access Authentication

Once the development server is running, you can access the authentication pages:

-   **Sign In**: Navigate to http://localhost:3000/signin
-   **Sign Up**: Navigate to http://localhost:3000/signup

Make sure you have configured the Google OAuth credentials in your `.env` file as described in step 4 for authentication to work properly. Additionally, configure your Resend API key for the forgot password functionality to work.

If you want to contribute, please refer to the contributing guide

Our Amazing Contributors
------------------------
