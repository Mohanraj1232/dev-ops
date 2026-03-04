# Single App Docker Project

A simple web application served with nginx in a Docker container.

## Prerequisites

- Docker Desktop installed and running on your system

## Project Structure

```
├── Dockerfile
├── index.html
└── README.md
```

## Building the Docker Image

To build the Docker image, run the following command in the project directory:

```bash
docker build -t single-app .
```

## Running the Container

After building the image, you can run the container with:

```bash
docker run -p 8080:80 single-app
```

## Accessing the Application

Once the container is running, open your web browser and navigate to:

```
http://localhost:8080
```

You should see the "Hello DevOps Class 🚀" page.

## Stopping the Container

To stop the running container:

1. Press `Ctrl + C` in the terminal where the container is running
2. Or use `docker ps` to find the container ID and then `docker stop <container-id>`

## Docker Commands Summary

| Command | Description |
|---------|-------------|
| `docker build -t single-app .` | Build the Docker image |
| `docker run -p 8080:80 single-app` | Run the container |
| `docker ps` | List running containers |
| `docker stop <container-id>` | Stop a specific container |
| `docker images` | List available images |