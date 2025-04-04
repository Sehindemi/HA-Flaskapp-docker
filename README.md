# HA Flask App with Docker

This project demonstrates the deployment of a Flask web application using Docker with high availability (HA) architecture. By leveraging Docker Compose and an NGINX reverse proxy, this setup ensures scalable and resilient infrastructure. The app is designed for easy deployment in any environment, providing a foundation for building containerised web applications.

## Overview

This repository contains a Flask application running behind an NGINX reverse proxy in a Docker container. The setup aims to demonstrate how to:

- Use Docker for containerising web applications
- Implement high availability with load balancing using NGINX
- Simplify deployment using Docker Compose

The architecture can be scaled by increasing the number of Flask app instances or NGINX replicas.

### Key Components:
- **Dockerfile**: Builds the Flask app image with Python and necessary dependencies.
- **docker-compose.yml**: Defines the configuration for Flask and NGINX containers.
- **nginx.conf**: Configures NGINX for reverse proxy and load balancing.
- **requirements.txt**: Lists all Python dependencies required for the Flask app.
- **app/**: Contains the core application code, including routes for handling HTTP requests.

## Steps to Build and Run

Follow these steps to build and deploy the app:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Sehindemi/HA-Flaskapp-docker.git
   cd HA-Flaskapp-docker/flask-app


2. **Build and start the containers: Use Docker Compose to build and run the containers:**
docker-compose up --build

3. Access the Flask app: Open a browser and go to http://localhost to see the running Flask application.
docker-compose up --scale flask-app=3

## Stages of Building the Application

- **Building Flask Image**: The `Dockerfile` defines the steps for creating the Flask image, including installing dependencies and setting up the app environment.

- **Setting Up NGINX Reverse Proxy**: The `nginx.conf` configures NGINX to route incoming traffic to the Flask containers. It ensures that requests are balanced across multiple Flask app instances.

- **Using Docker Compose for Multi-Container Setup**: The `docker-compose.yml` file sets up the Flask application and NGINX container. It also defines networking between the containers.

- **Running and Testing the App**: Once the containers are up, the Flask app is accessible at `http://localhost`, and you can test its functionality.

## How It Works

- **Flask App**: The Flask app runs inside a Docker container and listens on port 5000 by default.

- **NGINX**: NGINX acts as a reverse proxy and load balancer, directing incoming traffic to Flask instances, ensuring that multiple instances of Flask can handle requests simultaneously.

- **Docker Compose**: Docker Compose simplifies the orchestration of these services, allowing you to manage both the Flask and NGINX containers with a single command.
