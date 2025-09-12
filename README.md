# Change Detection Stack

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project provides a Docker-based stack for running [changedetection.io](https://github.com/dgtlmoon/changedetection.io), a powerful open-source tool for monitoring and detecting changes in websites.

The stack is pre-configured with the following services:

- **changedetection.io**: The main web application for change detection.
- **browser-sockpuppet-chrome**: A headless Chrome browser for rendering web pages, enabling advanced change detection features.
- **cloudflared**: A service for exposing the `changedetection.io` application to the internet using [Cloudflare Tunnel](https://www.cloudflare.com/products/tunnel/).

This setup is based on the official `docker-compose.yml` template from the [changedetection.io repository](https://github.com/dgtlmoon/changedetection.io/blob/master/docker-compose.yml).

## Features

- **Easy Deployment**: Get a full change detection stack running with a single command.
- **Persistent Storage**: Your `changedetection.io` data is stored in a Docker volume, ensuring it persists across container restarts.
- **Secure Remote Access**: Expose your `changedetection.io` instance to the internet securely with Cloudflare Tunnel.
- **Scalable**: The stack is designed to be scalable, allowing you to monitor a large number of websites.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/changedetection-stack.git
    cd changedetection-stack
    ```

2.  **Create a `.env` file:**

    Copy the `.env.example` file to `.env`:

    ```bash
    cp .env.example .env
    ```

3.  **Configure the environment variables in `.env`:**

    - `TZ`: Your timezone (e.g., `America/New_York`).
    - `CLOUDFLARE_TUNNEL_TOKEN`: Your Cloudflare Tunnel token.

4.  **Start the services:**

    ```bash
    docker-compose up -d
    ```

    This command will start all the services in the background.

5.  **Access changedetection.io:**

    Once the services are running, you can access the `changedetection.io` web interface through the URL provided by your Cloudflare Tunnel.

## Configuration

The primary configuration is managed through environment variables in the `.env` file. See the "Getting Started" section for details.

You can customize the `docker-compose.yml` file for advanced settings, such as:

- **`browser-sockpuppet-chrome`**:
  - `SCREEN_WIDTH`, `SCREEN_HEIGHT`, `SCREEN_DEPTH`: The screen resolution for the headless browser.
  - `MAX_CONCURRENT_CHROME_PROCESSES`: The maximum number of concurrent Chrome processes.

## Volumes

- `changedetection-data`: A Docker volume for persisting the `changedetection.io` data.

## Networking

- `changedetection-net`: A Docker network for communication between the services.

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) file for details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
