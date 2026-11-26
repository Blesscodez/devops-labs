
# Day 6 – Deploying and Managing an NGINX Container

## Objective

Deploy an NGINX web server inside a Docker container, access it through a browser and practise basic container management.

## 1. Deploy NGINX

Created and started an NGINX container:

```bash
sudo docker run -d -p 8080:80 --name devops-nginx nginx
```

### Understanding the command

- `docker run`: Creates and starts a container.
- `-d`: Runs the container in detached mode.
- `-p 8080:80`: Maps host port 8080 to container port 80.
- `--name devops-nginx`: Assigns a name to the container.
- `nginx`: Specifies the image.

## 2. Verify the Container

Checked running containers:

```bash
sudo docker ps
```

Confirmed that NGINX was running and port 8080 was mapped to container port 80.

## 3. Access the Web Server

Opened the following address in a browser:

http://localhost:8080

The default NGINX welcome page loaded successfully.

Also tested the server using:

```bash
curl -I http://localhost:8080
```

Received an HTTP `200 OK` response, confirming that the web server was responding successfully.

## 4. View Container Logs

Displayed container logs:

```bash
sudo docker logs devops-nginx
```

Followed logs in real time:

```bash
sudo docker logs -f devops-nginx
```

Exited live log viewing using `Ctrl + C`.

## 5. Inspect the Container

Inspected container configuration and runtime information:

```bash
sudo docker inspect devops-nginx
```

Checked its status:

```bash
sudo docker inspect -f '{{.State.Status}}' devops-nginx
```

The container status was `running`.

## 6. Access the Container Shell

Opened an interactive Bash shell:

```bash
sudo docker exec -it devops-nginx bash
```

Inspected the default NGINX web directory:

```bash
ls
ls /usr/share/nginx/html
```

Found the default website files:

- `index.html`
- `50x.html`

Exited the container shell:

```bash
exit
```

## 7. Stop and Restart the Container

Stopped the container:

```bash
sudo docker stop devops-nginx
```

Checked all containers, including stopped ones:

```bash
sudo docker ps -a
```

Restarted the container:

```bash
sudo docker start devops-nginx
```

Verified that it was running again:

```bash
sudo docker ps
```

## Key Concepts Learned

- Running containers in detached mode.
- Publishing container ports to the host.
- Accessing a containerised web server.
- Checking HTTP responses using `curl`.
- Viewing and following container logs.
- Inspecting container configuration and status.
- Executing commands inside running containers.
- Stopping and restarting containers.

## Outcome

Successfully deployed an NGINX web server using Docker, accessed it through a browser and practised essential container management commands.
