
# DevOps Engineering Learning Journey

Welcome to my DevOps Engineering learning journey! This repository documents my hands-on practice, technical development and practical projects as I build skills in DevOps and backend engineering.

My goal is to develop practical experience in Linux administration, version control, containerisation, CI/CD automation, cloud computing and infrastructure management.

## Learning Objectives

- Linux administration and system management
- Git and GitHub version control
- Docker and containerisation
- CI/CD automation
- Cloud computing
- Infrastructure as Code (IaC)
- Monitoring and logging
- Automation and scripting

## Week 1 – Progress and Practical Experience

### Day 1 – Environment Setup
- Prepared the Linux development environment.
- Set up Git and GitHub.
- Created the `devops-labs` repository.

### Day 2 – Linux Fundamentals
- Practised essential Linux commands.
- Worked with files and directories.
- Practised navigating the Linux filesystem.
- Managed files using terminal commands.

### Day 3 – Linux System Administration
- Practised Linux system administration commands.
- Explored system information and process management.
- Worked with permissions and system services.

### Day 4 – Git and Linux Networking

**Git and GitHub**
- Created and switched between branches.
- Practised staging and committing changes.
- Merged branches.
- Resolved Git merge conflicts.
- Created a pull request and practised code review.

**Linux Networking**
- Inspected network interfaces and IP addresses.
- Examined routing information.
- Used `ss` to inspect listening ports and network connections.
- Investigated server connectivity.

### Day 5 – Docker Installation

- Installed Docker using Ubuntu's package manager.
- Enabled and started the Docker service.
- Verified the Docker installation.
- Downloaded and ran the official `hello-world` image.
- Confirmed successful container execution.

### Day 6 – NGINX Container Deployment

- Pulled the NGINX image from Docker Hub.
- Created and ran an NGINX container.
- Configured port mapping from host port `8080` to container port `80`.
- Accessed the NGINX welcome page through a browser.
- Tested the web server using `curl`.
- Practised viewing logs and inspecting containers.
- Accessed the container shell.
- Stopped and restarted the container.

## Technologies and Tools

| Technology | Practical Experience |
|---|---|
| Linux / Ubuntu | Command-line operations and system administration |
| Git | Branching, merging and conflict resolution |
| GitHub | Repository management and pull requests |
| Docker | Image management and container execution |
| NGINX | Containerised web server deployment |
| Bash | Linux command-line operations |

## Important Commands Practised

### Linux Networking

```bash
ip -br addr
ip route
sudo ss -tulnp
```

### Git

```bash
git status
git add .
git commit -m "Commit message"
git push
git branch
git switch
git merge
```

### Docker

```bash
docker --version
sudo systemctl enable docker
sudo systemctl start docker
sudo docker run hello-world
sudo docker ps
```

### NGINX Container

```bash
sudo docker run -d -p 8080:80 --name devops-nginx nginx
sudo docker logs devops-nginx
sudo docker inspect devops-nginx
sudo docker exec -it devops-nginx bash
sudo docker stop devops-nginx
sudo docker start devops-nginx
curl -I http://localhost:8080
```

## Repository Structure

```text
devops-labs/
│
├── linux-practice/
├── git-practice/
├── day4-notes.md
├── day5-docker.md
├── day6-nginx.md
└── README.md
```

## Practical Evidence

### NGINX Welcome Page
![NGINX Welcome Page](screenshots/nginx-welcome.png)

### Running Docker Container
![Docker Running](screenshots/docker-running.png)

### NGINX HTTP Response
![NGINX HTTP Response](screenshots/nginx-http-response.png)

## Future Learning Goals

- Build custom Docker images using Dockerfiles.
- Explore Docker Compose.
- Develop CI/CD pipelines.
- Learn cloud infrastructure fundamentals.
- Practise Infrastructure as Code.
- Implement monitoring and logging solutions.

---

**Learning by doing. Building practical skills. Growing towards DevOps Engineering.**
