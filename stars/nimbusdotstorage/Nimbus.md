---
project: Nimbus
stars: 808
description: An open source alternative to Google Drive, One Drive, iCloud, etc.
url: https://github.com/nimbusdotstorage/Nimbus
---

Nimbus cloud storage
====================

A better cloud

Quickstart
----------

### 1\. Clone the Repository

git clone https://github.com/logscore/Nimbus.git
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
2.  **Verify the database is running if running a detatched container**:
    
    docker compose ps
    
    You should see the `nimbus-db` container in the list with a status of "Up".
    
3.  **Connect to the database** (optional):
    
    # Using psql client inside the container
    docker compose exec postgres psql -U postgres -d nimbus
    

### 4\. Environment Setup

Copy the `.env.example` file to `.env` using this command, `cp .env.example .env` and fill in these values:

GOOGLE\_CLIENT\_ID=
GOOGLE\_CLIENT\_SECRET=

# To generate a secret, just run \`openssl rand -base64 32\`
BETTER\_AUTH\_SECRET=

### 5\. Run Database Migrations

After setting up the database, run the migrations:

bun db:migrate

### 6\. Start the Development Server

In a new terminal, start the development server:

> NOTE: this starts both the web and server development servers, to run just one, use `bun dev:web` or `bun dev:server`. Both will need the db running to work.

bun dev

The application should now be running at http://localhost:3000
