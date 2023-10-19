---
id: 4196
title: 'How to Install Node.js on Ubuntu 20.04 &#8211; Made Easy'
date: '2021-01-05T00:39:29+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4196'
permalink: /install-nodejs-on-ubuntu/
rank_math_seo_score:
    - '82'
rank_math_focus_keyword:
    - 'Install Node.js on Ubuntu'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
ss_social_share_disable:
    - ''
rank_math_internal_links_processed:
    - '1'
rank_math_pillar_content:
    - 'off'
rank_math_description:
    - 'In this article, you''ll download and install Node.js on Ubuntu 20.04 in multiple ways, remove Node.js and test it by running a Node.js web-server. Node.js is an open-source, cross-platform, JavaScript runtime.'
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
socialsnap_share_count_timestamp:
    - '2023-09-08 16:38:02'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '11'
categories:
    - how-to
tags:
    - installation
    - nodejs
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

[Node.js ](https://nodejs.org/en/)is an open-source, cross-platform, JavaScript runtime environment for general-purpose programming. It is lightweight and built based on Chrome’s V8 JavaScript engine. **It is used to build fast and scale-able web applications on the server-side.** It is one of the most widely used web technologies.

[NPM ](https://www.npmjs.com/)(**N**ode.js **P**ackage **M**anager) is an open-source library of Node.js packages. It is used to install and manage package dependencies.

In this article, you’ll download and install Node.js on Ubuntu 20.04 using Ubuntu repository(APT), Node source repository and NVM, remove Node.js and test it by running a Node.js **[web-server](https://en.wikipedia.org/wiki/Web_server).**

## <span class="ez-toc-section" id="methods_to_install_nodejs_on_ubuntu"></span>Methods to Install Node.js on Ubuntu<span class="ez-toc-section-end"></span>

- **[Official Ubuntu repositories](#ubuntu_official_repository)** – It will **not provide you** the **LTS** (**L**atest **S**table **V**ersion). Instead, **you get the version that is tested and verified by Ubuntu**. (Currently `<strong>v10.23.0</strong>`)
- **[Node Source repository](#using-node-source) –** You can choose Node Source if you want a *different version* than the one offered by the Ubuntu repository. Currently, Node Source supports Node.js **v15.x, v14.x, v13.x, v12.x,** and` <strong>v10.x</strong>`.
- **[Node Version Manager](#using-nvm)** – You can install multiple Node.js versions on the same machine. **If you are a Node.js developer, then this is the preferred way to install Node.js on Ubuntu.**

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="using_ubuntu%e2%80%99s_official_repository"></span>Using Ubuntu’s Official Repository<span class="ez-toc-section-end"></span>

Ubuntu 20.04 contains an earlier stable version of Node.js in its repositories. At the time of writing, the version in the repositories is <mark>***v10.23.0.***</mark> You’ll find an early version because the Ubuntu team will test the versions before hosting them in their repository.

To <mark>install</mark> Node.js, execute the following command.

```
<pre class="wp-block-code">```
sudo apt install nodejs
```
```

You’ll get a stable version of Node.js installed from the Ubuntu repository. This is enough for new developers to work on their skills. Still, you might need NPM to install other packages to work with Node.js.

To install <mark>npm</mark>, execute the following command.

```
<pre class="wp-block-code">```
sudo apt install npm
```
```

You’ve successfully installed Node.js and NPM.

To verify the installation of Node.js, execute the following command.

```
<pre class="wp-block-code">```
nodejs -v
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code">```
v10.23.0
```
```

To verify the installation of NPM, execute the following command.

```
<pre class="wp-block-code">```
npm -v
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
6.14.8
```
```

You’re all set to work on the Node.js stable version of Ubuntu.

But in most cases, you might need the latest version to get the support for the newest packages. In the next section, you’ll install the Latest Stable Version of Node.js.

## <span class="ez-toc-section" id="using_node_source_repository"></span>Using Node Source Repository<span class="ez-toc-section-end"></span>

Node source repository contains the latest version always. To learn more about the Node Source, visit their [official page](https://github.com/nodesource/distributions/blob/master/README.md).

In order to install the latest stable version of Node.js, you can use the PPA (**P**ersonal **P**ackage **A**rchive) which is maintained by **NodeSource**. This will hold *more up-to-date versions of Node.js*. You can choose between Node.js <mark>v10.x </mark>(*LTS version*), Node.js <mark>v12.x </mark>(*Active LTS version*), Node.js v15.x (*Current version*), and also any other version from the [official Github page](https://github.com/nodesource/distributions).

First, install curl (*if you already don’t have*) using the below command.

```
<pre class="wp-block-code">```
sudo apt install curl
```
```

Next, install the PPA to get access to its contents. From your home directory, use `<mark>curl</mark>` to retrieve the installation script for your preferred version. If you prefer another version, replace `<var>15.x</var>` with your preferred version string.

```
<pre class="wp-block-code">```
curl -sL https://deb.nodesource.com/setup_<var>15.x</var> -o nodesource_file.sh
```
```

You can read the content of the file using an editor of your choice, you will use nano in this tutorial.

If you would like to view the contents, use the below command. ( <mark>nano</mark> is used to view the content, Press *CTRL + X* to *exit* the <mark>nano</mark>).

```
<pre class="wp-block-code">```
nano nodesource_setup.sh
```
```

Now run the script using the below command. It’ll start the node source setup.

```
<pre class="wp-block-code">```
sudo bash nodesource_setup.sh
```
```

The PPA will be added to your configuration and your local package cache will be updated automatically.

Next, install Node.js and NPM using the below command.

```
<pre class="wp-block-code">```
sudo apt install nodejs
```
```

NodeJS is installed.

To check the installation, use the below command.

```
<pre class="wp-block-code">```
node -v
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
10.23.0
```
```

You’ve successfully setup Node.js and NPM using Nodesource repository.

In the next step, you’ll tackle how to manage multiple versions and multiple instances.

## <span class="ez-toc-section" id="using_nvm"></span>Using NVM<span class="ez-toc-section-end"></span>

In this step, you’ll find yet another way (preferred in most cases) to install Node.js on Ubuntu 20.04.

You’ll use NVM which stands for **N**ode **V**ersion **M**anager. NVM is a practical tool for managing multiple Node.js versions.

This helps in creating **multiple versions** of the node running in the same system which is made possible due to the fact that nvm works at the level of the *independent directory*.

You can access the newest versions of Node.js at the same time manage previous releases with the help of NVM.

The versions of Node.js that you manage with <mark>apt</mark> are distinct from the versions you manage with NVM.

First, install <mark>curl</mark>, if you have not installed it already, using the below command. (Hopefully, You should have this installed, if you have not skipped the previous section).

```
<pre class="wp-block-code">```
sudo apt install curl
```
```

Next, download the `nvm` installation script from the [official GitHub page](https://github.com/creationix/nvm) using the <mark>curl</mark>.

The version number may differ from the one highlighted here

```
<pre class="wp-block-code">```
curl -sL https://raw.githubusercontent.com/nvm-sh/nvm/<var>v0.37.2</var>/install.sh -o nvm.sh
```
```

You can view the content in the script file using the following command. You can prefer any editor of your choice.

```
<pre class="wp-block-code">```
nano nvm.sh
```
```

Next, run the command below to execute the script file.

```
<pre class="wp-block-code">```
bash nvm.sh
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code">```
=> Compressing and cleaning up git repository

=> Appending nvm source string to /home/ubuntu/.bashrc
=> Appending bash_completion source string to /home/ubuntu/.bashrc
=> <strong>Close and reopen your terminal to start using nvm or run the following to use it now:</strong>
```
```

You can either log out and log in again, reopen the terminal (as mentioned in the above output), or you can use the below command to save the changes to the session.

```
<pre class="wp-block-code">```
source ~/.profile
```
```

Now that you have successfully installed NVM, you can **install multiple versions of Node.js using NVM**.

To look into the versions of Node.js that NVM provides, execute the below command.

```
<pre class="wp-block-code">```
nvm ls-remote
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
       v14.9.0
       v14.10.0
       v14.10.1
       v14.11.0
       v14.12.0
       v14.13.0
       v14.13.1
       v14.14.0
       v14.15.0   (LTS: Fermium)
       v14.15.1   (LTS: Fermium)
       v14.15.2   (LTS: Fermium)
       v14.15.3   (Latest LTS: Fermium)
        v15.0.0
        v15.0.1
        v15.1.0
        v15.2.0
        v15.2.1
        v15.3.0
        v15.4.0
        v15.5.0
```
```

You can install Node.js by specifying the version number from the above list using the below command.

```
<pre class="wp-block-code">```
nvm install 14.15.3
```
```

Now, you have installed a version using NVM, you can go ahead and use the version using the below command.

```
<pre class="wp-block-code">```
nvm use 14.15.3
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Now using node v14.15.3 (npm v6.14.9)
```
```

Since there are so many versions available, it is normal that you may forget which version is the current version.

You can find the current version using the below command.

```
<pre class="wp-block-code">```
node -v
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
v14.15.3
```
```

You can identify the versions that are installed in your system using the below command.

```
<pre class="wp-block-code">```
nvm ls
```
```

You can define a particular version as default version using the <mark>alias </mark>command as shown below.

```
<pre class="wp-block-code">```
nvm alias default 14.15.3
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
default -> 14.15.3 (-> v14.15.3)
```
```

Each and every version of Node.js in NVM will have a separate npm to track the packages installed for the particular version.

To learn more about the nvm, you can use the below command.

```
<pre class="wp-block-code">```
nvm help
```
```

It is advisable to use the LTS for professional purpose.

You’ve successfully completed the installation of Node.js using nvm. In the next step, you’ll remove a particular version or all versions of Node.js.

## <span class="ez-toc-section" id="removing_nodejs_optional"></span>Removing Node.js \[Optional\]<span class="ez-toc-section-end"></span>

In this step, you’ll remove Node.js version using the <mark>apt</mark> command. Removing unnecessary files are as important as installing it.

The following command is used to remove the stable version installed from Ubuntu repository. This command saves the configuration files that are downloaded during installation.

```
<pre class="wp-block-code">```
sudo apt remove nodejs
```
```

In order to delete Node.js *along with configuration files* execute the below command.

```
<pre class="wp-block-code">```
sudo apt purge nodejs
```
```

In order to *delete the additional files* that are installed along with node.js installation, execute the below command.

```
<pre class="wp-block-code">```
sudo apt autoremove
```
```

To *remove the current active version* of Node.js.

First, use the below command to check the current active version.

```
<pre class="wp-block-code">```
nvm current
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
v14.15.3
```
```

Next, remove the version based on its version number, if it is **not the <mark>current</mark> active version**, using the below command.

```
<pre class="wp-block-code">```
nvm uninstall <var>node_version</var>
```
```

If the version you have to <mark>remove</mark> is the <mark>current</mark> version. Then, <mark>deactivate</mark> the version using the below command.

```
<pre class="wp-block-code">```
nvm deactivate
```
```

Now you can remove the version using the <mark>remove</mark> command followed by the version number. This command removes the files associated with this version. Note that the *cache files are still not removed* as these can be used when the version is reinstalled.

## <span class="ez-toc-section" id="creating_web_server_optional"></span>Creating Web Server \[Optional\]<span class="ez-toc-section-end"></span>

This is an **optional** step. If you want to **test your node.js installation**, you’ll create a web server with “*<var>Ask Vikram!</var>*” text.

First, create a file **server.js** using the below command.

```
<pre class="wp-block-code">```
nano <var>server.js</var>
```
```

You will see <mark>nano</mark> editor has opened. Type the below code into the file.

```
<pre class="wp-block-code config">```
var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('<var>Ask Vikram</var>!\n');
}).listen(3000, "127.0.0.1");
console.log('Server running at http://127.0.0.1:3000/');
```
```

After typing, Press*<mark> CTRL + X</mark>* to exit. Press *<mark>Y</mark>* to save the file.

Now type the following command into the terminal to run the web-server.

```
<pre class="wp-block-code">```
node <var>server.js</var>
```
```

You will see the following output which confirms that the *server is running* and *Node.js is installed successfully*. You can open the following link in your browser to see the output.

Output

```
<pre class="wp-block-code config">```
Server running at http://127.0.0.1:3000/
```
```

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this article, you have **installed Node.js** using the Ubuntu repository, NodeSource repository, and NVM. You have also **removed Node.js** versions and run a simple server using Node.js.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

You’ve installed Node JS. If you would like to install a database, you shall use the guide, [How to install PostgreSQL on Ubuntu](http://149.28.53.131/install-postgresql-on-ubuntu/).

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)