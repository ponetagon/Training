## Prerequisites

Before starting the workshop, make sure you have:
- **Docker** installed on your system. [Download Docker](https://www.docker.com/get-started)
- Basic knowledge of the command line.
- A text editor (e.g., Visual Studio Code, Sublime Text).

## Workshop Agenda

 **Basic Docker Commands**
   - Pulling an image: `docker pull`
   - Running a container: `docker run`
   - Listing running containers: `docker ps`
   - Stopping and removing containers: `docker stop` and `docker rm`

 **Building Docker Images**
   - Writing a `Dockerfile`
   - Building an image: `docker build -t myapp:v1 .`
   - Inspecting images: `docker images`

 **Working with Volumes**
   - Mounting volumes: `docker run -v /host/path:/container/path`
   - Understanding volume persistence.

 **Docker Compose**
   - Introduction to `docker-compose.yml`
   - Running multi-container applications: `docker-compose up`
   - Stopping and removing services: `docker-compose down`

 **Hands-On Projects**
   - Build and run a simple web server in a container.
   - Deploy a multi-service application (e.g., a web app with a database).

## Example Commands

### Build and Run a Simple Container

```bash
docker build -t myapp:v1 .
docker run -d --name myapp -p 8080:80 myapp:v1
