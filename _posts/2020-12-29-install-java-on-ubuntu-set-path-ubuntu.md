---
id: 4041
title: 'How to Install Java on Ubuntu 20.04 and Set Path[Simple Way]?'
date: '2020-12-29T18:43:10+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4041'
permalink: /install-java-on-ubuntu-set-path-ubuntu/
rank_math_seo_score:
    - '74'
rank_math_focus_keyword:
    - 'install java on ubuntu'
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
rank_math_description:
    - 'In this tutorial, you''ll install Java on Ubuntu 20.04 and set set path java_home. You''ll install JRE, Open JDK 11 and OpenJDK 8, set the default Java version to be used currently and the set Java_home for java on Ubuntu. '
socialsnap_share_count_timestamp:
    - '2023-09-17 05:45:09'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '45'
categories:
    - how-to
tags:
    - java
    - jdk
    - jre
    - openjdk
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

Java is a class based, object oriented programming language which is widely used to develop enterprise class applications.

In this tutorial, you’ll learn difference between JRE, Open JDK and Oracle JDK, install **J**ava **R**untime **E**nvironment on ubuntu and install java on Ubuntu 20.04 and set java\_home path on Ubuntu 20.04 step by step.

Installing Java is to Install Java Development kit on Ubuntu.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="jre_vs_open_jdk_vs_oracle_jdk"></span>JRE vs Open JDK vs Oracle JDK<span class="ez-toc-section-end"></span>

It is important to understand the difference between jdk vs OpenJDK and Oracle JDK before you install and use it.

**JRE** – It is a Java runtime environment which is used to run the Java based applications. **It is sufficient to install Java Runtime Environment (JRE) if you just want to run the Java based programs** and no need to use any Java developer Tools.

**Open JDK** – It is a free and opensource implementation of the Java SE Platform Edition developed by Oracle, OpenJDK and the Java community. JDK is a **J**ava **D**evelopment **K**it which consists of all the necessary things to develop a Java program. If you need to A new version of OpenJDK is release every six months. Support is provided only for the latest version of the OpenJDK. It is free to use under **GNU General Public License (GNU GPL) version 2**.

**Oracle JDK** – It is a version fully developed by Oracle Corporation and it has some licensing implications. Public updates for Oracle Java SE 8 released after January 2019 will not be available for commercial, business, or production use without a commercial license, as [announced](https://java.com/en/download/release_notice.jsp) by Oracle.

Now, you’ll learn how to install JRE, Open JDK and Oracle JDK in Ubuntu.

## <span class="ez-toc-section" id="installing_jre_on_ubuntu_default"></span>Installing JRE on Ubuntu (Default)<span class="ez-toc-section-end"></span>

In this section, you’ll install default JRE on Ubuntu. Default JRE means the latest LTS version of the JRE which is currently Java 11.

JRE is already included in the JDK package. If you are going to install JDK version, then you can skip this section and directly install JDK using the next section.

Use the <mark>apt</mark> command line utility with the <mark>install</mark> command to install the default JRE.

```
<pre class="wp-block-code">```
sudo apt install default-jre
```
```

Default JRE is installed.

## <span class="ez-toc-section" id="installing_open_jdk_default"></span>Installing Open JDK (default)<span class="ez-toc-section-end"></span>

In this section, you’ll install the default Open JDK version.

The default Open JDK version currently is Java 11. It is the latest LTS version of Java.

Use the apt command line utility with the install command to install the default OpenJDK.

```
<pre class="wp-block-code">```
sudo apt install default-jdk
```
```

Open JDK is installed. You can verify it using the <mark>java -version</mark> command.

```
<pre class="wp-block-code">```
java -version
```
```

You’ll see the output as below with the details of the Java versions installed.

Output

```
<pre class="wp-block-code config">```
openjdk version "11.0.9.1" 2020-11-04
OpenJDK Runtime Environment (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04)
OpenJDK 64-Bit Server VM (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04, mixed mode, sharing)

```
```

Default Open JDK is installed on Ubuntu. Now, you’ll install Open JDK8.

## <span class="ez-toc-section" id="installing_open_jdk_8"></span>Installing Open JDK 8<span class="ez-toc-section-end"></span>

In this section, you’ll install the Open JDK version 8.

Java 8 is most widely used Java version. Hence, if your applications require Java version 8 on Ubuntu, you can install Java 8 using the below command.

```
<pre class="wp-block-code">```
sudo apt install openjdk-8-jdk
```
```

If you use the <mark>Java -version</mark> command, you’ll still see the <mark>Java version 11</mark>. Because you have installed OpenJDK 11 first. You’ll learn how to manage the default Java version on Ubuntu in the next step.

You’ve installed Open JDKs.

## <span class="ez-toc-section" id="setting_the_default_java_version"></span>Setting the Default Java Version<span class="ez-toc-section-end"></span>

In this section, you’ll set the default Java version. Because You’ve installed two versions of the JDK in the previous steps.

First to check the current default Java version, use the command Java -version.

```
<pre class="wp-block-code">```
java -version
```
```

You’ll see the current default version of Java as below.

Output

```
<pre class="wp-block-code config">```
openjdk version "11.0.9.1" 2020-11-04
OpenJDK Runtime Environment (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04)
OpenJDK 64-Bit Server VM (build 11.0.9.1+1-Ubuntu-0ubuntu1.20.04, mixed mode, sharing)

```
```

To change the default java version, <mark>update-alternatives</mark> utility with <mark>–config</mark> option.

Use the below command to update the default Java version.

```
<pre class="wp-block-code">```
sudo update-alternatives --config java
```
```

You’ll see the below prompt which will display the available versions of Java. The one marked with the **<mark>\*</mark>** is the current default version.

Enter your desired version to set as the default Java version. In this example, you’ll select 2.

Output

```
<pre class="wp-block-code config">```
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
* 0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      auto mode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      manual mode
  2            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081      manual mode

Press <enter> to keep the current choice[*], or type selection number:<var>2</var>
```
```

You’ll see the below output which says Java 8 open JDK is set a default Java version.

Output

```
<pre class="wp-block-code config">```
update-alternatives: using /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java to provide /usr/bin/java (java) in manual mode
```
```

To validate if its set properly, use the below command.

```
<pre class="wp-block-code">```
java -version
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
openjdk version "1.8.0_275"
OpenJDK Runtime Environment (build 1.8.0_275-8u275-b01-0ubuntu1~20.04-b01)
OpenJDK 64-Bit Server VM (build 25.275-b01, mixed mode)
```
```

You’ve set the default Java version to Open JDK version “1.8.0\_275” successfully. Next, you’ll set Java\_home environment variable.

## <span class="ez-toc-section" id="setting_java_home_on_ubuntu"></span>Setting Java\_Home on Ubuntu<span class="ez-toc-section-end"></span>

Applications developed using Java use the environment variable Java\_home to determine the Java installation location. In this section, you’ll set Java\_home environment variable. Environment variables are normally defined in the file <mark>/etc/environment</mark>.

Now, you’ll find the Java installation locations using the update-alternatives command as below.

```
<pre class="wp-block-code">```
sudo update-alternatives --config java
```
```

It’ll display the Java installation locations and it shows the default Java version too as below.

Output

```
<pre class="wp-block-code">```
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      auto m                                                                                                                                                             ode
  1            /usr/lib/jvm/java-11-openjdk-amd64/bin/java      1111      manual                                                                                                                                                              mode
<var>*</var> 2            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081      manual                                                                                                                                                              mode

Press <enter> to keep the current choice[*], or type selection number:

```
```

Press <mark>Enter</mark> to keep the current choice.

- OpenJDK 11 is located at <mark>/usr/lib/jvm/java-11-openjdk-amd64/bin/java</mark>
- OpenJDK 8 is located at <mark>/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java</mark>

<mark>/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java</mark> is set as default Java as denoted with <var>\*</var>. You can copy this path.

Now open the <mark>/etc/environment</mark> using the nano editor using the below command.

```
<pre class="wp-block-code">```
sudo nano /etc/environment
```
```

It’ll open the environment file. Append the java path configuration as shown below.

/etc/environment/

```
<pre class="wp-block-code config">```

PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin"
JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java"

```
```

Presss <mark>Ctrl + X</mark> and Press <mark>Y</mark> and then press <mark>Enter</mark> to save the file and exit.

You can logout and login again or run source command as below to make the environment path changes effective your current session.

```
<pre class="wp-block-code">```
source /etc/environment
```
```

You can validate if the Environment variable is correctly set by using the echo command. Echo command will display the value of the variable passed along with it.

```
<pre class="wp-block-code">```
echo $JAVA_HOME
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java
```
```

You’ve successfully set Java\_home for Java on Ubuntu.

## <span class="ez-toc-section" id="uninstalling_java"></span>Uninstalling Java<span class="ez-toc-section-end"></span>

If you want to uninstall Java for any reason, you can do it by using the <mark>apt remove</mark> command as shown below.

```
<pre class="wp-block-code">```
sudo apt remove <var>openjdk-8-jdk</var>
```
```

You can remove the specific java version by using that version name appropriately in the highlighted text.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, You’ve leanrt the difference between JRE, Open JDK and Oracle JDK. You’ve installed JRE, Open JDK 11 and Open JDK8, set the default Java version when you have multiple java versions installed. You’ve also set Java\_home environment variable for Java.

You have learnt, How to install Java runtime environment on Ubuntu, how to install Java on Ubuntu, set java\_home for Java and set default Java version on Ubuntu.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1609210574563">### How to set JAVA\_HOME for Java?

<div class="rank-math-answer ">You can set Java\_home for java in the /etc/environment file.

</div></div><div class="rank-math-list-item" id="faq-question-1609210637559">### How to set Java environment path in Ubuntu?

<div class="rank-math-answer ">You can set Java environment path on Ubuntu in the /etc/environment file.

</div></div><div class="rank-math-list-item" id="faq-question-1609213582269">### how to find jdk path in ubuntu

<div class="rank-math-answer ">You can find JDK path in Ubuntu using the command: <mark>readlink -f $(which java)</mark>. It will show you the location of the default Java version that is currently active.

</div></div><div class="rank-math-list-item" id="faq-question-1609213639428">### how to find jre path in linux

<div class="rank-math-answer ">You can find JRE path in linux ubuntu using the command `<mark>echo $JAVA_HOME</mark>`.

</div></div><div class="rank-math-list-item" id="faq-question-1609213667530">### How to know the JVM path in a Linux system?

<div class="rank-math-answer ">You can find JVM path in Ubuntu using the command: <mark>readlink -f $(which java)</mark>. It will show you the location of the default Java version that is currently active.

</div></div><div class="rank-math-list-item" id="faq-question-1609213739258">### How to find path to java?

<div class="rank-math-answer ">You can find path to Java (all installed versions) using the command `<mark>update-alternatives --list java</mark>`. It will also show the currently active version using **\***. After displaying, press Enter to exit the prompt without changing the default version.

</div></div><div class="rank-math-list-item" id="faq-question-1609213829708">### how to find jre version in linux

<div class="rank-math-answer ">You can find JRE verssion in linux ubuntu using the command `<mark>echo $JAVA_HOME</mark>`. It will display the currently active JRE in your system.

</div></div></div></div>