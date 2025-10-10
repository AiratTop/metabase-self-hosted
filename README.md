# Metabase Self-Hosted with Docker

![metabase](https://repository-images.githubusercontent.com/1071483828/2e3ee35d-850f-4443-a0cb-4d0ea6e07852)

This repository provides a `docker-compose` setup to run a self-hosted [Metabase](https://www.metabase.com/) instance with a [PostgreSQL](https://www.postgresql.org/) database as its application backend.

It's configured to connect to a shared Docker network, making it easy to integrate with other services.

## Features

- Uses the official Metabase and PostgreSQL Docker images.
- The Metabase application database is persisted in a local volume.
- Pre-configured for a shared network for easy inter-service communication.
- Includes scripts for easy management (`restart-docker.sh`, `update-docker.sh`).
- Includes a `backup.sh` script for backing up the PostgreSQL application database.

## Getting Started

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AiratTop/metabase-self-hosted.git
    cd metabase-self-hosted
    ```

2.  **Create the shared network:**
    If you haven't already, create the shared Docker network. This allows Metabase to communicate with other services.
    ```bash
    docker network create shared_network
    ```

3.  **Configure environment variables:**
    Update a `.env` file and specify your PostgreSQL database credentials.


4.  **Start the services:**
    ```bash
    docker compose up -d
    ```

5.  **Access Metabase:**
    Once the containers are running, you can access the Metabase setup wizard in your browser at [http://localhost:3000](http://localhost:3000).

## Usage

The repository includes several scripts to simplify management:

-   **Start:** `docker compose up -d`
-   **Restart:** `./restart-docker.sh`
-   **Update:** `./update-docker.sh` (Pulls the latest Docker images and restarts the services)
-   **Backup:** `./backup.sh` (Creates a compressed backup of the PostgreSQL database in the `backups` directory)

## See Also

Check out other self-hosted solutions:

-   [**postgresql-self-hosted**](https://github.com/AiratTop/postgresql-self-hosted): A simple and robust PostgreSQL setup.
-   [**mysql-self-hosted**](https://github.com/AiratTop/mysql-self-hosted): A self-hosted MySQL instance.
-   [**clickhouse-self-hosted**](https://github.com/AiratTop/clickhouse-self-hosted): High-performance columnar database for analytics.
-   [**metabase-self-hosted**](https://github.com/AiratTop/metabase-self-hosted): Self-hosted Metabase on Docker for business intelligence and analytics.
-   [**qdrant-self-hosted**](https://github.com/AiratTop/qdrant-self-hosted): A vector database for AI applications.
-   [**redis-self-hosted**](https://github.com/AiratTop/redis-self-hosted): A fast in-memory data store, often used as a cache or message broker.
-   [**caddy-self-hosted**](https://github.com/AiratTop/caddy-self-hosted): A modern, easy-to-use web server with automatic HTTPS.
-   [**wordpress-self-hosted**](https://github.com/AiratTop/wordpress-self-hosted): Production-ready WordPress stack with MySQL, phpMyAdmin, and WP-CLI.
-   [**n8n-self-hosted**](https://github.com/AiratTop/n8n-self-hosted): Scalable n8n with workers, Caddy for auto-HTTPS, and backup scripts.
-   [**monitoring-self-hosted**](https://github.com/AiratTop/monitoring-self-hosted): Self-hosted monitoring stack with Prometheus and Grafana.
-   [**ollama-self-hosted**](https://github.com/AiratTop/ollama-self-hosted): Ready-to-use solution for running Ollama with the Open WebUI on Docker.
-   [**authentik-self-hosted**](https://github.com/AiratTop/authentik-self-hosted): Authentik is a flexible, open-source Identity & Access Management (IAM) solution.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**Airat Halitov**

- Website: [airat.top](https://airat.top)
- GitHub: [@AiratTop](https://github.com/AiratTop)
- Email: [mail@airat.top](mailto:mail@airat.top)
- Repository: [metabase-self-hosted](https://github.com/AiratTop/metabase-self-hosted)
