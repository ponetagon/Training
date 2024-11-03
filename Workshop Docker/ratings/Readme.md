# Ratings Service

This is the **Ratings Service**, a microservice that provides rating information for books or other products.

## Prerequisites

- Docker installed on your system

## Building the Docker Image

To build the Docker image for the ratings service, use the following command:

```bash
docker build -t ratings:v1 .

```
## Run the Docker container

To run the Docker image for the ratings service, use the following command:

```bash
docker run -d --name ratings -p 8080:9080 ratings:v1
```