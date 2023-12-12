# PostgreSQL and Adminer

## Overview

This project provides a Docker Compose configuration file to set up a containerized environment with PostgreSQL and Adminer. PostgreSQL is a powerful open-source relational database management system, while Adminer is a lightweight and user-friendly database management tool. With this setup, you can easily run and manage PostgreSQL databases using Adminer in a containerized environment.

## Prerequisites

Before you begin, make sure you have the following installed on your system:

* Docker: https://www.docker.com/get-started
* Docker Compose: https://docs.docker.com/compose/install/

## Usage

1. Clone or download this repository to your local machine.
2. Open a terminal and navigate to the project directory containing the `docker-compose.yml` file.
3. Customize environment variables (optional):
    * You can modify environment variables in the `docker-compose.yml` file to suit your needs. The following variables are available:
      * `POSTGRES_PORT`: PostgreSQL port (default: 5432)
      * `POSTGRES_PASSWORD`: PostgreSQL password (default: postgres)
      * `ADMINER_PORT`: Adminer port (default: 8008)
4. Start the containerized environment by running the following command:
    ```
    docker-compose up -d
    ```
    The -d flag is used to run the containers in the background.
5. Once the containers are up and running, you can access Adminer by opening a web browser and navigating to `http://localhost:${ADMINER_PORT}` (e.g., **http://localhost:8008** if ADMINER_PORT is not customized). Use the following credentials to log in:
    * **Server**: postgres
    * **Username**: postgres
    * **Password**: (Use the POSTGRES_PASSWORD defined in the docker-compose.yml file)
6. You can now use Adminer to manage your PostgreSQL databases.
7. When you're done, you can stop and remove the containers by running:
   ```
   docker-compose down
   ```

## Persistence

The PostgreSQL data is persisted in the ./data directory on your host machine. This ensures that your data remains intact even after stopping or removing containers.

## Important Notes

* Make sure to secure your PostgreSQL database by changing the default password (POSTGRES_PASSWORD) in a production environment.
* Ensure that the necessary ports (e.g., ${POSTGRES_PORT} and ${ADMINER_PORT}) are not in use by other services on your system.