# Week 2 - Day 1: Building and Containerizing a Node.js Application

## Objective

Build a simple Node.js web application, package it into a Docker image, and run it inside a Docker container.

## 1. Environment Setup

Verified the development environment:

- Ubuntu on WSL2
- Node.js 18.19.1
- npm 9.2.0
- Docker 29.1.3

## 2. Created the Node.js Application

Created a project named `week2-containerized-app`.

Project structure:

```text
week2-containerized-app/
├── Dockerfile
├── package.json
└── server.js
```

### server.js

Implemented a basic HTTP server using Node.js.

The application:
- Listens on port 3000.
- Returns an HTML response.
- Displays a welcome message.
- Confirms that the application was built with Node.js and Docker.

### package.json

Configured the application with an npm start script:

```json
"scripts": {
  "start": "node server.js"
}
```

Tested the application locally using:

```bash
npm start
curl http://localhost:3000
```

Confirmed that the application returned the expected HTML response.

## 3. Created a Dockerfile

Created a Dockerfile to define how the application should be packaged.

```dockerfile
FROM node:18

WORKDIR /app

COPY package*.json ./

COPY server.js ./

EXPOSE 3000

CMD ["npm", "start"]
```

### Dockerfile concepts learned

- `FROM`: Selects the base image.
- `WORKDIR`: Sets the working directory inside the container.
- `COPY`: Copies application files into the image.
- `EXPOSE`: Documents the application's listening port.
- `CMD`: Defines the default command executed when the container starts.

## 4. Built a Custom Docker Image

Built the application image using:

```bash
sudo docker build -t week2-node-app:v1 .
```

Successfully created:

- Image name: `week2-node-app`
- Image tag: `v1`

Verified the image using:

```bash
sudo docker images
```

## 5. Ran the Docker Container

Started the application inside a Docker container:

```bash
sudo docker run -d -p 3000:3000 \
  --name week2-node-container \
  week2-node-app:v1
```

### Docker concepts learned

- `docker build`: Builds an image from a Dockerfile.
- `-t`: Assigns a name and tag to an image.
- `docker run`: Creates and starts a container.
- `-d`: Runs a container in the background.
- `-p`: Maps a host port to a container port.
- `--name`: Assigns a custom container name.

## 6. Verified the Deployment

Checked running containers:

```bash
sudo docker ps
```

Confirmed:

- Container: `week2-node-container`
- Image: `week2-node-app:v1`
- Status: Up
- Port mapping: `3000:3000`

Tested the deployed application:

```bash
curl http://localhost:3000
```

Successfully received the application's HTML response.

The application was accessible at:

http://localhost:3000

## 7. Skills Practised

- Node.js application development
- npm project configuration
- Dockerfile creation
- Docker image building
- Docker container deployment
- Port mapping
- Application testing
- Linux command-line operations

## Outcome

Successfully developed and containerized my first Node.js web application.

The application was packaged into a custom Docker image and deployed inside a running container.

This practical exercise introduced the process of packaging applications into portable environments using Docker.

## Next Steps

Continue learning Docker by exploring:

- Container inspection and management
- Docker logs
- Docker networking
- Docker Compose
- Multi-service application deployment
