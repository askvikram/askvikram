---
id: 4632
title: 'How to Install Docker on Ubuntu 20.04 &#8211; Comprehensive Guide'
date: '2021-01-26T21:10:29+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4632'
permalink: /install-docker-on-ubuntu/
rank_math_seo_score:
    - '96'
rank_math_focus_keyword:
    - 'install docker on ubuntu,install docker,installing docker,ubuntu'
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
rank_math_primary_category:
    - '16'
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
rank_math_pillar_content:
    - 'on'
socialsnap_share_count_timestamp:
    - '2023-09-13 15:39:13'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '5'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"0343920eed1f7926900eb9cd4ccce0e6";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - aws
    - docker
    - installation
    - tutorials
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

[Docker ](https://www.docker.com/)is an open-source platform for developers and system administrators which creates a portable container for application development. Docker is used for building, testing, and deploying applications that can run virtually. It is similar to a [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine). Docker applications are fast, because instead of requiring dedicated server resources, it shares the kernel and other resources. It is quick and easy to configure.

Containers allow applications to run isolated from one another. It also bundles their own software, libraries, and configuration files. They can communicate with each other through well-defined channels. The use of Containers is becoming popular because they are flexible, lightweight, portable, loosely coupled, scalable, and more secure. Multiple containers can run on the same hardware.

In this tutorial, you’ll install Docker on Ubuntu 20.04 and execute some of the basic Docker commands.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="methods_to_install_docker_on_ubuntu"></span>Methods to Install Docker on Ubuntu<span class="ez-toc-section-end"></span>

In this step, you’ll go through different methods to install Docker on Ubuntu 20.04. Docker has two versions namely:

- Docker CE (Community Edition)

- Docker EE (Enterprise Edition)

In this tutorial, you’ll install Docker CE because Docker CE is more than enough to get started and build small scale applications.

Various methods to Install Docker on Ubuntu are: (**You can navigate to specific method by clicking the link**)

- [Using Default Ubuntu repository](#Default-Ubuntu-Repository)
- [Using Official Docker repository (Recommended)](#Official-Docker-repository)
- [Using a <mark>.deb</mark> package](#deb-package)
- [Using an automated script](#using-automated-scripts)

## <span class="ez-toc-section" id="installing_docker_using_default_ubuntu_repository"></span>Installing Docker Using Default Ubuntu Repository<span class="ez-toc-section-end"></span>

In this step, you’ll install Docker on Ubuntu using the default repository. Ubuntu Repositories contain highly tested and secure software that is easy to install and use. To know more about Ubuntu repositories visit this [Ubuntu Community page](https://help.ubuntu.com/community/Repositories/Ubuntu#:~:text=By%20default%20Ubuntu%20Software%20Center,the%20Edit%2C%20Software%20Sources%20menu.).

First, you’ll install Docker on Ubuntu, using the <mark>docker.io</mark> command in your terminal.

```
<pre class="wp-block-code">```
sudo apt install docker.io
```
```

You’ll get a prompt to enter (y/n). Press <mark>y</mark>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Preparing to unpack .../5-docker.io_<var>19.03.8</var>-0ubuntu1.20.04.2_amd64.deb ...
Unpacking docker.io (<var>19.03.8</var>-0ubuntu1.20.04.2) ...
Setting up docker.io (<var>19.03.8</var>-0ubuntu1.20.04.2) ...
...
```
```

Next, you’ll install the dependency packages using the below command in your terminal.

```
<pre class="wp-block-code">```
sudo snap install docker
```
```

- **sudo** – Keyword to run the command with sudo administrative privileges
- **snap** – compresses system configuration information into a [pax ](https://fileinfo.com/extension/pax#:~:text=Portable%20Archive%20Exchange%20(PAX)%20file,sv4crc%2C%20tar%2C%20and%20ustar.)file and transmit to a remote system.
- **install** – copy files and set attributes.
- **docker** – package name

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
docker <var>19.03.11</var> from Canonical✓ installed
```
```

Finally, verify that you’ve install Docker on Ubuntu, using the <mark>–version</mark> sub-command in your terminal.

```
<pre class="wp-block-code">```
docker --version
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Docker version <var>19.03.8</var>, build afacb8b7f0
```
```

You’ve installed Docker from Ubuntu Default repositories. The drawback of installing Docker from the default repository is that **you may not get the latest version of Docker**. As you can see Ubuntu repositories gives version <var>19.03.8</var> of Docker while the LST (Latest Stable Version) of Docker is <var>20.10.2</var> (at the time of writing).

In the next step, you’ll install Docker on Ubuntu using Docker Official repositories.

## <span class="ez-toc-section" id="installing_docker_using_official_docker_repositories_recommended"></span>Installing Docker Using Official Docker Repositories (Recommended)<span class="ez-toc-section-end"></span>

In this step, you’ll install the latest version of Docker from the Official Docker Repository. You’ll add a new package source and the [GPG key](https://help.ubuntu.com/community/GnuPrivacyGuardHowto) from Docker.

A GPG (GNU Privacy Guard), is a public key cryptography implementation. It helps in the secure transmission of information.

First, install a few packages that allows <mark>apt</mark> to use a repository over HTTPS, using the below command in terminal.

```
<pre class="wp-block-code">```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```
```

You’ll get a prompt to enter (y/n). Press <mark>y</mark>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Setting up gnupg-agent (2.2.19-3ubuntu2) ...
Setting up curl (7.68.0-1ubuntu2.4) ...
Setting up software-properties-common (0.98.9.3) ...
...
Running hooks in /etc/ca-certificates/update.d...
done.
```
```

Next, to ensure that the downloads are valid, you’ll add GPG key for Official Docker repository to your system, using the below command in your terminal.

```
<pre class="wp-block-code">```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
OK
```
```

Now, you’ve added the GPG key to your system.

**Optional:** You can verify by searching for the last 8 characters(<mark>0EBF CD88</mark>) of the fingerprint, using the below command. The fingerprint is a short version of the server’s public key. It is used for verification.

```
<pre class="wp-block-code">```
sudo apt-key fingerprint 0EBFCD88
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]

```
```

Now, You’ll have the key with the fingerprint<mark> 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88</mark>.

Next, you’ll **set up the stable Docker repository by adding it to the APT sources**, using the below command in your terminal.

To add the nightly or test repository, append nightly or test (or both) after stable in the below command. You can learn more about the Docker channels from the [Official Docker Documentation](https://docs.docker.com/engine/install/).

```
<pre class="wp-block-code">```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu <var>focal</var> stable"
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Reading package lists... Done
```
```

Next, update the package database with the Docker packages, using the below command in your terminal.

```
<pre class="wp-block-code">```
sudo apt update
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Reading package lists... Done
Building dependency tree
Reading state information... Done
```
```

**Optional:** You can ensure you are downloading Docker from Docker Repositories, by using the below command.

```
<pre class="wp-block-code">```
apt-cache policy docker-ce
```
```

- **apt-cache** – collects information of packages
- **policy** – shows which versions of a package apt knows
- **docker-ce** – package name

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
docker-ce:
  <var>Installed: (none)</var>
  Candidate: 5:<var>20.10.2~3-0~ubuntu-focal</var>
  Version table:
     5:<var>20.10.2~3-0~ubuntu-focal</var> 500
        500 https://download.docker.com/linux/ubuntu focal/stable amd64 Packages
        100 /var/lib/dpkg/status/var
```
```

**Installed: (none)** shows that <mark>docker-ce</mark> is not installed yet.

**Candidate: 5:<var>20.10.2~3-0~ubuntu-focal</var>** shows you are using Ubuntu 20.04 (focal).

In Version Table, you can see version *20.10.2* of Docker.

Now you’ll install Docker on Ubuntu, using the below <mark>install</mark> in your terminal.

```
<pre class="wp-block-code">```
sudo apt install docker-ce
```
```

You’ll get a prompt to enter (y/n). Press <mark>y</mark>.

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Setting up containerd.io (1.4.3-1) ...
Setting up docker-ce-cli (5:20.10.2~3-0~ubuntu-focal) ...
Setting up docker-ce (5:20.10.2~3-0~ubuntu-focal) ...
Setting up docker-ce-rootless-extras (5:20.10.2~3-0~ubuntu-focal) ...
...
```
```

You’ve installed Docker successfully.

To verify you can execute the below command in your terminal.

```
<pre class="wp-block-code">```
 docker --version
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Docker version <var>20.10.2</var>, build 2291f6
```
```

You’ve successfully **installed docker using Official Docker Repositories**. Please note that you may get a different version number (as <var>20.10.2</var> was the LTS at the time of writing).

In the next step, you’ll install docker on Ubuntu using <mark>.deb</mark> package.

## <span class="ez-toc-section" id="installing_docker_manually_from_a_package"></span>Installing Docker Manually From a Package<span class="ez-toc-section-end"></span>

In this step, you’ll install Docker on Ubuntu by downloading the <mark>.deb</mark> file from the index files of the specific version (In this case, <mark>focal </mark>– Ubuntu 20.04).

Deb file is a installation package format used by all Debian based distributions. The Ubuntu repositories contain thousands of deb packages that can be installed either from the Ubuntu Software Center or from the command line using the apt and apt-get utilities.

You’ve to download the <mark>.deb</mark> file every time when you want to upgrade the docker. This method is preferred, if you want to install a different version of Docker than the latest version.

First, you’ll go to `<a class="rank-math-link" href="https://download.docker.com/linux/ubuntu/dists/" rel="noreferrer noopener" target="_blank">Docker Ubuntu Distributions page</a>` and choose your Ubuntu (<mark>focal </mark>– 20.04) version.

<div class="wp-block-image"><figure class="aligncenter size-large">![install docker on ubuntu step 1](http://149.28.53.131/wp-content/uploads/2021/01/1-5.png)<figcaption>Figure 1 Install docker on ubuntu from .deb package – Step 1</figcaption></figure></div>Next, you’ll click pool and then stable.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/3-3.png)<figcaption>Figure 2 Install Docker on ubuntu from .deb package – Step 2</figcaption></figure></div><div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/4-1.png)<figcaption>Figure 3 Install Docker on ubuntu from .deb package – Step 3</figcaption></figure></div>Next, you’ll choose `<mark>amd64</mark>` or `<mark>arm64</mark>` based on your processor.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/5-2.png)<figcaption>Figure 4 Install Docker on ubuntu from .deb package – Step 4</figcaption></figure></div>Next, you’ll download the `<mark>.deb</mark>` file for the version of Docker(<mark>docker-ce</mark>) you want to install.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/2-1.png)<figcaption>Figure 5 Install Docker on ubuntu from .deb package – Step 5</figcaption></figure></div>Finally, you’ll install Docker from the path you’ve downloaded <mark>.deb</mark> package, using the below command in your terminal.

Ensure you are using the path to the <mark>.deb</mark> package in your system.

```
<pre class="wp-block-code">```
sudo dpkg -i <var>/path/to/downloaded_packag</var>e.deb
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```

...
Setting up docker-ce (5:20.10.2~3-0~ubuntu-focal) ...
...

```
```

You’ve successfully installed Docker on Ubuntu using <mark>.deb</mark> package manually.

To verify the installation of docker, execute the below command in your terminal.

```
<pre class="wp-block-code">```
docker --version
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Docker version <var>20.10.2</var>, build 2291f6
```
```

In the next step, you’ll learn how to install Docker on Ubuntu using the scripts.

## <span class="ez-toc-section" id="installing_docker_on_ubuntu_using_the_automated_scripts"></span>Installing Docker on Ubuntu Using the Automated Scripts<span class="ez-toc-section-end"></span>

In this step, you’ll install Docker on Ubuntu using the automated scripts. **Docker provides convenience scripts for installing edge (latest) and test versions of the Docker engine**. These scripts helps you to install Docker and test it without setting any configurations.

It is not recommended to use this version in the Production Environment, because it may not be a stable one. For more details, read the instructions from the [Official Docker Documentation](https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script).

### Installing Docker Engine – Community (latest Version)

First, you’ll install Docker on Ubuntu (edge version) with the help of the [Get Docker](https:/get.docker.com) script, using the below command in your terminal.

```
<pre class="wp-block-code">```
curl -fsSL https://get.docker.com -o docker.sh
```
```

Script docker.sh is downloaded.

Next, execute the below command in your terminal to execute the script. It’ll install Docker.

```
<pre class="wp-block-code">```
sudo sh docker.sh
```
```

You’ve installed Docker on Ubuntu using the convenient scripts.

### Installing Docker – Test Version

You can install the test version of Docker Engine from [Test Docker](https://test.docker.com), using the below command in your terminal.

```
<pre class="wp-block-code">```
curl -fsSL <a class="rank-math-link" href="https://test.docker.com">https://test.docker.com</a> -o docker.sh
```
```

Script docker.sh for test version is downloaded.

Next, execute the below command in your terminal to execute the script. It’ll install test version of Docker.

```
<pre class="wp-block-code">```
sudo sh docker.sh
```
```

You’ve installed Docker on Ubuntu using the convenience scripts.

In the next step, you’ll test the installation of Docker by checking whether it’s running as a service.

## <span class="ez-toc-section" id="testing_docker_installation"></span>Testing Docker Installation<span class="ez-toc-section-end"></span>

In this step, you’ll test whether the install Docker on Ubuntu is successfull and running as a service properly.

When you install Docker, the daemon is started and the process is enabled on boot automatically.

You can check it by using the below command.

```
<pre class="wp-block-code">```
sudo systemctl status docker
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset>
     Active: <var>active (running)</var> since Mon 2021-01-25 11:55:41 UTC; 2h 11min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 17435 (dockerd)
      Tasks: 8
     Memory: 58.8M
     CGroup: /system.slice/docker.service
             └─17435 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/con>
```
```

You will see that the docker is in running state (active) currently.

In the next step, you’ll setup docker command for non root user.

## <span class="ez-toc-section" id="using_docker_command_without_sudo"></span>Using Docker Command Without Sudo<span class="ez-toc-section-end"></span>

In this step, you’ll configure the user to access <mark>docker</mark> command without <mark>sudo</mark>.

You can run <mark>docker </mark>command with <mark>sudo </mark>or as a user available in the Docker Group.

If you try running <mark>docker </mark>without <mark>sudo </mark>or the user not available in the Docker group, you’ll see the below output.

```
<pre class="wp-block-code config">```
docker: Cannot connect to the Docker daemon. Is the docker daemon running on this host?.
See 'docker run --help'.
```
```

To add current user of the system to the Docker group, you can execute the below command in your terminal.

```
<pre class="wp-block-code">```
sudo usermod -aG docker ${USER}
```
```

Next, you can execute the below command in your terminal.

```
<pre class="wp-block-code">```
su - ${USER}
```
```

Next, you’ll enter the password for <mark>USER</mark>.

```
<pre class="wp-block-code config">```
Password:

```
```

You can confirm that the <mark>USER</mark> is added to Docker group using the id command. *<mark>id</mark>* is a *command*-line utility that prints group *IDs* of the current user.

```
<pre class="wp-block-code">```
id -nG
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
askvikram docker
```
```

- **askvikram** – Current user name
- **docker** – Docker Group name

You’ve added the current user to the Docker group successfully.

Finally, to add another user to the Docker group, execute the below command.

```
<pre class="wp-block-code">```
sudo usermod -aG docker <var>username</var>
```
```

- **sudo** – Keyword to run the command with sudo administrative privileges
- **usermod** – keyword to modify the user properties
- **-aG** – Option to add Group
- **docker** – Docker Group name
- **username** – Username to be added to the Docker Group

In the next step, you’ll work with some of the basic commands of Docker.

## <span class="ez-toc-section" id="exploring_docker_command"></span>Exploring Docker Command<span class="ez-toc-section-end"></span>

In this step, you’ll find out what is a <mark>docker</mark> command, docker image, docker hub and execute few commands using <mark>docker-cli</mark>.

You can avoid prefixing every command with sudo if you have gone through the [previous step](#Using-Docker-Command-Without-Sudo).

```
<pre class="wp-block-code">```
sudo docker [option] [management command] [command]
```
```

- **docker** – specifies docker command
- **\[option\]** – specifies the optional command for docker
- **\[management command\]** – specifies command for managing docker
- **\[command\]** – actual docker command

### Listing the Available Docker Commands

You can view the available commands in docker, using the below command in your terminal.

```
<pre class="wp-block-code">```
sudo docker
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default
                           "/home/askvikram/.docker")
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
                           "/home/askvikram/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default
                           "/home/askvikram/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default
                           "/home/askvikram/.docker/key.pem")
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
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
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

Run 'docker COMMAND --help' for more information on a command.

To get more help with docker, check out our guides at https://docs.docker.com/go/guides/

```
```

These are the commands you can use in docker. You can refer what each command does by downloading this [Official Docker Cheat-sheet](https://www.docker.com/sites/default/files/d8/2019-09/docker-cheat-sheet.pdf).

### Knowing System Information for Docker 

You can view the system wide information of Docker using the below command in your terminal.

```
<pre class="wp-block-code">```
sudo docker info
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
 Containers: 1
  Running: 0
  Paused: 0
  Stopped: 0
...
```
```

You’ll see warnings, errors, Client and Server information of Docker.

### Running a Docker Image

You’ll get into some of the basic commands of Docker using Docker image.

**A Docker image is a read-only template that contains a set of instructions for creating a container that can run on the Docker platform**. It provides a convenient way to package up applications and preconfigured server environments, which you can use for your own private use or share publicly with other Docker users. You can build a Docker container from Docker image.

Docker Hub is a service provided by Docker for finding and sharing Docker images. To Know more about the Docker hub, visit the [Official Docker Documentation](https://docs.docker.com/docker-hub/).

You can use the below command to download a test image and run it in a container.

**What happens when you run the below command?**

The command first searches locally for any Docker image named <mark>hello-world</mark>. If it is not available locally, then it searches in the docker hub (Default Repository) for the <mark>hello-world</mark> docker image and downloads it.

After the image is downloaded, Docker creates a container and the application within the container is executed.

```
<pre class="wp-block-code">```
sudo docker run hello-world
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete
Digest: sha256:31b9c7d48790f0d8c50ab433d9c3b7e17666d6993084c002c2ff1ca09b96391d
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```
```

Now, you’ve successfully executed a docker image downloaded from Docker Hub.

### Listing Local Docker Images

You can list the locally available Docker images, using the <mark>docker images</mark> command in your terminal.

```
<pre class="wp-block-code">```
sudo docker images
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
REPOSITORY    TAG       IMAGE ID       CREATED         SIZE
hello-world   latest    bf756fb1ae65   12 months ago   13.3kB
```
```

You can see <mark>hello-world</mark> Docker image downloaded in the[ previous step](#testing-docker-image), is available locally in your system.

### Searching Docker Images in Docker Hub

You can search for any Docker image using the <mark>docker search</mark> command.

```
<pre class="wp-block-code">```
sudo docker search <var>image_name</var>
```
```

- **docker** – specifies docker related command
- **search** – used to search for Docker images in Docker Hub
- **image\_name** – Docker image name to be searched in Docker Hub

The above command gives you a list of Docker images from the Docker hub.

For example, you can consider the image\_name as ‘django’.

```
<pre class="wp-block-code">```
sudo docker search django
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
NAME                                  DESCRIPTION                                     STARS    OFFICIAL   AUTOMATED
django                                Django is a free web application framework, …   1040      [OK]
dockerfiles/django-uwsgi-nginx        Dockerfile and configuration files to build …   187                  [OK]
camandel/django-wiki                  wiki engine based on django framework           33                   [OK]
alang/django                          This image can be used as a starting point t…   29                   [OK]
micropyramid/django-crm               Opensourse CRM developed on django framework…   19                   [OK]
...
```
```

All the available Docker images with the name <mark>Django</mark> are listed from the Docker Hub.

<mark>OK</mark> in the <mark>OFFICIAL</mark> Column indicates that Docker image is supported and built by the company behind the project.

### Pulling a Docker Image From Docker Hub

In this section, you’ll Pull the Docker image from Docker Hub and execute some of the basic commands. You can notice that you’ve already pulled a image from Docker in one of the previous steps ([Running Docker Image](#testing-docker-image)) using the <mark>run</mark> command.

You can pull a Docker image using the <mark>pull</mark> command as shown below.

```
<pre class="wp-block-code">```
sudo docker pull django
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Using default tag: latest
latest: Pulling from library/django
75a822cd7888: Pull complete
e4665cede9d1: Pull complete
202a45aa091c: Pull complete
7799136eb561: Pull complete
7a7f9ca3fd40: Pull complete
412f2d081014: Pull complete
Digest: sha256:5bfd3f442952463f5bc97188b7f43cfcd6c2f631a017ee2a6fca3cb8992501e8
Status: Downloaded newer image for django:latest
docker.io/library/django:latest
```
```

You’ve successfully pulled a Docker image from Docker hub using the <mark>pull</mark> command.

In the next step, you’ll learn how to uninstall docker.

## <span class="ez-toc-section" id="uninstalling_docker"></span>Uninstalling Docker<span class="ez-toc-section-end"></span>

In this step, you’ll uninstall docker assuming you’ve install docker on ubuntu earlier.

First, you’ll uninstall any versions of Docker that you have installed, using the below command in your terminal.

```
<pre class="wp-block-code">```
sudo apt-get remove docker docker-engine docker.io
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
...
Removing docker.io (19.03.8-0ubuntu1.20.04.2) 
...
```
```

You can see that docker version <var>19.03.8</var> is removed.

Finally, you can remove images, containers, volumes, or customized configuration files on your host, using the below command.

```
<pre class="wp-block-code">```
sudo rm -rf /var/lib/docker
```
```

You’ve removed all your docker related files from your system.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you’ve successfully installed Docker on Ubuntu, executed some of the basic commands in docker and uninstalled docker and its files.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

As a next step, you can create a Docker hub account and push your Docker images to the Docker Hub.

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1611652060781">### 1. How is Docker different from virtual Machine?

<div class="rank-math-answer ">Docker is container based technology and containers are just user space of the operating system. At the low level, a container is just a set of processes that are isolated from the rest of the system. The containers shares the host OS kernel.  
A Virtual Machine, on the other hand, is not based on container technology. They are made up of user space plus kernel space of an operating system. Under VMs, server hardware is virtualized. Each VM has Operating system (OS) &amp; apps. It shares hardware resource from the host. ([Read more](https://devopscon.io/blog/docker/docker-vs-virtual-machine-where-are-the-differences/#:~:text=Docker%20is%20container%20based%20technology,space%20of%20the%20operating%20system.&text=A%20Virtual%20Machine%2C%20on%20the,VMs%2C%20server%20hardware%20is%20virtualized.))

</div></div><div class="rank-math-list-item" id="faq-question-1611655806367">### 2. How do I pass Environment variables to Docker containers?

<div class="rank-math-answer ">You an pass a environment variable with the help of <mark>-e</mark> flag,using the below command.  
`<mark>docker run -e host='<variable_name>' <image_name></mark>`  
You an pass as many as environment variables as a file with the help of <mark>-env</mark> flag,using the below command.  
`<mark>docker run --env VAR1=value1 --env VAR2=value2 ubuntu env | grep <br></br>VAR VAR1=value1 <br></br>VAR2=value2 </mark>`   
([Read more](https://docs.docker.com/engine/reference/commandline/run/#set-environment-variables--e---env---env-file))

</div></div><div class="rank-math-list-item" id="faq-question-1611656253196">### 3. How to fix Got permission denied issue in ubuntu docker?

<div class="rank-math-answer ">First, you’ll create a docker group if it does not exist already using the below command.  
`<mark>sudo groupadd docker</mark>`  
Next, you’ll add the user to the docker group using the below command.  
`<mark>sudo usermod -aG docker $USER</mark>`  
Next, Log out from your system and log in.  
Finally, you’ll run the docker command without root using the below command.  
`<mark>docker run hello-world</mark>`.  
If the problem still persist, you’ve to reboot your system and try again. [(Read more](https://stackoverflow.com/questions/48957195/how-to-fix-docker-got-permission-denied-issue))

</div></div><div class="rank-math-list-item" id="faq-question-1611657364092">### 4. Docker error : No space left on the device

<div class="rank-math-answer ">You can try executing the below command. The following command will remove   
`- all stopped containers `  
`- all networks not used by at least one container `  
`- all dangling images `  
`- all dangling build cache`  
`<mark>docker system prune</mark>`  
([Read more](https://stackoverflow.com/questions/30604846/docker-error-no-space-left-on-device))

</div></div><div class="rank-math-list-item" id="faq-question-1611657543266">### 5. ‘Username’ is not in the sudoers file. This incident will be reported

<div class="rank-math-answer ">First, open the sudoers file using the below command.  
`<mark>sudo nano /etc/sudoers</mark>`  
Then, add the following line below the admin syntax replacing user\_name with your system user.  
`user_name ALL=(ALL) ALL`  
([Read more](https://stackoverflow.com/questions/47806576/linux-username-is-not-in-the-sudoers-file-this-incident-will-be-reported))

</div></div><div class="rank-math-list-item" id="faq-question-1611658193325">### 6. docker.io : Depends: containerd (&gt;= 1.2.6-0ubuntu1~)

<div class="rank-math-answer ">There are 2 different packages, namely  
– `containerd`   
– `containerd.io`   
You can execute the below command and you should see both packages.  
<mark>`dpkg -l containerd*` </mark>  
If any of the package is not found, you can install using the below command.  
<mark>`sudo apt install <package_name>`.</mark>

</div></div></div></div>