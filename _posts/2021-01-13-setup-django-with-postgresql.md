---
id: 4346
title: 'How to Setup Django With PostgreSQL on Ubuntu 20.04 &#8211; Comprehensive Guide'
date: '2021-01-13T20:37:21+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4346'
permalink: /setup-django-with-postgresql/
rank_math_seo_score:
    - '83'
rank_math_focus_keyword:
    - 'Setup Django with PostgreSQL,connect PostgreSQL to Django'
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
socialsnap_share_count_timestamp:
    - '2023-09-07 17:34:01'
ss_total_share_count:
    - '0'
ss_ss_click_share_count_facebook:
    - '1'
rank_math_analytic_object_id:
    - '9'
categories:
    - how-to
tags:
    - django
    - postgresql
    - ubuntu
---

[Django ](https://www.djangoproject.com/)is an open-source **Python** framework for developing **web applications**. It is a versatile, powerful, efficient, and flexible framework for rapid development. Django comes with a development server which by default **contains a lightweight SQLite database file to store data**. Django supports major Databases like MySQL, PostgreSQL, Oracle, etc.

[PostgreSQL ](https://www.postgresql.org/)is one of the widely used **open-source Relational Database Management System** (RDBMS). It has more focus on SQL standards compliance. PostgreSQL is well known for its reliability, data integrity, and correctness. It supports all major Datatypes including binary large objects, pictures, sounds, and videos.

In this Django tutorial, you’ll Download and setup Django with PostgreSQL on Ubuntu 20.04.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="installing_postgressql_and_pip_package_manager"></span>Installing PostgresSQL, and <mark>Pip </mark>Package Manager<span class="ez-toc-section-end"></span>

In this step, you’ll install pip and PostgreSQL from the Ubuntu repository. <mark>pip </mark>is a package manager for Python which is used to install and manage Python packages. <mark>pip </mark>connects to an online repository to get packages. Mostly Python comes with pip preinstalled.

First, **Open your terminal** and execute the following command (**Python 3**).

```
<pre class="wp-block-code">```
sudo apt-get install python3-pip python3-dev libpq-dev postgresql postgresql-contrib
```
```

You’ve installed <mark>pip </mark>package manager and PostgreSQL. These packages are the necessary Python development files required to setup Django with PostgreSQL.

PostgreSQL uses ***“Peer Authentication”*** for local connections. Peer Authentication means that if the *user’s OS username is similar to the PostgreSQL username* then no further authentication is required.

In the next step, you’ll create a Database and a Database user in PostgreSQL.

## <span class="ez-toc-section" id="creating_a_database_and_database_user_in_postgresql"></span>Creating a Database and Database User in PostgreSQL<span class="ez-toc-section-end"></span>

In this step, you’ll create a database, database user, and configure the database to setup Django with PostgreSQL. In the previous step **when you installed PostgreSQL**, an OS user named <mark>postgres</mark> is created. The *OS user* <mark>postgres </mark>corresponds to the PostgreSQL administrative user <mark>postgres</mark>. Note that OS username and PostgreSQL username are the same which enables peer authentication.

First, execute the following command to log in to the PostgreSQL’s interactive session.

```
<pre class="wp-block-code">```
sudo -u postgres psql
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
psql (12.5 (Ubuntu 12.5-0ubuntu0.20.04.1))
Type "help" for help.

postgres=#
```
```

You’ve now logged in to the PostgreSQL interactive session.

Next, you’ll **create a database** in PostgreSQL by executing the following query in the PostgreSQL interactive session. Make sure you replace <var>db\_name</var> with a name relevant to the project.

```
<pre class="wp-block-code config">```
CREATE DATABASE <var>db_name</var>;
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
CREATE DATABASE
```
```

Now the database is created.

Make sure to end the PostgreSQL command with **semicolon** ( ‘;’ ).

Next, you’ll **create a database user** to interact with the database. Ensure you assign a strong and secure password. Execute the following query (*Change the db\_user and password*).

```
<pre class="wp-block-code config">```
 CREATE USER <var>db_user</var> WITH PASSWORD '<var>password</var>';
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
CREATE ROLE
```
```

Now the Database User is created.

You’ll **configure the user** to set default values for the parameters shown below.

- encoding: utf-8
- isolation scheme: read committed
- timezone: UTC

By doing this, you don’t have to configure the parameters every time you make a connection in PostgreSQL database.

Next, execute the below queries to set default values for the parameters.

To set the **encoding** to read **utf-8**.

```
<pre class="wp-block-code config">```
ALTER ROLE db_user SET client_encoding TO 'utf8';
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
ALTER ROLE
```
```

To set the **isolation** to read **committed**.

```
<pre class="wp-block-code config">```
ALTER ROLE db_user SET default_transaction_isolation TO 'read committed';
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
ALTER ROLE
```
```

To set the **timezone** to read **UTC**.

```
<pre class="wp-block-code config">```
ALTER ROLE db_user SET timezone TO 'UTC';
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
ALTER TABLE
```
```

Next, you’ll **grant database access to the newly created user** by executing the below query.

```
<pre class="wp-block-code config">```
GRANT ALL PRIVILEGES ON DATABASE db_name  TO db_user;
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
GRANT
```
```

You’ve **successfully setup the PostgreSQL** by creating a database, database user and configured the database user permissions.

Finally, exit from the interactive PostgreSQL session by executing the below command.

```
<pre class="wp-block-code config">```
\q
```
```

In the next step, you’ll install Django.

## <span class="ez-toc-section" id="installing_django_within_a_python_virtual_environment"></span>Installing Django Within a Python Virtual Environment <span class="ez-toc-section-end"></span>

In this step, you’ll **install <mark>virtualenv</mark>** package, create a virtual environment, activate it, and then install <mark>django</mark>. <mark>virtualenv </mark>package helps you create virtual environments easily. Virtual environment helps to setup Django with PostgreSQL in a local scope.

First, To install <mark>virtualenv</mark> package execute the below command.

```
<pre class="wp-block-code">```
sudo pip3 install virtualenv
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Collecting virtualenv
  Downloading virtualenv-20.3.0-py2.py3-none-any.whl (5.7 MB)
     |████████████████████████████████| 5.7 MB 13.5 MB/s

Successfully installed appdirs-1.4.4 distlib-0.3.1 filelock-3.0.12 virtualenv-20.3.0
```
```

Next , you’ll **create a folder** for Django project by executing the below command.

```
<pre class="wp-block-code">```
mkdir ~/<var>your_project_name</var>
```
```

Next, **move to the newly created folder** by executing the below command.

```
<pre class="wp-block-code">```
cd ~/<var>your_project_name</var>
```
```

Next, you’ll **create a Python virtual environment** in your project directory (current directory) by executing the below command.

```
<pre class="wp-block-code">```
virtualenv <var>your_environment_name</var>
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
created virtual environment CPython3.8.5.final.0-64 in 770ms
  creator CPython3Posix(dest=/home/ubuntu/first_project/first_project_env, clear=False, no_vcs_ignore=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/home/ubuntu/.local/share/virtualenv)
    added seed packages: pip==20.3.1, setuptools==51.0.0, wheel==0.36.1
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator
```
```

The virtual environment creates a local copy of Python and pip into a directory named <var>*your\_*e*nvironment\_name*</var> inside the project directory. To use this virtual environment, First, you’ve to activate the virtual environment.

To activate the virtual environment, execute the below command.

```
<pre class="wp-block-code">```
source <var>your_environment_name</var>/bin/activate
```
```

You can see that the prompt is now changed to the virtual environment name.

Output

```
<pre class="wp-block-code config">```
<var>(your_environment_name)</var> user@host:~/<var>your_project_name</var> $
```
```

Next, you’ll **install Django and Psycopg2** by executing the below command. Psycopg2 is a PostgreSQL adapter for Django.

```
<pre class="wp-block-code">```
 pip install django psycopg2-binary
```
```

You’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Collecting django
  Downloading Django-3.1.5-py3-none-any.whl (7.8 MB)
     |████████████████████████████████| 7.8 MB 1.8 MB/s
Collecting psycopg2-binary
  Downloading psycopg2_binary-2.8.6-cp38-cp38-manylinux1_x86_64.whl (3.0 MB)
     |████████████████████████████████| 3.0 MB 44.2 MB/s
```
```

You’ve successfully installed Django and Psycopg2. Now you have the necessary files to setup Django with PostgreSQL.

Finally, you’ll **start a Django project** with in the <var>your\_project\_name</var> folder by executing the below command.

```
<pre class="wp-block-code config">```
(<var>your_environment_name</var>) $ django-admin.py start_project <var>your_project_name</var> .
```
```

You’ve successfully installed and started a project in Django. To confirm you can see the <var>your\_project\_name</var> folder. You’ll see a new file named *‘<mark>manage.py</mark>‘* that is created by the Django <mark>startproject </mark>command.

In the next step, you’ll configure Django database settings to setup Django with PostgreSQL.

## <span class="ez-toc-section" id="configuring_database_settings_to_setup_django_with_postgresql"></span>Configuring Database Settings to Setup Django With PostgreSQL<span class="ez-toc-section-end"></span>

In this step, you’ll Setup Django with PostgreSQL by configuring the database settings in Django.

First, **open the settings.py** file created by Django startproject by executing the below command.

```
<pre class="wp-block-code">```
nano ~/<var>your_project_name</var>/<var>your_project_name</var>/settings.py
```
```

You’ll see a heading named Database towards the bottom of the file, **scroll down** to the section. You’ll see the content shown below.

```
<pre class="wp-block-code config">```
...

# Database
# https://docs.djangoproject.com/en/3.1/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

...
```
```

As you can see above, currently the Django project is using default SQLite database. You’ve to change that to PostgreSQL database.

To change the database to PostgreSQL replace the Database Section with the below content.

```
<pre class="wp-block-code configpostgtes">```
. . .

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': '<var>your_project_name</var>',
        'USER': '<var>db_user</var>',
        'PASSWORD': '<var>password</var>',
        'HOST': 'localhost',
        'PORT': '',
    }
}

. . .
```
```

Next, save and close the file by pressing <mark>CTRL + X</mark> and <mark>Y</mark>.

You’ve **setup Django with PostgreSQL**.

In the next step, you’ll test your setup by running a Django development server.

## <span class="ez-toc-section" id="testing_your_project"></span>Testing Your Project <span class="ez-toc-section-end"></span>

In this step, you’ll migrate the data structures to the PostgreSQL database and test the server. As of now, you’ve setup Django with PostgreSQL but you do not have any actual data. So, you’ll first set up the initial database structure.

First, **move to the <var>your\_project\_name</var> directory**.

```
<pre class="wp-block-code">```
cd ~/myproject
```
```

Next, execute the below command.

```
<pre class="wp-block-code">```
python manage.py makemigrations
```
```

Next, **initiate the migrate** process by executing the below command.

```
<pre class="wp-block-code">```
python manage.py migrate
```
```

You’ve created the database structure.

Next, you’ll **create an administrative account** by executing the below command.

```
<pre class="wp-block-code">```
python manage.py createsuperuser
```
```

You’ll be prompted to enter user name, email username, email and password. After entering the details you’ll see the below output.

Output

```
<pre class="wp-block-code config">```
Username (leave blank to use 'ubuntu'): <var>Askvikram</var>
Email Username (leave blank to use 'ubuntu'): <var>Askvikram</var>
Email address: <var>askvikram@hotmail.com</var>
Password:
Password (again):
Superuser created successfully.
```
```

Next, you’ve to open a port by allowing external connections so that it can get through firewall. This can be done by executing the below command.

```
<pre class="wp-block-code">```
sudo ufw allow <var>8000</var>
```
```

Next, you will **start your Django development server** by executing the below command.

```
<pre class="wp-block-code">```
python manage.py runserver 0.0.0.0:<var>8000</var>
```
```

Next, **visit the browser** using the IP address or Domain name of the server using port number <var>8000</var>.

```
<pre class="wp-block-code config">```
http://<var>server_domain_name_or_IP_Address</var>:8000
```
```

You’ll see the Django default root page.

Next, append “<mark>**/admin**</mark>” to the previous URL. You’ll be taken to the admin login page.

Finally, enter your <var>username</var> and <var>password</var> for the PostgreSQL user. You’ll be taken to the admin page. you’ve setup Django with PostgreSQL in the previous step and verified it by running a server.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this article, you’ve successfully installed and configured PostgreSQL and setup Django with PostgreSQL. You’ve learned to create a superuser to access the PostgreSQL account. Though Django comes with the SQLite database for development purposes, PostgreSQL proves efficient in Production server.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1611065821934">### 1. How to use Postgres database in Django?

<div class="rank-math-answer ">First. ensure you have Django and PostgreSQL is installed on the server.   
Next, you have to create a Django project using the <mark>startproject</mark> command inside the folder where you have to create the project.  
Finally, change the settings.py file as shown in the above step, “Configuring Database Settings to Setup Django With PostgreSQL”. s

</div></div><div class="rank-math-list-item" id="faq-question-1611069392994">### 2. Why does Postgres use Django?

<div class="rank-math-answer ">(i) Django offers a set of data types that will only work in PostgreSQL.  
(ii) Django has django.contrib.postgres to support database operations on PostgreSQL.   
(iii) If your application makes use of storing geographical data, you will need to use PostgreSQL, as GeoDjango is only fully compatible with PostgreSQL.  
(iv) Big Enterprises prefer to setup Django with PostgreSQL to support their heavy data load. Some of the companies that use PostgreSQL are Apple, Debian, Fujitsu, Red Hat, Sun Microsystem, Cisco, Skype.

</div></div><div class="rank-math-list-item" id="faq-question-1611070318420">### 3. Is Python 3.5 supported and working with PostgreSQL?

<div class="rank-math-answer ">Yes, Python 3.5 can be used to setup Django with PostgreSQL. Also Django officially mentions it’s compatible with Python 3.5 and has been since version 1.8.

</div></div><div class="rank-math-list-item" id="faq-question-1611072841567">### 4. How to exit from PostgreSQL command line utility: psql

<div class="rank-math-answer ">Type `<mark>\q</mark>` and then press <mark>`ENTER` </mark>to quit `<mark>psql</mark>`. As of *PostgreSQL 11*, the keywords “`<strong>quit</strong>`” and “`<strong>exit</strong>`” in the PostgreSQL command-line interface have been included to help make it easier to leave the command-line tool.

</div></div><div class="rank-math-list-item" id="faq-question-1611073052590">### 5. How to change PostgreSQL user password?

<div class="rank-math-answer ">To login without a password:  
<mark>sudo -u user\_name psql db\_name</mark>  
To reset the password if you have forgotten:  
<mark>ALTER USER user\_name WITH PASSWORD ‘new\_password’;</mark>  
You can use the above command even after you’ve setup Django with PostgreSQL.

</div></div><div class="rank-math-list-item" id="faq-question-1611073246921">### 6. password authentication failed for user “postgres”

<div class="rank-math-answer ">You can execute the below command to set a new password and try logging in again.  
<mark>ALTER USER postgres PASSWORD ‘newPassword’;</mark>  
You can visit this [Stackoverflow page](https://stackoverflow.com/questions/7695962/postgresql-password-authentication-failed-for-user-postgres?rq=1) for detailed explanation after you’ve setup Django with PostgreSQL

</div></div></div></div>