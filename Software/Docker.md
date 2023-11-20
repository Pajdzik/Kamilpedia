# Overview
- packages and runs an application in an isolated environment called a container
- containers are lightweight and contain everything needed to run the application
- container-based platform allows for highly portable workloads.
- lightweight and fast

# Architecture
- client-server architecture
- client talks to the daemon, which does the heavy lifting of building, running, and distributing
- REST API communication
- Docker Compose is another client
- Deamon
	- `dockerd`
	- listens for API requests and manages Docker objects such as images, containers, networks, and volumes
- Client
	- `docker`
	- user facing CLI
- Desktop
		- App containing deamon, client, and everything else
- Objects
	- images
		- read-only template with instructions for creating a container
		- often based on another image
		- Dockerfile defines steps to create and run it
		- each instruction in a Dockerfile creates a layer in the image
	- containers
		- runnable instance of an image
		- sandboxed process running on a host machine that is isolated from all other processes running on that host machine
	- networks
	- volumes
		- `docker run --mount` 
	- plugins

# Commands
- `run`
	- Starts a container
	- `-d` - detach, run in background
- `stop`
- `rm`
	- `-f` = `docker stop && docker rm`
- `exec`
	- executes a command in the container
- `volume`
	- `create`
	- 