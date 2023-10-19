---
id: 3661
title: 'How to Install Postgresql on Ubuntu 20.04?'
date: '2020-12-09T19:31:34+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3661'
permalink: /install-postgresql-on-ubuntu/
rank_math_primary_category:
    - '16'
rank_math_seo_score:
    - '79'
rank_math_focus_keyword:
    - 'install postgresql on ubuntu'
rank_math_description:
    - 'In this tutorial, you''ll install postgresql on ubuntu 20.04 and configure various authentication methods. You''ll also create new roles and new databases in postgresql which can be accessed.'
ss_social_share_disable:
    - ''
rank_math_internal_links_processed:
    - '1'
socialsnap_share_count_timestamp:
    - '2023-08-29 08:44:38'
ss_total_share_count:
    - '0'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
rank_math_analytic_object_id:
    - '20'
categories:
    - how-to
tags:
    - aws
    - ec2
    - installation
    - postgresql
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

Postgresql is an opensource relational database. It is highly available and versatile. PGAdmin is a commonly used database administration tool used to manage the Postgresql installations.

In this tutorial, you’ll install Postgresql 12 on Ubuntu 20.04.

If you want to **install Postgresql with High availability**, refer the tutorial [How to Set Up a Highly Available PostgreSQL Cluster Using Patroni and HAProxy on Ubuntu?](http://149.28.53.131/set-up-a-highly-available-postgresql-cluster-using-patroni-and-haproxy/?swcfpc=1) If you want a install a standalone Postgresql, read below.

This tutorial uses the AWS EC2 instances for demonstration. Hence you’ll install postgresql on Ubuntu in AWS EC2. However, **this will work in any Ubuntu servers**.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="step_1_%e2%80%93_installing_postgresql"></span>Step 1 – Installing Postgresql<span class="ez-toc-section-end"></span>

In this step, you’ll install postgresql.

Use the apt command along with -contrib to install postgresql database with additional optional [utilities](https://www.postgresql.org/docs/current/contrib.html).

```
<pre class="wp-block-code">```
sudo apt install postgresql postgresql-contrib
```
```

- **sudo apt install** – To install the packages
- **postgresql** – to install the postgresql package
- **postgresql-contrib** – to install the postgresql-contrib packages

Postgresql is installed along with the contributions.

By default, the installation creates a Postgresql cluster which is a collection of databases managed by a single instance of the server. This cluster will contain database called <mark>postgres</mark> which is default database for utilities, users and the third party services.

Default data directory for postgresql is **/var/lib/postgresql<mark>/12/</mark>main** and configuration files such as pg\_hba.conf are stored in **/etc/postgresql<mark>/12/</mark>main** directory. Ensure the appropriate version of the postgresql is used while checking the data or the configuration directory.

The <mark>systemctl</mark> command is used to manage the *systemd* services.

You can **check if the Postgresql service is active** by using the s<mark>ystemctl is-active</mark> command as below.

```
<pre class="wp-block-code">```
sudo systemctl is-active postgresql
```
```

You can check if the Postgresql service is enabled by using the <mark>systemctl is-enabled</mark> command.

```
<pre class="wp-block-code">```
sudo systemctl is-enabled postgresql
```
```

**enabled state ensures that the Postgresql starts automatically at the system boot**. It will be <mark>enabled</mark> by default.

You can check the current status of the Postgresql cluster using Systemctl status command.

```
<pre class="wp-block-code">```
 sudo systemctl status postgresql
```
```

It’ll show the running status of the postgresql as below.

```
<pre class="wp-block-code filecontent">```
ubuntu@ip-172-31-13-67:~$  sudo systemctl status postgresql
● postgresql.service - PostgreSQL RDBMS
     Loaded: loaded (/lib/systemd/system/postgresql.service; enabled; vendor pr>
     Active: active (exited) since Wed 2020-12-09 00:41:39 UTC; 23s ago
   Main PID: 41214 (code=exited, status=0/SUCCESS)
      Tasks: 0 (limit: 1164)
     Memory: 0B
     CGroup: /system.slice/postgresql.service

Dec 09 00:41:39 ip-172-31-13-67 systemd[1]: Starting PostgreSQL RDBMS...
Dec 09 00:41:39 ip-172-31-13-67 systemd[1]: Finished PostgreSQL RDBMS.
lines 1-10/10 (END)

```
```

You can also check if the Postgresql is ready to accept connections from the clients by using the below command.

```
<pre class="wp-block-code">```
sudo pg_isready
```
```

You’ll see the message accepting connections as below.

```
<pre class="wp-block-code config">```
/var/run/postgresql:5432 - accepting connections
```
```

Postgresql is installed. Now, you’ll create new roles.

## <span class="ez-toc-section" id="step_2_%e2%80%93_creating_a_new_role"></span>Step 2 – Creating a New Role<span class="ez-toc-section-end"></span>

In this step, you’ll create new roles to handle authorization to your postgresql database.

By default, **Postgresql is setup to use the ident authentication**. It means the the Postgresql roles are associated with the Unix/linux system account. If a roles with the name of the system account exists in the Postgresql database, then the user will be able to login to the Postgresql using the same user name.

AWS EC2 Ubuntu instances have the user ubuntu **created by default with the sudo privilege**. You’ll create a postgresql role called ubuntu which can be used to login to PostgreSQL database.

By default, the PostgreSQL **installation also creates a role called Postgres**. You can use the Postgres account to create new roles.

Use the below command to create role called <mark>ubuntu</mark>.

```
<pre class="wp-block-code">```
sudo -u postgres createuser <var>ubuntu</var>
```
```

- **sudo -u postgres** – To execute the command as the user <mark>postgres</mark>
- **createuser** – command to create user
- **ubuntu** – new role/user name to be created

Now the new role called ubuntu is created in your postgresql database.

**You can move on to step 3 to create database with the same name <mark>ubuntu</mark>.**

 If you want to create additional roles, you can use the below commands.

Switch over to the postgres account using <mark>sudo -i -u</mark> command.

```
<pre class="wp-block-code">```
sudo -i -u postgres
```
```

Now you’ll be logged in to the Postgresql database and postgres prompt will be displayed.

Use the command <mark>createuser –interactive –pwprompt</mark> to create a new role.

```
<pre class="wp-block-code">```
createuser --interactive --pwprompt
```
```

- **createuser** – command to create user
- **–interactive** – to create user using a interactive mode
- **–pwprompt** – to create a user with a password

The script will prompt for some interactive questions to create user with your specifications.

```
<pre class="wp-block-code  config">```
Enter name of role to add:<var>vikram</var>
```
```

Add your preferred username. Press <mark>Enter</mark>.

Now you’ll be asked to enter the password and confirm it again. *(Passwords you type are always invisible)*

```
<pre class="wp-block-code config">```
Enter password for new role:
Enter it again:
```
```

Press <mark>Enter</mark>.

Now, you’ll be prompted if you would want the new role to be a super user. Super user is a user with all the database privileges. Press <mark>Y</mark> if you want he new role to be a super user.

```
<pre class="wp-block-code config">```
Shall the new role be a superuser? (y/n) <var>y</var> 
```
```

The new role is created with your desired role name. You’ll create a database now.

## <span class="ez-toc-section" id="step_3_%e2%80%93_creating_a_new_database"></span>Step 3 – Creating a New Database<span class="ez-toc-section-end"></span>

In this step, you’ll create database.

Database is logical group of the user defined objects such as tables, views, triggers and other database objects. When you create a database, you can also provide special access to this specific database to the different roles.

You’ll create a database called <mark>ubuntu</mark> under the <mark>*role ubuntu*</mark>. It means the role ubuntu will be the owner of the database ubuntu.

Use the below command to create the database.

```
<pre class="wp-block-code">```
sudo -u postgres createdb -O <var>ubuntu</var> <var>ubuntu</var>
```
```

- **sudo -u postgres** – denotes the command should be executed as the postgres user.
- **createdb** – denotes a database to be created.
- **ubuntu** – To owner/role of the database to be created.
- **ubuntu** – name of the database to be created.

Now the database called **ubuntu** is created under the *role ubuntu*. You can login to the

You can connect to the ubuntu database by typing psql in the shell, if all the steps are followed appropriately.

```
<pre class="wp-block-code">```
psql
```
```

You are connected to the ubuntu database and you can try to create a database table if you want.

```
<pre class="wp-block-code">```
psql > create table <var>mytesttable</var>(<var>test</var> varchar);
```
```

this will show the below message which means the table is created successfully.

```
<pre class="wp-block-code config">```
CREATE TABLE
```
```

You have created database and created database tables inside it.

## <span class="ez-toc-section" id="step_4_%e2%80%93_configuring_the_postgresql_client_authenticationoptional"></span>Step 4 – Configuring the Postgresql Client Authentication(Optional)<span class="ez-toc-section-end"></span>

In this step, you’ll configure the PostgreSQl client authentication. You can learn about the various authentication methods available in PostgreSQL in [the official page](https://www.postgresql.org/docs/12/auth-methods.html).

By default, it is configured to use the peer authentication. This allows to connect with the same role name from ubuntu.

If you want to use different role names which is not the system user and connect to that different roles with the password, you need to update the authentication method in the **/etc/postgresql<mark>/12/</mark>main/pg\_hba.conf** file.

Use the below command to open the file.

```
<pre class="wp-block-code">```
sudo vim <strong>/etc/postgresql<mark>/12/</mark>main/pg_hba.conf</strong>
```
```

It will open the file as below. Press i to enter the edit mode in vim editor. Change the highlighted peer to md5. All the other users except <mark>postgres</mark> will be using the password method.

Do not change the authentication method for the user postgres(first line of the below code). If you change it, then you will not be able to login to the postgres user with the peer authentication method.   
  
 If you want to login to ubuntu with peer authentication, copy and paste a similar line for ubuntu in the place of the postgres. Otherwise You’ll also not be able to login to *ubuntu role* with peer authentication.

```
<pre class="wp-block-code config">```
local   all             postgres                                peer

# TYPE  DATABASE        USER            ADDRESS                 METHOD

# "local" Is for Unix Domain Socket Connections Only
local   all             all                                     <var>md5</var>
# IPv4 Local Connections:
host    all             all             127.0.0.1/32            md5
# IPv6 Local Connections:
host    all             all             ::1/128                 md5
# Allow Replication Connections From Localhost, by a User With The
# Replication Privilege.
local   replication     all                                     peer
host    replication     all             127.0.0.1/32            md5
host    replication     all             ::1/128                 md5

```
```

Save the file and exit the editor.

You have configured the authentication methods of the postgres to use various authentication methods.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

You have successfully installed PostgreSQL 12. You’ve learnt how to install PostgreSQL on Ubuntu 20.04 AWS EC2 Instance. You have also created roles and databases with the various authentication methods.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

You can **create a highlighly available PostgreSQL cluster** using the tutorial [How to Set Up a Highly Available PostgreSQL Cluster Using Patroni and HAProxy on Ubuntu](http://149.28.53.131/set-up-a-highly-available-postgresql-cluster-using-patroni-and-haproxy/).

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1607521351566">### How do I start postgresql on Ubuntu 

<div class="rank-math-answer ">use the command sudo systemctl start postgresql

</div></div><div class="rank-math-list-item" id="faq-question-1607521390534">### How install and configure PostgreSQL on Ubuntu?

<div class="rank-math-answer ">Follow the steps of this tutorial. You’ll successfully install and configure Postgresql.

</div></div><div class="rank-math-list-item" id="faq-question-1607521476220">### Where is PostgreSQL installed on Ubuntu?

<div class="rank-math-answer ">When installing PostgreSQL using apt, it is installed in the location **/var/lib/postgresql/**.

</div></div></div></div>