# Full Observability Stack (Prometheus, Grafana, Loki) with Docker Compose

This project demonstrates a complete, production-grade **observability stack** using industry-standard open-source tools. It launches a sample web application alongside services for collecting metrics, logs, and traces, providing deep insight into application performance and health.

## Architecture

This entire stack is orchestrated with a single `docker-compose.yml` file:

-   **Sample Application**: A simple web server (`yeasy/simple-web`) that automatically exposes a `/metrics` endpoint for Prometheus.
-   **Prometheus**: Scrapes and stores time-series metrics from the sample application.
-   **Loki**: Aggregates logs from all containers. It's designed to be highly efficient and integrates perfectly with Prometheus.
-   **Grafana**: The unified visualization layer. It comes pre-configured with Prometheus and Loki as data sources, allowing you to build dashboards that correlate metrics (like an error spike) with the corresponding logs in one click.

## How to Run This Project

**Prerequisites**: You must have [Docker](https://www.docker.com/products/docker-desktop/) installed.

1.  Clone this repository.
2.  Navigate to the root directory and run:
    ```bash
    docker-compose up -d
    ```
3.  The stack is now live!
    -   **Grafana Dashboard**: `http://localhost:3000` (login: `admin`/`admin`)
    -   **Prometheus UI**: `http://localhost:9090`
    -   **Sample Application**: `http://localhost:8080`

Once in Grafana, you can explore metrics from Prometheus and logs from Loki using the "Explore" tab.
