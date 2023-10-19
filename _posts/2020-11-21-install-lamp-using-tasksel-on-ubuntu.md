---
id: 3204
title: 'How to Install LAMP Using Tasksel on Ubuntu[Easy Method]?'
date: '2020-11-21T09:15:39+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3204'
permalink: /install-lamp-using-tasksel-on-ubuntu/
rank_math_seo_score:
    - '83'
bialty_cs_alt:
    - ''
rank_math_internal_links_processed:
    - '1'
ss_social_share_disable:
    - ''
rank_math_primary_category:
    - '16'
rank_math_focus_keyword:
    - 'install lamp using tasksel'
rank_math_description:
    - 'In this tutorial, you''ll install Lamp using tasksel on ubuntu and secure your mysql by adding password for the root user and removing anonymous users and test databases. '
socialsnap_share_count_timestamp:
    - '2023-09-13 14:49:23'
ss_total_share_count:
    - '1'
ss_ss_share_count_facebook:
    - '1'
tcb2_ready:
    - '1'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
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
    - '28'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"7fe4e9c19c8f705eaa52e6c52beea6ba";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - installation
    - taskel
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

LAMP stack is a set of open sources software which can be installed on your computer to make your computer a web server.

LAMP is an Acronym of **L**inux operating system, **A**pache web server, **M**ySQL database, **P**hp programming language.

In this tutorial, you’ll install lamp using Tasksel on Ubuntu. Tasksel is a Debian/Ubuntu based command line utility which can be used to install a group of packages in linux.

Tasksel is a debian based package and can **only be installed** on [Debian based distro](https://www.debian.org/misc/children-distros) such as **Ubuntu** linux.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

- Launch a server in any cloud provider. If you would like to **try Amazon web services( AWS) free tier** for one year, you can follow this guide to launch a server. [Launch EC2 Instance in AWS Step by step](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- If you would like to have a server from a managed cloud hosting provider, you can use Cloudways. Using Cloudways, you can create servers from leading cloud providers like AWS, DigitalOcean, Vultr, Linode, Google Cloud.
- Have root user access or a user account with SUDO Privileges.

## <span class="ez-toc-section" id="step_1_%e2%80%93_updating_packages_repository"></span>Step 1 – Updating Packages Repository<span class="ez-toc-section-end"></span>

In this step, first you’ll update the package repository of Ubuntu. It’ll help you to get the latest version of the installed packages.

<mark>apt update</mark> command is used to perform the update of the package repository. Use the below command to update the packages.

```
<pre class="wp-block-code">```
sudo apt update 
```
```

Now, your packages are updated. You’ll now install Tasksel to handle other package installations.

## <span class="ez-toc-section" id="step_2_%e2%80%93_installing_tasksel"></span>Step 2 – Installing Tasksel<span class="ez-toc-section-end"></span>

In this step, you’ll install Tasksel and all its dependencies.

Use the <mark>apt install</mark> command to install <mark>Tasksel</mark> with its dependencies.

```
<pre class="wp-block-code">```
sudo apt install tasksel
```
```

Now, you’ll use the <mark>Tasksel</mark> to install the LAMP Stack.

## <span class="ez-toc-section" id="step_2_%e2%80%93_installing_lamp_using_tasksel"></span>Step 2 – Installing LAMP Using Tasksel<span class="ez-toc-section-end"></span>

In this step, you’ll install LAMP stack using <mark>Tasksel</mark>.

Use the <mark>Tasksel install</mark> to install the LAMP package to your server.

```
<pre class="wp-block-code">```
sudo tasksel install lamp-server
```
```

You’ll have the lamp package installed in your server with the basic setup. You’ll need to secure the <mark>MYSQL</mark> installation to make your database secure.

## <span class="ez-toc-section" id="step_3_%e2%80%93_securing_mysql_installation"></span>Step 3 – Securing Mysql Installation<span class="ez-toc-section-end"></span>

Mysql is installed without any password for the root user during the installation. Anybody can access your database since it doesn’t have a password authentication. This will make your database vulnerable to the attacks.

Hence, now you’ll set up the password authentication and remove other unnecessary access for your mysql server using the mysql commandline wizard.

Use <mark>mysql\_secure\_installation</mark> to enter into the command line wizard.

```
<pre class="wp-block-code">```
sudo mysql_secure_installation
```
```

Mysql command line wizard will be opened.

The below three sections will be executed as a wizard. For the better understanding and reading experience, it is split as sections.

**Setting password for root user**

As a first part of the securing installation, you’ll set up the password authentication for the <mark>root</mark> user using the <mark>VALDATE PASSWORD PLUGIN</mark>. This plugin helps to check the strength of password allowing to set a **highly secure password**. Press Y to allow the usage of the Validate Password Plugin.

Output

```
<pre class="wp-block-code config">```
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No: <var>Y</var> 
``` 
```

This will display the different levels of secure password that will be validated by the Validate Password Plugin.

**Level 0 = low, Level 1 = medium, and Level 2 = strong.**

Medium level policy uses Length &gt;=8, mixed case, numeric and special characters. It is sufficient enough to secure the mysql database. Hence, you’ll **use the medium level password policy**.

Enter <mark>1</mark> to opt for the medium level policy as shown below.

Output

```
<pre class="wp-block-code config">```
There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: <var>1</var>
```
```

Now you’ll be asked to enter the password. Enter your desired password with length greater than 8, number, mixed case of alphabets and special characters.

Output

```
<pre class="wp-block-code config">```
Please set the password for root here.

New password: <var>**********</var>
Re-enter new password: <var>**********</var>
```
```

Once you press enter after entering the password, the Validate password plugin will validate your password and display the estimated strength of the password. It will ask you to confirm if you would like to continue with the provided password. Press <mark>Y</mark> and Press <mark>Enter</mark>.

Output

```
<pre class="wp-block-code config">```
Estimated strength of the password: 100
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : <var>Y</var>
```
```

**Removing Anonymous User Account**

Now, you’ll proceed to remove the anonymous user accounts created during installation.

Anonymous user account is created during installation to making the installation smoother and its intended only for testing. It’ll allow everyone to connect to your database without user account created for them.

You MUST remove it before you move your database to the production environment.

Press <mark>Y</mark> for the question <mark>Remove anonymous users?</mark> and press <mark>enter</mark>.

Output

```
<pre class="wp-block-code config">```
By default, a MySQL installation has an anonymous user,
allowing anyone to log into MySQL without having to have
a user account created for them. This is intended only for
testing, and to make the installation go a bit smoother.
You should remove them before moving into a production
environment.

Remove anonymous users? (Press y|Y for Yes, any other key for No) : <var>Y</var>
Success. 
```
```

**Disallowing Remote Login for Root User**

Root user is a user with every privilege on the database. Its destructive if somebody from the network have guessed your password and login to your database. Hence root account must be protected with utmost security to avoid unauthorized access.

In this step, you’ll remove the Remote login your root account.

Press <mark>Y</mark> for the question <mark>Disallow root login remotely?</mark> and press <mark>enter</mark>.

Output

```
<pre class="wp-block-code config">```
Normally, root should only be allowed to connect from
'localhost'. This ensures that someone cannot guess at
the root password from the network.

Disallow root login remotely? (Press y|Y for Yes, any other key for No) : <var>Y</var>
Success. 
```
```

**Removing Test Database and Its Access**

By default, a test database is created during the Mysql installation without password and anybody is allowed to access it. This is also intended only for testing and MUST be removed before moving into Production environment.

In this step, you’ll remove the test database and its access.

Press <mark>Y</mark> for the question <mark>Remove test database and access to it?</mark> and press <mark>enter</mark>.

Output

```
<pre class="wp-block-code config">```
By default, MySQL comes with a database named 'test' that
anyone can access. This is also intended only for testing,
and should be removed before moving into a production
environment.

Remove test database and access to it? (Press y|Y for Yes, any other key for No) : <var>Y</var>
 - Dropping test database...
Success.

 - Removing privileges on test database...
Success.
```
```

**Reloading Privilege Table**

All the privileges for each table is stored in a table called privilege table. Since you have removed the privileges on the test database, you need to **reload the privilege table** to ensure that the changes you have made until now takes effect.

In this step you’ll reload the privileges table.

Press <mark>Y</mark> for the question <mark>Reload privilege tables?</mark> and press <mark>enter</mark>.

Output

```
<pre class="wp-block-code config">```
Reloading the privilege tables will ensure that all changes
made so far will take effect immediately.

Reload privilege tables now? (Press y|Y for Yes, any other key for No) : <var>Y</var>
Success.

All done!
```
```

All done. You’ve secured your Mysql installation. Now you’ll proceed to test the LAMP stack installed to ensure if everything is installed properly.

## <span class="ez-toc-section" id="step_4_%e2%80%93_testing_the_lamp_stack"></span>Step 4 – Testing the LAMP Stack<span class="ez-toc-section-end"></span>

In this step, you’ll test the LAMP stack. Linux is an operating system which you are already working and Mysql is working fine based on the above steps.

You’ll test the remaining Apache and PHP.

**Testing Apache**

Open the web browser in you local computer and enter the <mark>public IP of your server</mark>. If you would like to test in the same Linux server, just type <mark>localhost</mark> in the browser address bar.

You’ll see the homepage like below. It means <mark>Apache is installed properly</mark> and its ready to serve webpages.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2020/11/Apache2-Ubuntu-Default-Page-It-works-2-665x1024.jpg)</figure></div>Apache is installed successfully. Now you’ll test PHP installation.

**Testing PHP**

To test the php file, now you’ll create a php file which will display the php information.

To server the file via Apache, the files should be created under the directory <mark>/var/www/html/</mark> .

Navigate to the /var/www/html/ directory using the below command.

```
<pre class="wp-block-code">```
cd /var/www/html/
```
```

Now create a file called info.php using the below command.

```
<pre class="wp-block-code">```
nano info.php
```
```

nano will open the file. Enter the below content.

/var/www/html/info.php

```
<pre class="wp-block-code filecontent">```
<?php
  phpinfo();
?>
```
```

The content is to display the information of the php. The method <mark>phpinfo()</mark> is used to display the information of the installed PHP.

Press <mark>Ctrl + O</mark> to write out the contents to file and press <mark>enter</mark>. Contents are written into the file. Now press <mark>Ctrl + X</mark> to exit the nano editor.

To check if the PHP is working fine, use your **<mark>publicaddress</mark>/info.php** in your web browser. You’ll see the PHP information as below.

<figure class="wp-block-image size-large">![Install lamp sing tasksel on ubuntu](http://149.28.53.131/wp-content/uploads/2020/11/PHP-7-4-3-phpinfo.jpg)</figure>This shows that the PHP is installed successfully.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

You’ve installed the LAMP stack using Tasksel and also verified the installion of apache and PHP.

You’ve learnt how to install lamp using tasksel on ubuntu.

You can now serve file using this webserver.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1605927754534">### Amazon Linux: apt-get: command not found

<div class="rank-math-answer ">If you’re using Amazon Linux machine image, it’s CentOS-based, which is RedHat-based. Red hat based linux supports `<strong><mark>yum</mark></strong>` not `<mark>apt-get</mark>`. You can install packages using YUM install &lt;Package name&gt;.

To list the available packages, you can use <mark>yum search &lt;Package name&gt;</mark>.

</div></div><div class="rank-math-list-item" id="faq-question-1605928270938">### What is Tasksel? 

<div class="rank-math-answer ">Tasksel is a Debian/Ubuntu based command line utility which can be used to install a group of packages in Linux.

</div></div><div class="rank-math-list-item" id="faq-question-1605928307233">### How to install Tasksel on Ubuntu?

<div class="rank-math-answer ">Tasksel can be installed using <mark>sudo apt install tasksel</mark>

</div></div><div class="rank-math-list-item" id="faq-question-1605928424006">### How do I install lamp in Tasksel?

<div class="rank-math-answer ">You can install lamp in tasksel using <mark>sudo tasksel install lamp-server</mark>.

</div></div><div class="rank-math-list-item" id="faq-question-1605928461913">### Tasksel VS APT? 

<div class="rank-math-answer ">Tasksel is more powerful in processing and selecting tasks. where APT installs packages in a standard way.

</div></div></div></div>