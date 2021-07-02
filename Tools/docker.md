# Docker
## [What is Docker](#whatis)
## [Basic Docker Terminology](#terminology)
- ### [Image](#image1)
- ### [Dockerfile](#dockerfile1)
- ### [Build](#build1)
- ### [Container](#container1)
- ### [Volume](#volume1)
- ### [Tag](#tag1)
- ### [Repository](#repository1)
- ### [Registry](#registry1)
## [Running a Basic Container](#run)

## <a name="whatis"></a>What is Docker

Docker allows for easy deployment of applications into a sandbox environment that runs on the host operating system (i.e. Linux). The key benefit to Docker is that it allows users to package an application with all of its dependencies into a standardized unit for software development. Unlike VMs, containers don't have the heavy overhead of a Guest OS and therefore have higher efficient usage of the system resources avaliable.

## <a name="terminology"></a>Basic Docker Terminology

### <a name="image1"></a>**Image**

A package with all the dependencies and information needed to create a container. An image contains all of the dependencies (such as frameworks) plus deployment and execution configuration to be used by the container runtime. Usually an image derives from multiple base images that are layers stacked on top of each other to form the container's filesystem. **Important:** An image is immutable once it has been created.

### <a name="dockerfile1"></a>**Dockerfile**

A text file containing instructions on how to build an image. Similarly to a bash script, the first line states the base image to begin with followed by instructions for installing required programs, copying files, etc.

### <a name="build1"></a>**Build**

The action of building an image based on the contents of the Dockerfile.

### <a name="container1"></a>**Container**

An instance of a Docker image. A container represents the execution of a single application instance. It consists of the Docker image, execution environment, and a set of instructions to execute. In Docker you scale a service by starting multiple containers from the same Docker image.

### <a name="volume1"></a>**Volume**

A writable filesystem that the container can use to write persistent data. Since images are read-only and most systems need to write to the filesystem, volumes add the writable filesystem to a container.

### <a name="tag1"></a>**Tag**

A label that can be applied to an image so that different images or versions of the same image can be easlily identified.

### <a name="repository1"></a>**Repository**

A collection of related Docker images that are tagged to indicate the version of the image. Some repos contain multiple variants of a specific image, such as an image including the SDK (heavier), a runtime only image (lighter), etc. These variants can be identified by different tagging schemes. There can also be platform variants for a single image based on a tag such as Linux and Windows images.

### <a name="registry1"></a>**Registry**

A service that provides access to a set of Docker images. The default registry is [Docker Hub](https://hub.docker.com) (owned by the Docker organization). It contains many of the most popular and most used open source images. Companies usually have a registry to store the images for a large number of groups/teams.

## <a name="run"></a>Running a Basic Container

We will start with running a basic container that just outputs some text to the log and exits when it is done. This exercise is the "Hello World!" of Docker.

During this section we will be using a very popular Docker Linux distribution called [Alpine](https://alpinelinux.org/). Alpine is a lightweight minimalistc OS that makes it perfect for running Docker.

Lets start by starting the container on our Docker instance:

```bash
docker run hello-world
```

Expected Output:

```text
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
1b930d010525: Pull complete
Digest: sha256:2557e3c07ed1e38f26e389462d03ed943586f744621577a99efb77324b0fe535
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```

This will start the docker container based on the `hello-world` image and run it in the foreground. If we want to run the container as a background job we can use the `-d` flag and Docker will not hold the terminal session or write logs out to the terminal window. When the container has exited your terminal session will be released from the container.

You will notice that in the output it starts with "Unable to find image". This is because the image has not yet been pulled down from Docker Hub and needs to be downloaded before it can be started. Also, if you have a keen eye you will notice that when we ran the command we just specified `hello-world` but Docker said it couldn't find `hello-world:latest` the `latest` part is the tag for that image and if no tag is specified the default tag is `latest`.

Everything in the output from **Hello from Docker!** onward is the log from the container as it is running. We will get more into how Docker logging works later.


https://dockerlabs.collabnix.com/docker/cheatsheet/