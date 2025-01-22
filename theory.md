# What is Docker?

Docker is a platform for developing, shipping, and running applications in isolated environments known as containers. It provides a consistent runtime environment that ensures the application runs the same regardless of where it's deployed, whether it's on a developer’s machine, a test environment, or in production.

## Key Concepts

### Container
- A lightweight, standalone, and executable software package that includes everything needed to run an application (code, runtime, libraries, environment variables, and configuration files).
- Containers are isolated from each other, allowing multiple containers to run on the same host without interfering with each other.

### Docker Image
- A read-only template used to create containers. Images are built from a set of instructions defined in a Dockerfile. Once built, an image can be used to create containers.

### Docker Engine
- The core part of Docker, which is responsible for running and managing containers. It includes the Docker daemon (`dockerd`), which listens for requests from Docker CLI or REST API and manages containers.

### Dockerfile
- A text file that contains a series of instructions used to create a Docker image. It defines the operating system, the software required, and the steps needed to configure the environment inside the container.

### Docker Compose
- A tool for defining and running multi-container Docker applications. It uses a `docker-compose.yml` file where you can define services, networks, and volumes for your app.

### Docker Hub
- A cloud-based registry service where you can find and store Docker images. Docker Hub has official images for popular applications, databases, and languages, making it easy to pull pre-built images for use.

### Volumes
- A mechanism for persisting data outside of a container. Volumes allow data to persist even after a container stops or is removed.

## Common Commands

- `docker --version`: Check Docker version.
- `docker build -t <image-name> .`: Build a Docker image from a Dockerfile.
- `docker run -d -p 8080:80 <image-name>`: Run a container from an image.
- `docker ps`: List all running containers.
- `docker ps -a`: List all containers (including stopped ones).
- `docker stop <container-id>`: Stop a running container.
- `docker start <container-id>`: Start a stopped container.
- `docker exec -it <container-id> /bin/bash`: Access a running container's shell.
- `docker rm <container-id>`: Remove a container.
- `docker rmi <image-name>`: Remove an image.

## Docker Networking

- **Bridge network (default)**: Allows containers on the same host to communicate with each other.
- **Host network**: Binds containers directly to the host's network interface.
- **Overlay network**: Used for multi-host networking, allowing containers on different hosts to communicate.

## Advantages of Docker

- **Portability**: Docker ensures that the application behaves the same across different environments (development, testing, production).
- **Isolation**: Containers are isolated from each other, which helps prevent conflicts between different application dependencies.
- **Consistency**: Containers ensure that the environment remains consistent across all stages of the development cycle.
- **Scalability**: Docker makes it easy to scale applications, whether by increasing the number of containers or using orchestration tools like Kubernetes.
- **Efficiency**: Docker uses fewer resources than traditional virtual machines (VMs) because containers share the host OS's kernel.

## Use Cases

- **Microservices Architecture**: Docker is a great choice for deploying microservices since each service can be isolated in its own container.
- **Continuous Integration/Continuous Deployment (CI/CD)**: Docker allows developers to create reproducible environments for testing and deploying applications.
- **Cloud-native Applications**: Docker is commonly used in cloud environments where applications are designed to run in containers.

## Docker vs Virtual Machines (VMs)

- **Lightweight**: Containers share the host OS's kernel, whereas VMs require a full guest OS, making containers more lightweight.
- **Performance**: Containers typically offer better performance since they do not require the overhead of running an entire operating system.
- **Startup Time**: Containers start much faster than VMs due to the absence of booting a full OS.

## Orchestration Tools

- **Docker Swarm**: A native clustering tool for Docker, allowing you to manage multiple Docker hosts as a single virtual host.
- **Kubernetes**: A powerful container orchestration platform used to automate the deployment, scaling, and management of containerized applications.

## Best Practices

- Keep Docker images as small as possible by using minimal base images (e.g., alpine).
- Use multi-stage builds in Dockerfiles to separate the build environment from the runtime environment.
- Leverage Docker Compose for defining and managing multi-container applications.
- Clean up unused images, containers, and volumes to free up resources (`docker system prune`).

These notes cover fundamental Docker concepts, commands, and best practices, and should help you demonstrate a solid understanding of Docker in interviews.
