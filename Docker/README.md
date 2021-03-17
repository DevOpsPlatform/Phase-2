## Docker

Getting all the tooling setup on your computer can be a daunting(difficult) task, but getting Docker up and running on your favorite OS has become very easy.

Once you are done installing Docker, test your Docker installation by running the following:

    root@docker:~# docker run hello-world
    Unable to find image 'hello-world:latest' locally
    latest: Pulling from library/hello-world
    b8dfde127a29: Pull complete
    Digest: sha256:308866a43596e83578c7dfa15e27a73011bdd402185a84c5cd7f32a88b501a24
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

try this: docker run -it ubuntu bash

    This means, docker pull the image ubuntu from docker hub and create a container by runing the image, and then interact with container by bash mode

    root@docker:~# docker run -it ubuntu bash
    Unable to find image 'ubuntu:latest' locally
    latest: Pulling from library/ubuntu
    5d3b2c2d21bb: Pull complete
    3fc2062ea667: Pull complete
    75adf526d75b: Pull complete
    Digest: sha256:b4f9e18267eb98998f6130342baacaeb9553f136142d40959a1b46d6401f0f2b
    Status: Downloaded newer image for ubuntu:latest
    root@eb7d00f4ac2c:/#
    
exit from the container and list all the contains

    root@eb7d00f4ac2c:/# exit
    exit
    root@docker:~# docker ps -a
    CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                     PORTS               NAMES
    eb7d00f4ac2c        ubuntu              "bash"              2 minutes ago       Exited (0) 5 seconds ago                       funny_neumann
    e9534adbcd21        hello-world         "/hello"            6 minutes ago       Exited (0) 6 minutes ago                       tender_heisenberg
    root@docker:~#

```
docker pull alpine
```

    root@docker:~# docker pull alpine
    Using default tag: latest
    latest: Pulling from library/alpine
    ba3557a56b15: Pull complete
    Digest: sha256:a75afd8b57e7f34e4dad8d65e2c7ba2e1975c795ce1ee22fa34f8cf46f96a3be
    Status: Downloaded newer image for alpine:latest
    docker.io/library/alpine:latest
    root@docker:~# docker images
    REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
    hello-world         latest              d1165f221234        12 days ago         13.3kB
    ubuntu              latest              4dd97cefde62        13 days ago         72.9MB
    alpine              latest              28f6e2705743        4 weeks ago         5.61MB
    
The `pull` command fetches the alpine **image** from the **Docker registry** and saves it in our system. You can use the `docker images` command to see a list of all images on your system. 


