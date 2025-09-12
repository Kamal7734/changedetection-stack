# Project Overview

This project provides a self-hosted setup for `changedetection.io`, a powerful tool for monitoring website changes. It uses Docker to orchestrate the necessary services, including the main `changedetection.io` application, a browser for rendering pages, and a Cloudflare Tunnel for secure remote access.

## Key Technologies

*   **Docker & Docker Compose:** The entire stack is containerized, making it easy to deploy and manage.
*   **changedetection.io:** The core application for monitoring and detecting website content changes.
*   **sockpuppetbrowser:** A browser automation service that allows `changedetection.io` to render and interact with complex JavaScript-heavy websites.
*   **Cloudflare Tunnel:** Provides a secure way to expose the `changedetection.io` service to the internet without opening up firewall ports.

## Building and Running

To run this project, you will need to have Docker and Docker Compose installed.

1.  **Configuration:**
    *   Create a `.env` file by copying the `.env.example` file: `cp .env.example .env`
    *   Edit the `.env` file and provide the necessary values for `BASE_URL`, `TZ`, and `CLOUDFLARE_TUNNEL_TOKEN`.

2.  **Running the Stack:**
    *   Start the services in detached mode: `docker-compose up -d`

3.  **Stopping the Stack:**
    *   Stop the services: `docker-compose down`

## Development Conventions

*   All services are defined in the `docker-compose.yml` file.
*   Configuration is managed through environment variables in the `.env` file.
*   The `changedetection.io` data is persisted in a Docker volume named `changedetection-data`.
