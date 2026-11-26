
# Day 5 – Docker Installation and First Container

## Objective
Install Docker, configure the Docker service and run the first container.

## 1. Install Docker

Installed Docker using Ubuntu's package manager:

```bash
sudo apt install docker.io
```

Verified the installation:

```bash
docker --version
```

## 2. Enable and Start Docker

Enabled Docker to start automatically at boot:

```bash
sudo systemctl enable docker
```

Started the Docker service:

```bash
sudo systemctl start docker
```

Verified its status:

```bash
sudo systemctl status docker
```

Confirmed that Docker was active and running.

## 3. Run the First Container

Executed the official Docker test image:

```bash
sudo docker run hello-world
```

Docker successfully:
- Contacted the Docker daemon.
- Downloaded the `hello-world` image from Docker Hub.
- Created and ran a container.
- Displayed the "Hello from Docker!" confirmation message.

## Key Concepts Learned

- **Docker:** A platform for building and running applications in containers.
- **Image:** A packaged template used to create containers.
- **Container:** A running instance of an image.
- **Docker daemon:** The background service that manages Docker objects.
- **Docker Hub:** A registry for storing and downloading container images.

## Commands Practised

```bash
docker --version
sudo apt install docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo systemctl status docker
sudo docker run hello-world
```

## Outcome

Successfully installed Docker, configured its service and ran the first container.
