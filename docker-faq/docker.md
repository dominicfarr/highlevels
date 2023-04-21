## What is docker

* Virtualisation software
* Packages applications with everything that application needs. 
  * Including dependencies, configuration, system tools, and runtimes.
  * It is a standardised unit that has everything an application needs.
* It can be shared and distributed.

### What came before

* Each developer would need to replicate the application environment on their local machine. 
* This replication will be different between developers depending on OS, machine etc.
* Multiple steps, and configuration all manually executed.
* It can get very tedious and error prone.

### How do container solve this
* Containers isolated application environment away from the host OS.
* You do not have to install and manage multiple versions of required serviece like Runtime or DBs and related configuration.
* Only 1 cmd to run, which is the same for everyone. Docker standarises process.
* Quicker and easier than local setup
* It can standarise the deployment process as well. Reducing overhead
* Local and Test and Prod environments are the same across all aspects.
  
### Why is Docker `better` than VMs
* Docker virtualises the OS app layer and uses the OS kernal directly. 
* VMs virtualise OS and Kernal layer, which makes them larger and slower.
* However, docker cannot run a foriegn OS. But most envs are in Linux. 
* There is a hypervisor layer in Docker, if you really need to run foreign OSs

### Installation
* Docker engine
  * Manages images and containers
* Docker client
  * CLI that interacts with Docker engine
* GUI

### Image vs Containers
* Docker `Image` is an executable application artifact. Like jar in Maven or node package, but contains complete environment configuration: Applcation, services needed, and OS layer.
* Docker `Container` is a running image

### Docker registry
* Storage and distributation system for images
* Official images created by companies offering applications like Redis, Mongo, DBs, etc. 
* `DockerHub` is the largest collection of images.
* Docker team reviews and publishes official content; maintains images, has security experts.
* Images are versioned via a tag.

### Get an image
* Locate image
  * Search on hub
  * In cli 
    * `docker pull [name image]`

### Start an image / Create container
* In cli 
  * `docker run [image name]:[image tag]`
* Adding -d flag will run the container in the background or detached.
* To see background logs from a detached container in cli
  * `docker logs [container id]`
* Can skip the pull with a direct run cmd using image name from hub

### Expose container to host env
* bind local port to container port
  * cli
    * `docker run -d -p 8080:80 imagename:imagetag`

### Handy commands
* docker pull
* docker ps
* docker run
* docker start
* docker stop
* docker logs
* docker build

### Private registries
* AWS -> ECR
* Google -> Container Registry
* Nexus
* Docker has a private registry too

### Registry vs Responsitory
* Registry holds images and repos
* Repository collect related images but at different versions

### Create an image
* Create a definition in a file called [Dockerfile](./testApp/Dockerfile)
* `docker build -t app:1.0 .`