---
id: 2458
title: 'How to Add User in Ubuntu [Including Sudo User &#038; Groups ]?'
date: '2020-06-14T16:26:03+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://139.180.139.123/?p=2458'
permalink: /add-user-in-ubuntu/
rank_math_internal_links_processed:
    - '1'
rank_math_primary_category:
    - '10'
rank_math_seo_score:
    - '74'
rank_math_description:
    - 'In this article, you''ll learn and add user in Ubuntu installation. You''ll also learn how to add user to Sudoers. '
rank_math_focus_keyword:
    - 'add user in ubuntu'
ekit_post_views_count:
    - '1'
socialsnap_share_count_timestamp:
    - '2023-09-04 23:43:57'
ss_total_share_count:
    - '0'
ss_social_share_disable:
    - ''
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
rank_math_analytic_object_id:
    - '40'
categories:
    - how-to
tags:
    - ubuntu
    - user
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

When you install Ubuntu, *the first thing you would need is to add users*. Because when installing Ubuntu, you’ll be having only root User Created.

Its dangerous to have and work with root user due to its highest privilege which have destructive capabilities. Hence, its a best practice to add users in Ubuntu for your day to day work.

In this article, you will learn

- [Difference between <mark>useradd</mark> and <mark>adduser</mark> commands](#Difference-Between-Useradd-and-Adduser-Commands)
- [How to add user in Ubuntu ](#Adding-User)
- [How to add user in Ubuntu with Home directory](#Adding-User-in-Ubuntu-With-Home-Directory)
- Create user with Password
- [Create User and Add to Group \[In Single Command\]](#Adding-User-to-Group)
- [Adding Existing User to Existing Group](#Adding-Existing-User-to-Existing-Group)
- [Add user to Sudo Group](http://Adding-User-to-Sudo-Group)
- [Add User to Sudoers File](http://Adding-Users-to-Sudoers-File)
- [Check if the User has Sudo privileges](#check-sudo-privileges)

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

To add user, you need to have the root user privilege. If you’ve a non root user, you should have an account with the Sudo Privileges.

## <span class="ez-toc-section" id="difference_between_useradd_and_adduser_commands"></span>Difference Between Useradd and Adduser Commands<span class="ez-toc-section-end"></span>

<mark>useradd</mark> is the binary compiled within your Ubuntu installation whereas the **<mark>adduser</mark> command is a perl script which uses the <mark>useradd</mark> command in the backend** along with some additional methods. Those additional methods make the <mark>adduser</mark> command more user friendly and interactive to customize the new user creation.

## <span class="ez-toc-section" id="adding_user"></span>Adding User<span class="ez-toc-section-end"></span>

In this section, you’ll learn how to add user in Ubuntu **using <mark>adduser</mark> command.**

<mark>adduser</mark> command internally uses the perl script which is an interactive script which will ask for the password to be set. It also creates the home directory for the newly created user.

When you’re logged in to the system **using the root user**, type the following command to add user.

```
<pre class="wp-block-code">```
adduser <var>username</var>
```
```

When you’re logged in to the system **using the non root user** with the sudo privileges, type the following command to add user from ubuntu terminal.

```
<pre class="wp-block-code">```
sudo adduser <var>username</var>
```
```

- **sudo** – Keyword to execute the command with admin privileges
- **adduser** – command to add a new user
- **username** – Your desired new user name

Press <mark>Enter</mark>.

You’ll be asked to enter the password.

Enter the password.

You’ll be asked with other questions which are optional. Press enter if you would like to skip it.

Finally, the information you’ve entered will be displayed for your confirmation. Press ‘Y’ if you would like to confirm.

The command will create user with home directory and copy the files from the *<mark>/etc/skel</mark>* directory to the users home directory. Within the home directory, the user can write, edit, and delete files and directories.

## <span class="ez-toc-section" id="adding_user_in_ubuntu_with_home_directory"></span>Adding User in Ubuntu With Home Directory<span class="ez-toc-section-end"></span>

In this section, you’ll learn how to add user in Ubuntu with the home directory using <mark>useradd</mark> command. This command will use the binary available in the Ubuntu system.

To create a home directory while adding a user, you need to use <mark>-m</mark> along with the command <mark>useradd</mark>. Otherwise, home directory will not be created.

Use the below command to add user with home directory.

```
<pre class="wp-block-code">```
sudo useradd -m <var>username</var>
```
```

- **useradd** – Command to create user
- **-m** – Option to specify that home directory for the user must be created
- **username** – Your desired new user name

If you want to create a home directory in a custom location rather in the default location, you specify the directory path along with the option <mark>-d</mark>. Use the below command to create user with custom home directory location.

```
<pre class="wp-block-code">```
useradd -m -d <var>/Your/Custom/FolderPath</var> <var>username</var>
```
```

- **adduser** – Command to create user
- **-m** – Option to specify that home directory for the user must be created
- **-d** – Option to specify the custom location for the home directory
- **/Your/Custom/FolderPath** – Desired path of your home directory
- **username** – Your desired new user name

The command will create user and copy the files from the */etc/skel* directory to the specified users home directory. Within the home directory, the user can write, edit, and delete files and directories.

Now, you’ve created user with the home directory in Ubuntu. Next you’ll learn how to add a created user to a group.

## <span class="ez-toc-section" id="adding_user_to_group"></span>Adding User to Group<span class="ez-toc-section-end"></span>

First, you’ll create a new group. Use the below command to create a new group.

```
<pre class="wp-block-code">```
sudo addgroup <var>groupname</var>
```
```

- **sudo** – Keyword to execute the command with admin privileges
- **addgroup** – command to add a new group
- **groupname** – Your desired new group name

Now you can add user to group by using the below command. **This command will create new user in ubuntu and add it to the group specified.**

```
<pre class="wp-block-code">```
sudo adduser <var>username</var> <var>groupname</var>
```
```

- **sudo** – Keyword to execute the command with admin privileges
- **adduser** – command to add a new user
- **username** – Your desired new user name
- **groupname** – Group name to which the new user should be added

## <span class="ez-toc-section" id="adding_existing_user_to_existing_group"></span>**Adding Existing User to Existing Group**<span class="ez-toc-section-end"></span>

If you have user already created a user without adding to any group, you can add the existing user to group by using the <mark>usermod</mark> command. <mark>usermod</mark> command is used to modify the user.

```
<pre class="wp-block-code">```
sudo usermod -aG <var>groupName</var> <var>username</var>
```
```

- **sudo –** Keyword to execute the command with admin privileges
- **usermod** – Command to modify the user settings
- **-a** – **Append flag(Mandatory)**. To append the new group information. If this is not used, the user will be removed from the groups not specified in the above command.
- **-G** – Flag to denote the group names that the user needs to be added to.
- **groupname** – Group name to which the user needs to be added. Multiple groups can be specified and separated with comma **(,)**.
- **username** – Username to add to the group specified.

## <span class="ez-toc-section" id="adding_user_to_sudo_group"></span>Adding User to Sudo Group<span class="ez-toc-section-end"></span>

If you want to add a user to Sudo Group, you can use the below command.

```
<pre class="wp-block-code">```
sudo usermod -aG sudo <var>username</var>
```
```

If you want to add the current logged in user to a specific group, use the below command.

```
<pre class="wp-block-code">```
sudo usermod -aG <var>sudo</var> ${USER}
```
```

Here <mark>${USER}</mark> variable will be replaced with the currently logged in user.

## <span class="ez-toc-section" id="adding_users_to_sudoers_file"></span>Adding Users to Sudoers File<span class="ez-toc-section-end"></span>

Users and groups sudo privileges are defined in the file called sudoers. This file is located in <mark>/etc/sudoers</mark>.

You can add the users to this file to make the users as sudo user.

It is always recommended to use the **visudo** editor to edit this file. Because this command checks for any syntax errors when you modify and save the file.

Now use the below command to oped and edit the sudoers file.

```
<pre class="wp-block-code">```
sudo visudo /etc/sudoers
```
```

File will be opened. Scroll down to the end of the page and add the below line. Replace the username variable with your desired username to be added to sudoers.

```
<pre class="wp-block-code config">```
<var>username</var>  ALL=(ALL) NOPASSWD:ALL
```
```

Now the file will look like below.

```
<pre class="wp-block-code config">```
#
# This File MUST Be Edited With the 'visudo' Command as Root.
#
# Please Consider Adding Local Content in /etc/sudoers.d/ Instead Of
# Directly Modifying This File.
#
# See the Man Page for Details on How to Write a Sudoers File.
#
Defaults        env_reset
Defaults        mail_badpass
Defaults        secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"

# Host Alias Specification

# User Alias Specification

# Cmnd Alias Specification

# User Privilege Specification
root    ALL=(ALL:ALL) ALL

# Members of the Admin Group May Gain Root Privileges
%admin ALL=(ALL) ALL

# Allow Members of Group Sudo to Execute Any Command
%sudo   ALL=(ALL:ALL) ALL

# See Sudoers(5) for More Information on "#include" Directives:

#Includedir /etc/sudoers.d

#Username Will Be Added to the Sudoers File
<var>username</var>  ALL=(ALL) NOPASSWD:ALL

```
```

Press <mark>Ctrl + O</mark> to write out the file. This will check the syntax errors and save the files successfully if there in no syntax errors.

Now press <mark>Ctrl + X</mark> to exit the editor. You have succesfully added the user to the sudoers file.

## <span class="ez-toc-section" id="check_if_the_user_is_added_to_the_sudo_privilege"></span>Check if the User Is Added to the Sudo Privilege<span class="ez-toc-section-end"></span>

After adding the user to Sudo group or the Sudoers file, you may need to confirm if the user is succesfully given the sudo privileges. You can check it by using the below command.

```
<pre class="wp-block-code">```
sudo -l -U <var>username</var>
```
```

This will display the details of the sudo privileges available to the user as shown below.

```
<pre class="wp-block-code config">```
Matching Defaults entries for ubuntu on ip-158-31-87-230:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User ubuntu may run the following commands on ip-158-31-87-230:
    (ALL : ALL) ALL
    <var>(ALL) NOPASSWD: ALL</var>

```
```

For e.g. the NOPASSWD keyword shows, the user will be able to execute the commands or switch to the root user privilege without specifying the password.

If you want to **check if the current user is a sudo user**, then you can use the below command.

```
<pre class="wp-block-code">```
sudo whoami
```
```

You’ll see the below output if the current user is a sudo user.

Output

```
<pre class="wp-block-code config">```
root
```
```

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

To summarize, you have learnt how to

- Add user in Ubuntu
- Add user with home directory
- Create a user and add group in a single command
- Adding existing user to the existing group
- Add user to Sudo group
- Add user to sudoers file
- Check if the user is granted with the sudo privilege

Your user is created and ready for use. You shall login with the password you’ve selected during user creation.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)