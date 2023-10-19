---
id: 5206
title: 'Docker Commands With Examples &#8211; Definitive Guide to Docker [2021]'
date: '2021-02-10T17:23:39+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=5206'
permalink: /basic-docker-commands-with-examples/
rank_math_seo_score:
    - '85'
rank_math_focus_keyword:
    - 'docker commands,docker command,docker tutorial,docker container,docker image'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
rank_math_internal_links_processed:
    - '1'
ss_social_share_disable:
    - ''
rank_math_description:
    - 'In this Docker tutorial, you''ll work with most of the basic Docker Commands with examples. Docker is an open-source containerization platform. It is used to build apps and micro-services.'
rank_math_pillar_content:
    - 'on'
rank_math_primary_category:
    - '16'
socialsnap_share_count_timestamp:
    - '2023-09-16 23:12:18'
ss_total_share_count:
    - '0'
tve_landing_page:
    - ''
tve_disable_theme_dependency:
    - ''
tve_content_before_more:
    - ''
tve_content_more_found:
    - ''
tve_save_post:
    - ''
tve_custom_css:
    - ''
tve_user_custom_css:
    - ''
tve_page_events:
    - ''
tve_globals:
    - ''
tve_global_scripts:
    - ''
thrive_icon_pack:
    - ''
thrive_tcb_post_fonts:
    - ''
tve_has_masonry:
    - ''
tve_has_typefocus:
    - ''
tve_updated_post:
    - ''
tve_has_wistia_popover:
    - ''
rank_math_analytic_object_id:
    - '3'
categories:
    - how-to
tags:
    - docker
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

[Docker ](https://www.docker.com/)is an open-source containerization platform. It is used to build apps and micro-services. Docker applications are fast as it shares the kernel and other resources. It employs virtualization at the OS-level. As the [Official Docker Documentation](https://docs.docker.com/) says,

> ” Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly. “
> 
> <cite> – [Official Docker Documentation](https://docs.docker.com/get-started/overview/)</cite>

Docker enables developers to package applications into containers. Docker container contains the portable code, merged with the operating system libraries and dependencies.

Docker Containers are,

- Flexible
- Lightweight
- Portable
- Loosely coupled
- Scalable
- Secure.

In this Docker tutorial, you’ll work with most of the basic Docker Commands with examples.[ ](https://www.docker.com/)

List of Docker Command s, you’ll learn in this tutorial.

- [docker –help](#help)
- [docker –version](#version)
- [docker info](#info)
- [docker login](#login)
- [docker logout](#logout)
- [docker search](#search)
- [docker image build](#image-build)
- [docker image pull](#image-pull)
- [docker images](#images)
- [docker image ls](#image-ls)
- [docker image rm](#image-rm)
- [docker image rmi](#image-rmi)
- [docker image prune](#image-prune)
- [docker container create](#container-create)
- [docker ps](#ps)
- [docker container start](#container-start)
- [docker run](#run)
- [docker container inspect](#container-inspect)
- [docker container log](#container-log)
- [docker container stop](#container-stop)
- [docker container kill](#container-kill)
- [docker container restart](#container-restart)
- [docker container rm](#container-rm)

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

- **\[Important\]** – Ensure you have Docker installed, if you do not have Docker installed in your server, Install Docker by following the guide [How to install Docker on Ubuntu 20.04](http://149.28.53.131/install-docker-on-ubuntu/).

## <span class="ez-toc-section" id="understanding_dockerfiles_docker_images_and_docker_containers"></span>Understanding Dockerfiles, Docker Images and Docker Containers<span class="ez-toc-section-end"></span>

### Dockerfiles

<mark>[Dockerfile](https://codefresh.io/docker-tutorial/build-docker-image-dockerfiles/)</mark> is a simple text document that has a set of commands to assemble a Docker image automatically. The <mark>docker build</mark> command is used to execute the commands in the <mark>Dockerfile</mark> sequentially.

### Docker Images

Docker image consists of a Dockerfile and dependencies. It is a read-only template. Docker Images contains instructions to create a Docker Container.

### Docker Container

Docker Container is the instance of Docker Images. Docker Containers has access to resources running in a different host or container. It is an isolated and secure application platform.

You must have a clear idea whether you are working with Docker Images or Docker Containers.

In this step, you’ve understand the basic differences between Dockerfile, Docker Images and Docker Container.

In the next step, you’ll learn about the different components of Docker Commands.

## <span class="ez-toc-section" id="understanding_the_anatomy_of_docker_commands"></span>Understanding the Anatomy of Docker Commands<span class="ez-toc-section-end"></span>

In this step, you’ll learn about the different parts of Docker Commands.

You can see the various components of <mark>docker</mark> commands in the below command.

```
<pre class="wp-block-code">```
sudo docker [option] [management command] [command] [arguments]
```
```

- **docker** – specifies the base command for docker
- **\[option\]** – specifies optional commands of the docker command
- **\[management** **command\]** – specifies command for managing docker
- **\[command\]** – specifies the actual docker command
- **\[arguments\]** – specifies the arguments of the docker command.

You can refer to this [Docker tutorial](http://149.28.53.131/install-docker-on-ubuntu/#using_docker_command_without_sudo) if you have to execute docker command without sudo.

### Listing Docker Options, Management Commands and Commands

You can list all the available Docker Commands by using the below command.

```
<pre class="wp-block-code">```
docker --help
```
```

You can add –help at the end of any Docker command to get information about the command.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default
                           "/home/ubuntu/.docker")
  -c, --context string     Name of the context to use to connect to the
                           daemon (overrides DOCKER_HOST env var and
                           default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level
                           ("debug"|"info"|"warn"|"error"|"fatal")
                           (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default
                           "/home/ubuntu/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default
                           "/home/ubuntu/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default
                           "/home/ubuntu/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  app*        Docker App (Docker Inc., v0.9.1-beta3)
  builder     Manage builds
  buildx*     Build with BuildKit (Docker Inc., v0.5.1-docker)
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container\'s changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container\'s filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container\'s filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes
```
```

### Knowing Your Docker Version

To view your Docker version you can execute the below command.

```
<pre class="wp-block-code">```
docker --version
```
```

- **docker** – specifies the base command for docker
- **–version** – It is one of the <mark>\[option\]</mark> commands in Docker. It displays the version of Docker.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Docker version <var>20.10.2</var>, build 2291f61
```
```

### Knowing Your Docker Installation

You can get a detailed information of Docker installed on your system using the below command.

```
<pre class="wp-block-code">```
docker info
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  app: Docker App (Docker Inc., v0.9.1-beta3)
  buildx: Build with BuildKit (Docker Inc., v0.5.1-docker)

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 20.10.3
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Native Overlay Diff: true
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 1
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 io.containerd.runtime.v1.linux runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 269548fa27e0089a8b8278fc4fc781d7f65a939b
 runc version: ff819c7e9184c13b7c2607fe6c30ae19403a7aff
 init version: de40ad0
 Security Options:
  apparmor
  seccomp
   Profile: default
 Kernel Version: 5.4.0-1029-aws
 Operating System: Ubuntu 20.04.1 LTS
 OSType: linux
 Architecture: x86_64
 CPUs: 1
 Total Memory: 978.6MiB
 Name: ip-172-31-47-101
 ID: TFGJ:5ZYC:22WJ:AEZP:ZBQJ:LQAD:LY3I:2QX2:4GNR:FNAQ:R6FJ:ENJU
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Registry: https://index.docker.io/v1/
 Labels:
 Experimental: false
 Insecure Registries:
  127.0.0.0/8
 Live Restore Enabled: false
```
```

Your output for the info command may vary based on the installation setup.

In the next step, You’ll start executing Docker Commands for Docker Hub.

## <span class="ez-toc-section" id="exploring_docker_commands_for_docker_hub"></span>Exploring Docker Commands for Docker Hub<span class="ez-toc-section-end"></span>

In this step, you’ll execute basic Docker commands for Docker Hub. Docker Hub is used for locating and distributing container images. It is a service provided by Docker.

### Login to a Docker Registry

```
<pre class="wp-block-code">```
docker login [options] [server]
```
```

- **docker** – specifies the base command for Docker
- **login** – specifies login to Docker Registry
- **\[options\]** – specifies the option commands for <mark>docker login</mark>
- **\[server\]** – specifies the server where the Docker Registry is located

You have to [create a Docker hub account](http://hub.docker.com), if you don’t have one with you. It is a free service provided by Docker.

You can execute the below command to login to the Docker Hub (Default Docker registry).

```
<pre class="wp-block-code">```
docker login
```
```

You’ll see the below output.

You’ll be prompted to enter your Docker Hub username and password.

Output

```
<pre class="wp-block-code config">```

Login with your Docker ID to push and pull images from Docker Hub. If you don\'t have a Docker ID, head over to https://hub.docker.com to create one.
Username: askvikram
Password:
WARNING! Your password will be stored unencrypted in /home/ubuntu/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
```
```

### Logout From a Docker Registry

You can use the below command to logout from a Docker registry.

```
<pre class="wp-block-code">```
docker logout [server]
```
```

- **docker** – specifies the base command for Docker
- **logout** – specifies the Docker Server to logout from registry
- **\[server\]** – specifies the URL of the Docker registry

For example, to logout from the Docker Hub, you’ll use the below command.

```
<pre class="wp-block-code">```
docker logout
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Removing login credentials for https://index.docker.io/v1/
```
```

In the next step, You’ll learn about the Docker <mark>search</mark> command.

### Exploring Docker Search Command

In this step, you’ll learn the Docker <mark>search</mark> command for searching a Docker Image in the Docker Hub. The <mark>search</mark> command is a child command of the <mark>docker</mark> command.

#### **Searching Docker Images by Name**

To search for Docker Images in the Docker Hub, you’ll use the below Docker command. You have to replace the <var>image\_name</var> with the Docker Image name.

```
<pre class="wp-block-code">```
docker search [options] <var>image_name</var>
```
```

- **docker** – specifies the base command for docker
- **search** – searches Docker Hub for images
- **\[options\]** – specifies optional commands of the <mark>docker search</mark> command
- **image\_name** – specifies the name of Docker Image to search in the Docker Hub

For example, to search for Docker Image of <var>Ubuntu</var> in the Docker Hub, you will use the below Docker command.

```
<pre class="wp-block-code">```
docker search <var>ubuntu</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                                                      DESCRIPTION                                  STARS     OFFICIAL   AUTOMATED
ubuntu                                                    Ubuntu is a Debian-based Linux operating sys…   11793     [OK]
dorowu/ubuntu-desktop-lxde-vnc                            Docker image to provide HTML5 VNC interface …   495                  [OK]
websphere-liberty                                         WebSphere Liberty multi-architecture images …   267       [OK]
rastasheep/ubuntu-sshd                                    Dockerized SSH service, built on top of offi…   250                  [OK]
consol/ubuntu-xfce-vnc                                    Ubuntu container with "headless" VNC session…   232                  [OK]
ubuntu-upstart                                            Upstart is an event-based replacement for th…   110       [OK]
neurodebian                                               NeuroDebian provides neuroscience research s…   79        [OK]
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mysql-5      ubuntu-16-nginx-php-phpmyadmin-mysql-5          50                   [OK]
ubuntu-debootstrap                                        debootstrap --variant=minbase --components=m…   44        [OK]
open-liberty                                              Open Liberty multi-architecture images based…   42        [OK]
nuagebec/ubuntu                                           Simple always updated Ubuntu docker images w…   24                   [OK]
i386/ubuntu                                               Ubuntu is a Debian-based Linux operating sys…   24
[.....]
```
```

You’ve successfully searched for a Docker Image from the Docker Hub.

#### **OPTIONAL: Exploring the OPTIONS in the Search Command \[[Skip](#image-commands)\]**

- **–filter** – filter the output based on the condition you provide
- **–limit** – limits the max search results to the number you provide

#### **Applying Filters in the Search Command**

First, you’ll use the <mark>–filter</mark> option to filter the search results of the <mark>docker search</mark> command.

You can filter the search result based on the following criteria.

- **–filter stars=<var>number</var>\[int\]** – lists only the Docker Images with more than the given <var>number</var> of stars
- **–filter is-automated=**<var>boolean</var>**\[true, false\]** – lists only automated Docker Images if the \[<var>boolean</var>\] is set to true,
- **–filter is-official=**<var>boolean</var>**\[true, false\]** – lists only official Docker Images if the \[<var>boolean</var>\] is set to true,

#### **Filtering Based on Stars**

You can filter the search results of Docker images from Docker Hub which has at least <var>number</var>(50 in this case) stars, using the below command.

```
<pre class="wp-block-code">```
docker search --filter=stars=<var>50</var> <var>ubuntu</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                                                   DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
ubuntu                                                 Ubuntu is a Debian-based Linux operating sys…   11795     [OK]
dorowu/ubuntu-desktop-lxde-vnc                         Docker image to provide HTML5 VNC interface …   495                  [OK]
websphere-liberty                                      WebSphere Liberty multi-architecture images …   267       [OK]
rastasheep/ubuntu-sshd                                 Dockerized SSH service, built on top of offi…   250                  [OK]
consol/ubuntu-xfce-vnc                                 Ubuntu container with "headless" VNC session…   232                  [OK]
ubuntu-upstart                                         Upstart is an event-based replacement for th…   110       [OK]
ansible/ubuntu14.04-ansible                            Ubuntu 14.04 LTS with ansible                   98                   [OK]
neurodebian                                            NeuroDebian provides neuroscience research s…   79        [OK]
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mysql-5   ubuntu-16-nginx-php-phpmyadmin-mysql-5          50                   [OK]
```
```

Notice that, you’ll get back Docker Images that has exactly 50 stars and more.

#### **Filtering Based on Automated Images**

You can filter the search results that are automated images, using the below command.

```
<pre class="wp-block-code">```
docker search --filter=is-automated=true <var>ubuntu</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                                                      DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
dorowu/ubuntu-desktop-lxde-vnc                            Docker image to provide HTML5 VNC interface …   495                  [OK]
rastasheep/ubuntu-sshd                                    Dockerized SSH service, built on top of offi…   250                  [OK]
consol/ubuntu-xfce-vnc                                    Ubuntu container with "headless" VNC session…   232                  [OK]
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mysql-5      ubuntu-16-nginx-php-phpmyadmin-mysql-5          50                   [OK]
nuagebec/ubuntu                                           Simple always updated Ubuntu docker images w…   24                   [OK]
1and1internet/ubuntu-16-apache-php-5.6                    ubuntu-16-apache-php-5.6                        14                   [OK]
1and1internet/ubuntu-16-apache-php-7.0                    ubuntu-16-apache-php-7.0                        13                   [OK]
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mariadb-10   ubuntu-16-nginx-php-phpmyadmin-mariadb-10       11                   [OK]
1and1internet/ubuntu-16-nginx-php-5.6-wordpress-4         ubuntu-16-nginx-php-5.6-wordpress-4             8                    [OK]
1and1internet/ubuntu-16-apache-php-7.1                    ubuntu-16-apache-php-7.1                        6                    [OK]
1and1internet/ubuntu-16-nginx-php-7.0                     ubuntu-16-nginx-php-7.0                         4                    [OK]
smartentry/ubuntu                                         ubuntu with smartentry                          1                    [OK]
1and1internet/ubuntu-16-php-7.1                           ubuntu-16-php-7.1                               1                    [OK]
1and1internet/ubuntu-16-sshd                              ubuntu-16-sshd                                  1                    [OK]
```
```

#### **Filtering Based on Official Images**

You can filter the search results that are Official images, using the below command.

```
<pre class="wp-block-code">```
 docker search --filter=is-official=true <var>ubuntu</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
ubuntu              Ubuntu is a Debian-based Linux operating sys…   11795     [OK]
websphere-liberty   WebSphere Liberty multi-architecture images …   267       [OK]
ubuntu-upstart      Upstart is an event-based replacement for th…   110       [OK]
neurodebian         NeuroDebian provides neuroscience research s…   79        [OK]
```
```

#### **Applying Multiple Filter in Search Command**

You can apply multiple filters in <mark>search</mark> command by adding <mark>–filter</mark> before the filters, as shown in the below command.

```
<pre class="wp-block-code">```
docker search --filter is-official=true --filter stars=<var>50</var> <var>ubuntu</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                 DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
ubuntu               Ubuntu is a Debian-based Linux operating sys…   11795     [OK]
websphere-liberty    WebSphere Liberty multi-architecture images …   267       [OK]
ubuntu-upstart       Upstart is an event-based replacement for th…   110       [OK]
neurodebian          NeuroDebian provides neuroscience research s…   79        [OK]
```
```

You’ve successfully searched a Docker Image in the Docker Hub.

In the next step, you’ll execute Docker commands for Docker Image.

## <span class="ez-toc-section" id="exploring_docker_commands_for_docker_image"></span>Exploring Docker Commands for Docker Image<span class="ez-toc-section-end"></span>

In this step, you’ll learn and execute some of the basic Docker commands for Docker Images. The below command is the parent command for managing Docker images.

```
<pre class="wp-block-code">```
docker image [command]
```
```

- **docker** – specifies the base command for docker
- **image**– specifies Management command for Docker Images
- **\[command\]** – specifies any Docker Container commands

### Developing Docker Image From Dockerfile

You can build a Docker Image from Dockerfile using the below command.

```
<pre class="wp-block-code">```
docker image build <var>path/to/docker_file</var> .
```
```

- **build** – specifies that Docker image is developed from Dockerfile
- **path/to/Dockerfile** – path of the Docker file, it may be local path or URL
- **. (period)** – specifies that the Docker Image is created in the current folder

### Downloading Docker Image From a Docker Hub

You can pull a Docker Image from Docker Repository using the below command.

```
<pre class="wp-block-code">```
docker image pull [options] <var>name</var>
```
```

- **pull** – pulls an image or a repository from a registry
- **name** – specifies the name of the Docker Image

For example, to download <var>Redis </var>image from Docker Hub, you’ll use the below command.

```
<pre class="wp-block-code">```
docker image pull <var>redis</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Using default tag: latest
latest: Pulling from library/redis
a076a628af6f: Pull complete
f40dd07fe7be: Pull complete
ce21c8a3dbee: Pull complete
ee99c35818f8: Pull complete
56b9a72e68ff: Pull complete
3f703e7f380f: Pull complete
Digest: sha256:fffdb7cc1ecc787ffa3b7a1d7fa794e158a91541f452093ae24d206cd12562bf
Status: Downloaded newer image for redis:latest
docker.io/library/redis:latest
```
```

Notice that, pull command first search for the Docker image locally in local Image cache. If the image is not present in the Image cache then it downloads the image from the Docker hub.

### Listing All Docker Images in Your System

You can list the Docker Images present in your system locally, using the below command.

```
<pre class="wp-block-code">```
 docker images
```
```

- **docker** – specifies the base command for Docker
- **images –** specifies to list all images

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
<var>ubuntu       latest    f63181f19b2f   2 weeks ago   72.9MB</var>
```
```

You’ll see a list of locally available Docker Images.

Alternatively, You can use <mark>docker image ls</mark> command to list all images in your system

```
<pre class="wp-block-code" id="image-ls">```
docker image ls 
```
```

### Removing Docker Image

You can remove a Docker Image from your system in one of the two ways given below.

- Remove Image using <mark>rm</mark> command
- Remove Image using <mark>rmi</mark> command

#### **Removing Docker Image by Name/ID Using <mark>Rm</mark> Command**

You’ll use the below command to delete a Docker Image using its name or its ID.

```
<pre class="wp-block-code">```
docker image rm <var>image_name_or_ID</var>
```
```

- **docker**  – specifies the base command for docker
- **image** – specifies the management command for Docker Image
- **rm** – specifies that you want to remove one or more images
- **image\_name\_or\_ID** – specifies the name or ID of the Docker Image

For example, if the Image Name is <var>ubuntu</var> and the Image ID is <var>f63181f19b2f</var>. You can use either of the two commands given below.

```
<pre class="wp-block-code">```
docker image rm <var>ubuntu</var>
```
```

(OR)

```
<pre class="wp-block-code">```
docker image rm <var>f63181f19b2f</var> 
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Untagged: <var>ubuntu</var>:latest
Untagged: <var>ubuntu@sha256:703218c0465075f4425e58fac086e09e1de5c340b12976ab9eb8ad26615c3715</var>
Deleted: <var>sha256:f63181f19b2fe819156dcb068b3b5bc036820bec7014c5f77277cfa341d4cb5e</var>
Deleted: <var>sha256:0770b7f116f8627ec336a62e65a1f79e344df7ae721eb3e06e11edca85d3d1e7</var>
Deleted: <var>sha256:476e931831a5b24b95ff7587cca09bde9d1d7c0329fbc44ac64793b28fb809d0</var>
Deleted: <var>sha256:9f32931c9d28f10104a8eb1330954ba90e76d92b02c5256521ba864feec14009</var>
```
```

#### **Removing Docker Image by Name/ID Using <mark>Rmi</mark> Command**

You’ll use the below command to delete Docker Image either by name or ID.

```
<pre class="wp-block-code">```
 docker rmi <var>image</var> 
```
```

- **docker** – specifies the base command for docker
- **rmi** – specifies removing one or more images
- **image**– specifies the name/ id of the image

For example, if you consider the name\_or\_id is <var>ubuntu</var>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Untagged: ubuntu:latest
Untagged: ubuntu@sha256:703218c0465075f4425e58fac086e09e1de5c340b12976ab9eb8ad26615c3715
Deleted: sha256:f63181f19b2fe819156dcb068b3b5bc036820bec7014c5f77277cfa341d4cb5e
Deleted: sha256:0770b7f116f8627ec336a62e65a1f79e344df7ae721eb3e06e11edca85d3d1e7
Deleted: sha256:476e931831a5b24b95ff7587cca09bde9d1d7c0329fbc44ac64793b28fb809d0
Deleted: sha256:9f32931c9d28f10104a8eb1330954ba90e76d92b02c5256521ba864feec14009
```
```

#### **Removing Multiple Docker Images Using Rmi Command**

You’ll use the below command to delete multiple Docker Images by specifying either its name or ID (Consider <var>ubuntu</var> for image\_1 and <var>redis</var> for image\_2).

```
<pre class="wp-block-code">```
docker rmi <var>image_1</var> <var>image_2</var> ...
```
```

- **docker**  – specifies the base command for Docker
- **rmi** – specifies removing one or more Docker Images
- **image\_1, image\_2, …** – specifies the Name or ID of the Docker Images

For example, if you consider image\_1 as <var>ubuntu</var> and image\_2 as <var>redis</var>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Untagged: ubuntu:latest
Untagged: ubuntu@sha256:703218c0465075f4425e58fac086e09e1de5c340b12976ab9eb8ad26615c3715
Deleted: sha256:f63181f19b2fe819156dcb068b3b5bc036820bec7014c5f77277cfa341d4cb5e
Deleted: sha256:0770b7f116f8627ec336a62e65a1f79e344df7ae721eb3e06e11edca85d3d1e7
Deleted: sha256:476e931831a5b24b95ff7587cca09bde9d1d7c0329fbc44ac64793b28fb809d0
Deleted: sha256:9f32931c9d28f10104a8eb1330954ba90e76d92b02c5256521ba864feec14009
Untagged: redis:latest
Untagged: redis@sha256:0f97c1c9daf5b69b93390ccbe8d3e2971617ec4801fd0882c72bf7cad3a13494
Deleted: sha256:621ceef7494adfcbe0e523593639f6625795cc0dc91a750629367a8c7b3ccebb
Deleted: sha256:de66cfbf4712b8ba9ef292e08ef7487be26d9d21b350548e400ae351405d820e
Deleted: sha256:79b2381e35429e8fc04d31b3445f069c22d288bf5c4cba7b7c10004ff78ae201
Deleted: sha256:1d047d19be363b00139990d4d7f392dabdb0809dbc9d0fbe67c1f15b8caed27a
Deleted: sha256:8c41f4e708c37059df28ae1cabc200a6db2fee45bd3a2cadcf70f2765bb68730
Deleted: sha256:b51317bef36fe1900be48402c8a41fcd9cdb6b8950c10209f764473cb8323371
Deleted: sha256:cb42413394c4059335228c137fe884ff3ab8946a014014309676c25e3ac86864

```
```

#### **Remove Dangling Images**

Dangling images are the Layers in a Docker Image that does not serve any purpose and consume Dick space.

You can remove dangling images, using the below command.

```
<pre class="wp-block-code">```
docker image prune
```
```

- **prune** – remove unused images

You’ll get a prompt to enter (y/n). Press <mark>y</mark>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
WARNING! This will remove all dangling images.
Are you sure you want to continue? [y/N] y
Total reclaimed space: 1034B
```
```

In the next step, you’ll execute Docker commands for Docker Container.

## <span class="ez-toc-section" id="exploring_docker_commands_for_docker_container"></span>Exploring Docker Commands for Docker Container<span class="ez-toc-section-end"></span>

In this step, you’ll execute some of the basic Docker commands for Docker Containers. The below command is the parent command for managing Docker Containers.

```
<pre class="wp-block-code">```
docker container [command]
```
```

- **docker** – specifies the base command for docker
- **container** – specifies Management command for Docker Containers
- **\[command\]** – specifies any Docker Image commands

### Creating a Docker Container

To create a Docker Container, you will use the create command

```
<pre class="wp-block-code">```
docker container create [option] image 
```
```

- **create** – specifies the command to create a new container
- **\[option\]** – specifies the option command for Docker container
- **image** – specifies the Docker Image to create Docker container

For example, to create a Docker Container for <var>redis</var>, you’ll use the below command.

```
<pre class="wp-block-code">```
docker container create <var>redis</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code conifg">```
<var>4ec9f348221ff2248188f431974a989c451fef149952b11a57116695eb66f36d</var>
```
```

You’ll see the ID of the newly created Container.

You’ve successfully created Docker Container from a Docker Image.

### Listing All Docker Containers

You’ll use the below Docker command, to list all Docker containers that are running, exited or stopped.

```
<pre class="wp-block-code">```
docker ps -a
```
```

- **ps** – specifies to list containers
- **-a** – specifies to show all containers

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
CONTAINER ID   IMAGE     COMMAND                  CREATED             STATUS                         PORTS     NAMES
<var>4ec9f348221f   redis     "docker-entrypoint.s…"   46 seconds ago      Created                                 zen_rosalind</var>
```
```

Name and ID for the container is created when you start the container. Make a note of either the Name or ID of the Container which is used in the next step.

In the next step, you’ll run the existing Docker Container.

### Starting an Existing Docker Container

To start one stopped or newly created Docker containers, you’ll use the below command

```
<pre class="wp-block-code">```
docker container start [options] container_id
```
```

- **start** – specifies to start one or more existing containers
- \[**options**\] – specifies the optional commands for docker container start
- **container\_id** – specifies the ID of the container.

For example, to start the Ubuntu Image, you’ll use the below command.

```
<pre class="wp-block-code">```
docker container start -i <var>4ec9f348221f</var>
```
```

- –**i** – specifies to keep STDIN open

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
<var>4ec9f348221f</var>
```
```

### Listing All Running Docker Containers

You’ll use the below Docker command, to list all Docker containers that are in running status.

```
<pre class="wp-block-code">```
docker ps
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config" id="run">```
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS         PORTS      NAMES
<var>4ec9f348221f   redis     "docker-entrypoint.s…"   12 minutes ago   Up 5 minutes   6379/tcp   zen_rosalind</var>
```
```

You’ve successfully started a Docker Container.

In the nest step, you’ll use the run command.

### Running a Docker Container

Docker <mark>run</mark> command is the combination of <mark>create</mark> and <mark>start</mark> commands. It is used to run a Docker container.

To run a Docker container, you can use the below command.

```
<pre class="wp-block-code">```
docker run -it redis
```
```

- **run**  – specifies to run a command in a new container
- –**i** – specifies to keep STDIN open
- **-t** – specifes to allocate a pseudo-TTY
- **redis** – specifies the image name

You’ll see the below output.

Output

```
<pre class="wp-block-code config" id="container-inspect">```
1:C 09 Feb 2021 11:20:39.069 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 09 Feb 2021 11:20:39.069 # Redis version=6.0.10, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 09 Feb 2021 11:20:39.070 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
                _._
           _.-``__ ''-._
      _.-``    `.  `_.  ''-._           Redis 6.0.10 (00000000/0) 64 bit
  .-`` .-```.  ```\/    _.,_ ''-._
 (    '      ,       .-`  | `,    )     Running in standalone mode
 |`-._`-...-` __...-.``-._|'` _.-'|     Port: 6379
 |    `-._   `._    /     _.-'    |     PID: 1
  `-._    `-._  `-./  _.-'    _.-'
 |`-._`-._    `-.__.-'    _.-'_.-'|
 |    `-._`-._        _.-'_.-'    |           http://redis.io
  `-._    `-._`-.__.-'_.-'    _.-'
 |`-._`-._    `-.__.-'    _.-'_.-'|
 |    `-._`-._        _.-'_.-'    |
  `-._    `-._`-.__.-'_.-'    _.-'
      `-._    `-.__.-'    _.-'
          `-._        _.-'
              `-.__.-'

1:M 09 Feb 2021 11:20:39.076 # Server initialized
1:M 09 Feb 2021 11:20:39.076 # WARNING overcommit_memory is set to 0! Background save may fail under low memory condition. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 09 Feb 2021 11:20:39.076 * Ready to accept connections

```
```

You can quit the Redis server by pressing <mark>CTRL+C</mark>.

### Inspecting a Docker Container

You can view information about your Docker container using the below Docker command.

```
<pre class="wp-block-code">```
docker container inspect container
```
```

- **inspect** – displays detailed information on one or more containers
- **container** – specifies the name or ID of the container

For example, to inspect the <var>redis</var> container with container name as <var>zen\_rosalind</var> and container ID as <var>4ec9f348221f</var>, you’ll use one of the two below commands.

```
<pre class="wp-block-code">```
docker container inspect <var>4ec9f348221f</var>
```
```

(OR)

```
<pre class="wp-block-code">```
docker container inspect <var>zen_rosalind</var>
```
```

You’ll see detailed information about the container.

You can check the activities of your container using the <mark>log</mark> command.

```
<pre class="wp-block-code" id="container-log">```
docker container log container
```
```

- **log** – specifies to print the log details of the container
- **container** – specifies the name or ID of the container.

### Stopping a Docker Container

You’ll use the below Docker command to stop a running Docker container.

```
<pre class="wp-block-code">```
docker container stop <var>container</var>
```
```

- **docker**  — specifies the base command for Docker
- **container** – specifies the management command for Docker container
- **stop** – specifies the command to stop one or more Docker containers
- **container** – specifies the name or ID of the Docker containers

For example, to stop a Docker Container of Redis with the name *zen\_rosalind* and ID *4ec9f348221f*, you’ll use one of the below two commands.

```
<pre class="wp-block-code">```
docker container stop <var>zen_rosalind </var>
```
```

(OR)

```
<pre class="wp-block-code">```
docker container stop <var>4ec9f348221f</var>
```
```

You”ll get the ID or name as the output. This verifies that the container is stopped.

You can verify it by running <mark>docker ps</mark> command.

Alternatively you can use the below command to stop one or more Docker containers.

```
<pre class="wp-block-code" id="container-kill">```
docker container kill container
```
```

- **docker** – specifies the base command for docker
- **container** – specifies the management command for Docker container
- **kill** – specifies to stop one or more containers
- **container** – specifies the name or ID of the Docker containers

stop command is preferred over kill command because when you stop a container using stop command it generally waits for 10 seconds before the process is shutdown whereas using kill command shuts down immediately.

### Stopping Multiple Docker Containers

To stop more than one container you can use the below Docker command.

```
<pre class="wp-block-code">```
docker container stop <var>container_1 </var><var>container_2 [...]</var>
```
```

- **docker**  – specifies the base command for docker
- **container** – specifies the management command for containers
- **stop** – specifies the stop container command
- **container\_1 container\_2 \[…\]** – specifies the name or ID of containers

You’ll see the container ID or name in the output.

You can verify whether the containers stopped running using the <mark>docker ps</mark> command.

### Restarting a Docker Container

You’ll use the below command to restart a Docker container.

```
<pre class="wp-block-code">```
docker container restart <var>container</var>
```
```

- **docker**  – specifies the base command for docker
- **container** – specifies the management command for Docker container
- **restart** – specifies to restart a Docker container
- **container** – specifies the name or ID of the Docker container

For example, to restart a Docker Container of Redis with the name *zen\_rosalind* and ID *4ec9f348221f*, you’ll use one of the below two commands.

```
<pre class="wp-block-code">```
docker container restart <var>zen_rosalind </var>
```
```

(OR)

```
<pre class="wp-block-code">```
docker container restart <var>4ec9f348221f</var>
```
```

You”ll get the ID or name as the output. This verifies that the container is restarted.

You can verify it by running <mark>docker ps</mark> command.

### Removing a Docker Container

You can remove a Docker container using the below command.

```
<pre class="wp-block-code">```
docker container rm <var>container</var>
```
```

- **docker**  – specifies the base command for docker
- **container** – specifies the management command for container
- **rm** – specifies the command to remove one or more containers
- **container** – specifies the name or ID of the container

For example, to remove a Docker Container of Redis with the name *zen\_rosalind* and ID *4ec9f348221f*, you’ll use one of the below two commands.

```
<pre class="wp-block-code">```
docker container rm <var>zen_rosalind </var>
```
```

(OR)

```
<pre class="wp-block-code">```
docker container rm <var>4ec9f348221f</var>
```
```

You”ll get the ID or name as the output. This verifies that the container is removed.

You can verify it by running <mark>docker ps -a</mark> Docker command.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you’ve learnt how to use basic and essential Docker commands for Docker Hub, Docker Images and Docker Containers. You’ve executed the commands and verified the output with examples.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

If you are using a shared hosting, try switching to dedicated cloud hosting with Cloudways. As low as 10$ per month.   
[![Load WordPress Sites in as fast as 37ms!](//www.cloudways.com/affiliate/accounts/default1/banners/4869f424.jpg "Load WordPress Sites in as fast as 37ms!")](https://www.cloudways.com/en/wordpress-cloud-hosting.php?id=770792&a_bid=4869f424&chan=speedtutorials)![](https://www.cloudways.com/affiliate/scripts/imp.php?id=770792&a_bid=4869f424&chan=speedtutorials)  
## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1613024710305">### How do I get into a Docker container’s shell?  


<div class="rank-math-answer ">You can use the below Docker command to get into the Docker Container Shell  
<mark>docker exec -it container image</mark>  
– **docker –**  specifies the base command for docker  
– **exec** – specifies to run a command in a running container.  
– **-it** – specifies to keep the STDIN open  
–  **container** – specifies the name or ID of the container  
– **image** – specifies the name of the image  
For example, to get into a bash container with ID 53fgyr2412er, you’ll use the below command.  
<mark>docker exec -it 53fgyr2412er bash</mark>

</div></div><div class="rank-math-list-item" id="faq-question-1613025033401">### How to copy files from host to Docker container?

<div class="rank-math-answer ">You can use the below Docker command to copy files from host to Docker container.  
<mark>docker cp file.txt container:/file.txt</mark>  
– **docker**  – specifies the base command for docker  
–  **cp –** specifies the command to copy files in a container  
– **file.txt** – specifies the files to be copied  
– **container:/file.txt**– specifies the name or ID of the container and the path of the file in the container

</div></div><div class="rank-math-list-item" id="faq-question-1613025737654">### How to list containers in Docker?

<div class="rank-math-answer ">You can use the below command to list the containers in Docker.  
<mark>docker container ls</mark>  
–  **docker**  – specifies the base command for docker  
– **container** – specifies the management command for docker container  
–  **ls** – specifies the command to list the containers  
To list all docker containers, you’ll use the <mark>-a</mark> flag after the <mark>ls</mark> command as shown in the below command.  
<mark>docker container ls -a</mark>

</div></div><div class="rank-math-list-item" id="faq-question-1613025987047">### How do I auto start docker container at system reboot?

<div class="rank-math-answer "><mark>docker update –restart \[option\] container</mark>  
– **docker**  – specifies the base command for docker   
– **update** – specifies the command to update Docker container  
– **–restart** – specifies the command to configure restart settings for a container  
– **\[option\]** – specifies the option command to mention the restart details {no, on-failure, unless-stopped, always}  
– **container** – specifies the name or ID of the container

</div></div><div class="rank-math-list-item" id="faq-question-1613027389755">### How to use Docker command without sudo?

<div class="rank-math-answer ">First, you’ll add the user to the Docker group using the below command.  
`<mark>sudo usermod -aG docker ${USER}</mark>`  
Next, you’ll execute the below command.  
`<mark>su - ${USER}</mark>`  
Finally, you’ll enter the password of the current user (if any).   
You can refer this [Docker tutorial](http://149.28.53.131/install-docker-on-ubuntu/#using_docker_command_without_sudo) to add a user to Docker group who is not the current user.

</div></div></div></div>