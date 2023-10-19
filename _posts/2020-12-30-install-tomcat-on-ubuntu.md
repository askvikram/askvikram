---
id: 4127
title: 'How to Install Tomcat on Ubuntu 20.04[Simple Way]?'
date: '2020-12-30T12:15:54+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4127'
permalink: /install-tomcat-on-ubuntu/
rank_math_seo_score:
    - '83'
rank_math_focus_keyword:
    - 'install tomcat on ubuntu'
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
rank_math_primary_category:
    - '16'
socialsnap_share_count_timestamp:
    - '2023-09-11 02:32:45'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '13'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"013de335f59e170a4349bd0028bde1d7";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - tomcat
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

[Apache Tomcat](http://tomcat.apache.org/) is an open source [web server](https://en.wikipedia.org/wiki/Web_server) and a Java servlet container used to serve the client requests. Its is highly robust, light weight and easy to use web server. It also consists of many addons.

In this tutorial, you’ll install tomcat on Ubuntu 20.04, Setup firewall and test if the server is serving client requests correctly.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="step_1_%e2%80%93_installing_open_jdk"></span>Step 1 – Installing Open JDK<span class="ez-toc-section-end"></span>

In this step, you’ll install OpenJDK on Ubuntu. Since Tomcat is an open source implementation of Java, installing of the Open JDK is must for tomcat to work.

Use the apt install command to install OpenJDK as below.

```
<pre class="wp-block-code">```
sudo apt install <var>default-jdk</var>
```
```

- **sudo** – To run the command with the administrative privilege
- **apt install** – To install an apt package from the repository
- **default-jdk** – To install the Default JDK. Using this default keyword will ensure, you install the latest stable version at the time of the installation. If you want to install a specific version, you can use the specific version in the highlighted place. e.g. <mark>openjdk-11-jdk</mark> to install openjdk version 11

You’ve installed the OpenJDK. You can validate using the <mark>java -version</mark> command. You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
openjdk version "11.0.9.1" 2020-11-04
OpenJDK Runtime Environment (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04)
OpenJDK 64-Bit Server VM (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04, mixed mode, sharing)
```
```

Java version 11.0.9.1 is installed successfully. Now, you’ll proceed to install Tomcat on Ubuntu.

## <span class="ez-toc-section" id="step_2_%e2%80%93_installing_tomcat_on_ubuntu"></span>Step 2 – Installing Tomcat on Ubuntu<span class="ez-toc-section-end"></span>

In this section, you’ll install Tomcat On Ubuntu 20.04.

You can check all the Tomcat packages available in the apt repository using the command <mark>apt-cache search</mark>. You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
resource-agents - Cluster Resource Agents
libapache-mod-jk-doc - Documentation of libapache2-mod-jk package
libapache2-mod-jk - Apache 2 connector for the Tomcat Java servlet engine
libjnlp-servlet-java - simple and convenient packaging format for JNLP applications
liblogback-java - flexible logging library for Java
liblogback-java-doc - flexible logging library for Java - documentation
libnetty-tcnative-java - Tomcat native fork for Netty
libnetty-tcnative-jni - Tomcat native fork for Netty (JNI library)
libsolr-java - Enterprise search server based on Lucene - Java libraries
libspring-instrument-java - modular Java/J2EE application framework - Instrumentation
libtcnative-1 - Tomcat native library using the Apache Portable Runtime
libtomcat9-embed-java - Apache Tomcat 9 - Servlet and JSP engine -- embed libraries
libtomcat9-java - Apache Tomcat 9 - Servlet and JSP engine -- core libraries
libtomcatjss-java - JSSE implementation using JSS for Tomcat
nagios-plugins-contrib - Plugins for nagios compatible monitoring systems
python3-ajpy - Python module to craft AJP requests
solr-common - Enterprise search server based on Lucene3 - common files
solr-jetty - Enterprise search server based on Lucene3 - Jetty integration
solr-tomcat - Enterprise search server based on Lucene3 - Tomcat integration
<var>tomcat9 - Apache Tomcat 9 - Servlet and JSP engine</var>
<var>tomcat9-admin - Apache Tomcat 9 - Servlet and JSP engine -- admin web applications</var>
tomcat9-common - Apache Tomcat 9 - Servlet and JSP engine -- common files
tomcat9-docs - Apache Tomcat 9 - Servlet and JSP engine -- documentation
tomcat9-examples - Apache Tomcat 9 - Servlet and JSP engine -- example web applications
tomcat9-user - Apache Tomcat 9 - Servlet and JSP engine -- tools to create user instanc                                                                                                  es
yasat - simple stupid audit tool

```
```

You need to install the highlighted packages. <mark>tomcat9</mark> and <mark>tomcat9-admin</mark> for administrating the tomcat setup.

Use the below command to install tomcat9 and tomcat9-admin.

```
<pre class="wp-block-code">```
sudo apt install tomcat9 tomcat9-admin
```
```

It’ll install the tomcat9 and its necessary dependencies. After installation, Tomcat9 will be automatically started and running. You’ll verify it in the next step.

## <span class="ez-toc-section" id="step_3_%e2%80%93_verifying_tomcat_installation"></span>Step 3 – Verifying Tomcat Installation<span class="ez-toc-section-end"></span>

In this section, You’ll check the status of the Tomcat9 if its running properly.

Tomcat9 will be running as a system service. **You can use <mark>systemctl status</mark> to check the status of the system service**.

use the below command to check the status of the Tomcat9 on Ubuntu.

```
<pre class="wp-block-code">```
 sudo systemctl status tomcat9
```
```

If tomcat is running properly, you’ll see the below output.

Output

```
<pre class="wp-block-code config">```
 tomcat9.service - Apache Tomcat 9 Web Application Server
     Loaded: loaded (/lib/systemd/system/tomcat9.service; enabled; vendor preset: enabled)
     Active: active <var>(running)</var> since Wed 2020-12-30 05:22:22 UTC; 19s ago
       Docs: https://tomcat.apache.org/tomcat-9.0-doc/index.html
   Main PID: 193547 (java)
      Tasks: 29 (limit: 1164)
     Memory: 93.7M
     CGroup: /system.slice/tomcat9.service
             └─193547 /usr/lib/jvm/default-java/bin/java -Djava.util.logging.config.file=/var/lib/tomcat9/conf/logging.properties -Djava.util.logging.manager=org.apache.juli.ClassLoaderL>

Dec 30 05:22:28 ip-172-31-47-246 tomcat9[193547]: Deployment of deployment descriptor [/etc/tomcat9/Catalina/localhost/manager.xml] has finished in [2,137] ms
Dec 30 05:22:28 ip-172-31-47-246 tomcat9[193547]: Deploying deployment descriptor [/etc/tomcat9/Catalina/localhost/host-manager.xml]
Dec 30 05:22:28 ip-172-31-47-246 tomcat9[193547]: The path attribute with value [/host-manager] in deployment descriptor [/etc/tomcat9/Catalina/localhost/host-manager.xml] has been ignor>
Dec 30 05:22:29 ip-172-31-47-246 tomcat9[193547]: At least one JAR was scanned for TLDs yet contained no TLDs. Enable debug logging for this logger for a complete list of JARs that were >
Dec 30 05:22:29 ip-172-31-47-246 tomcat9[193547]: Deployment of deployment descriptor [/etc/tomcat9/Catalina/localhost/host-manager.xml] has finished in [1,125] ms
Dec 30 05:22:29 ip-172-31-47-246 tomcat9[193547]: Deploying web application directory [/var/lib/tomcat9/webapps/ROOT]
Dec 30 05:22:30 ip-172-31-47-246 tomcat9[193547]: At least one JAR was scanned for TLDs yet contained no TLDs. Enable debug logging for this logger for a complete list of JARs that were >
Dec 30 05:22:30 ip-172-31-47-246 tomcat9[193547]: Deployment of web application directory [/var/lib/tomcat9/webapps/ROOT] has finished in [1,117] ms
Dec 30 05:22:30 ip-172-31-47-246 tomcat9[193547]: Starting ProtocolHandler ["http-nio-8080"]
Dec 30 05:22:30 ip-172-31-47-246 tomcat9[193547]: Server startup in [4,569] milliseconds
lines 1-20/20 (END)

```
```

**Status running shows, Tomcat9 is installed successfully and running.** Now, you’ll enable tomcat to start automatically.

## <span class="ez-toc-section" id="step_4_%e2%80%93_enabling_tomcat_service"></span>Step 4 – Enabling Tomcat Service<span class="ez-toc-section-end"></span>

In this section, you’ll enable Tomcat to start automatically after the system reboot. It is recommended to start the tomcat automatically after system reboot. Otherwise, websites hosted with the tomcat may not work after the system reboot.

Tomcat9 is a system service and you can enable it using the command <mark>systemctl enable</mark> command to start automatically after the reboot.

Use the below command to enable the Tomcat service.

```
<pre class="wp-block-code">```
sudo systemctl enable tomcat9
```
```

Tomcat auto start is enabled. Now, you’ll set up the firewall settings for the Tomcat9.

## <span class="ez-toc-section" id="step_5_%e2%80%93_setting_up_firewall"></span>Step 5 – Setting Up Firewall<span class="ez-toc-section-end"></span>

In this section, you’ll set up [firewall](https://en.wikipedia.org/wiki/Firewall_(computing)#:~:text=In%20computing%2C%20a%20firewall%20is,network%2C%20such%20as%20the%20Internet.) for the tomcat. Firewall is a network security system which monitors the incoming and outgoing traffic of your server based on the predefined rules.

Your Ubuntu servers are protected by firewall by default. You need to open up the port <mark>8080</mark> to access tomcat from outside of your local network. Connections are established using the TCP protocol when connecting to the tomcat from the outside computer.

Use the below command to allow the TCP traffic from any IP address via 8080 to your Ubuntu server.

```
<pre class="wp-block-code">```
sudo ufw allow 8080/tcp
```
```

 You’ll see the below output if the rules are updated properly.

Output

```
<pre class="wp-block-code config">```
Rules updated
Rules updated (v6)

```
```

If you are using amazon EC2 instance, you’ll need to allow the traffic to your server in the security group as shown below. If you are using Digitalocean Droplets, you can configure cloud firewalls using [this](https://www.digitalocean.com/docs/networking/firewalls/how-to/configure-rules/) tutorial. For other service providers, refer the respective firewall tutorials.

<figure class="wp-block-image size-large">![install tomcat on ubuntu](http://149.28.53.131/wp-content/uploads/2020/12/security-group-1024x378.jpg)</figure>0.0.0.0/0 source means to allow the traffic from any source. If you need to allow traffic from a specific IP address, you can specify that IP address in the source. Then the traffic from other IP address will be dropped automatically.

You’ve configured firewalls to allow traffic to tomcat. You’ll test if works properly in the next step.

## <span class="ez-toc-section" id="step_6_%e2%80%93_testing_tomcat_server"></span>Step 6 – Testing Tomcat Server<span class="ez-toc-section-end"></span>

In this section, you’ll test if the Tomcat server is serving the client requests appropriately. You are just going to use the default tomcat homepage to check if its working.

Use the public IP address of your server with port 8080 in your browser as shown below.

http://<var>13.127.78.230</var>:8080/

You’ll see the below output if the tomcat is configured properly.

<figure class="wp-block-image size-large">![install tomcat on ubuntu](http://149.28.53.131/wp-content/uploads/2020/12/Apache-Tomcat-1024x222.jpg)</figure>Tomcat is working properly.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, You’ve installed tomcat on Ubuntu, configured firewall and tested it. You can go ahead and create virtual hosts and host different websites.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

You can install complete LAMP stack at one shot using this tutorial. [How to Install LAMP Using Tasksel on Ubuntu](http://149.28.53.131/install-lamp-using-tasksel-on-ubuntu/).

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1609300442673">### I Can’t access Tomcat using IP address?

<div class="rank-math-answer ">You need to ensure that the firewall is configured properly to allow traffic via port 8080 in the ubuntu servers. You can check it by using the command <mark>ss -ltn</mark>. Additionally check security group configuration if you are using amazon ec2 ubuntu instance. Check cloud firewalls if you are using any other cloud providers.

</div></div><div class="rank-math-list-item" id="faq-question-1609310264809">### Tomcat is running on port 8080, but unable to access remotely using IP address?

<div class="rank-math-answer ">Check if port 8080 is accessible from outside. You can check it by using the command <mark>ss -ltn</mark>. Additionally check security group configuration if you are using amazon ec2 ubuntu instance. Check cloud firewalls if you are using any other cloud providers.

</div></div><div class="rank-math-list-item" id="faq-question-1609310399398">### How to access tomcat from another computer?

<div class="rank-math-answer ">If your port 808 is open to public, then you can access the tomcat from another computer. Check if port 8080 is accessible from outside. You can check it by using the command <mark>ss -ltn</mark>. Additionally check security group configuration if you are using amazon ec2 ubuntu instance. Check cloud firewalls if you are using any other cloud providers.

</div></div></div></div>