---
id: 4491
title: 'How to Connect to EC2 File Directory Using Filezilla and SFTP &#8211; Comprehensive Guide'
date: '2021-01-18T22:05:21+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4491'
permalink: /connect-to-ec2-file-directory-using-filezilla/
rank_math_seo_score:
    - '84'
rank_math_focus_keyword:
    - 'connect to ec2 file directory using filezilla,upload files to ec2 instance,connect filezilla using pem file,Filezilla download,access files on aws ec2'
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
    - 'Filezilla is open-source software for FTP, FTP over TLS (FTPS), and SFTP clients. In this article, you''ll connect to EC2 file directory using Filezilla and SFTP.'
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
    - 'off'
socialsnap_share_count_timestamp:
    - '2023-09-15 09:59:32'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '7'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"851aa2c37ae3ad5b08ca151b21c9ccf4";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - aws
    - ec2
    - filezilla
    - sftp
    - ubuntu
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

In this article, you’ll download and install Filezilla, connect Filezilla using <mark>PEM</mark> file and SFTP from your windows computer.

You’ll connect to EC2 file directory using Filezilla, access files on AWS EC2 file directory and upload files to EC2 instance, download files from EC2 instance using FileZilla.

[Filezilla ](https://filezilla-project.org/)is open-source software for FTP, FTP over TLS (FTPS), and SFTP clients. It also contains Filezilla servers (supports only in Windows). Filezilla is one of the AWS SFTP clients. Some of the other AWS SFTP clients are Cyberduck, WinSCP, and OpenSSH.

Filezilla supports various features such as,

- Overwrite existing files **only** if f*ile size does not match* or *the file is newer*.
- Supports IPv6
- Ability to pause and continue active transfers etc.

To know about more features of Filezilla visit [this wiki page](https://en.wikipedia.org/wiki/FileZilla#Features).

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Before you start, you’ll need the following.

- If you do not have servers in the cloud, Create an AWS EC2 Ubuntu server instance by following the guide [How to launch an EC2 Instance.](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/)
- **\[Important\]** – Update the packages list in the server which is upgrade-able using **`sudo apt update`**
- **\[Important\]** – Upgrade the packages in the server to the latest versions using **`sudo apt upgrade`**

## <span class="ez-toc-section" id="downloading_and_installing_filezilla_client"></span>Downloading and Installing Filezilla Client<span class="ez-toc-section-end"></span>

In this step, you’ll download Filezilla and install it (You can skip this step if Filezilla is already installed).

First, go to the [Filezilla Official Website](https://filezilla-project.org/download.php).

Next, **Press the Filezilla Download button** shown in the below image.

<div class="wp-block-image"><figure class="aligncenter size-large is-resized">![](http://149.28.53.131/wp-content/uploads/2021/01/2.png)<figcaption>Figure 1 Filezilla Download Button.</figcaption></figure></div>Next, you’ll see a window popup as shown below. In the option select the Filezilla ***Download*** button (Option I).

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/3-1.png)<figcaption>Figure 2 Select the free version of Filezilla.</figcaption></figure></div>Setup binary file will be downloaded. Go to the **“Downloads”** folder and *double click* the downloaded binary file. (If you are asked, “*Do you want to run this file?*“, Press ***“Yes”***.)

Next, You can see the *installation window* opened as shown in the image below.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/4.png)<figcaption>Figure 3 Filezilla License agreement and privacy policy.</figcaption></figure></div>Now, Read the *“Licence agreement and privacy policy”* and then press ***“I agree”***.

Next, you’ll be asked whether you wish to install Filezilla for all users. It is recommended to install it using the option, **only for me** (the current user) if more than one person will be using the system.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/5-1.png)<figcaption>Figure 4 Selecting user in Installation options.</figcaption></figure></div>Press the **Next** button, after selecting an option.

You can leave other settings default and Press the **Next** button.

Next, choose the directory you wish to install Filezilla and Press the **Next** button (If you are asked to install any additional components, Press the **Decline** button.).

Finally, Press the **Finish** button. You’ve successfully downloaded and installed Filezilla Client.

In the next step, you’ll customize Filezilla to support SFTP connections.

## <span class="ez-toc-section" id="setting_up_sftp_and_connect_filezilla_using_pem_file"></span>Setting Up SFTP and Connect Filezilla Using PEM File<span class="ez-toc-section-end"></span>

In this step, you’ll set up SFTP in Filezilla.

*SFTP* stands for ***S**SH **F**ile **T**ransfer **P**rotocol*. It is a network protocol that provides file access, file transfer, and file management over any reliable data stream.

Privacy Enhanced Mail (**PEM**) files are concatenated certificate containers frequently used in certificate installations when multiple certificates form a complete chain and imported as a single file.

First, **Open your Filezilla Client** installed in the previous step.

Next, Press **Edit** in the Menu.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/7.png)<figcaption>Figure 5 Setting up SFTP in Filezilla – Step 1</figcaption></figure></div>Press **Settings** in the sub menu.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/7-1.png)<figcaption>Figure 6 Setting up SFTP in Filezilla – Step 2</figcaption></figure></div>Next, select **SFTP** under **Connection** from the Select Page in the left tab.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/8.png)<figcaption>Figure 7 Setting up SFTP in Filezilla – Step 3</figcaption></figure></div>Next, Press the **Add key file** button. Go the folder containing the *.pem* file of your EC2 instance. **Select** the *.pem* file.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/9-1.png)<figcaption>Figure 8 Setting up SFTP in Filezilla – Step 4</figcaption></figure></div>You can see that the key file is added successfully for your SFTP connection.

Finally, Press **Ok**.

In the next step, you’ll connect to EC2 file directory using Filezilla and SFTP.

## <span class="ez-toc-section" id="creating_a_new_site_and_connect_to_ec2_file_directory_using_filezilla"></span>Creating a New Site and Connect to EC2 File Directory Using Filezilla<span class="ez-toc-section-end"></span>

In this step, you’ll **create a new site in Filezilla** and connect to EC2 file directory using Filezilla and SFTP.

A new site helps you to connect to your EC2 instance easily by storing IP addresses and Key files in a new site.

You can reuse this site later by navigating to <mark>File &gt; Site Manager &gt; My Sites</mark> and Press the **connect** button whenever you want to connect to your EC2 instance.

To create a new site, Go to **File** Menu.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/10.png)<figcaption>Figure 9 Creating a new site</figcaption></figure></div>Next, Press the ***New site*** Button (as shown below in Figure 10) and **name** your site. You can see that site is added under *My Sites* as shown in the image below.

<div class="wp-block-image"><figure class="aligncenter size-large">![Creating a new site to Connect to EC2 File Directory using Filezilla.](http://149.28.53.131/wp-content/uploads/2021/01/11-1.png)<figcaption>Figure 10 – Creating a new site to Connect to EC2 File Directory using Filezilla.</figcaption></figure></div>Next, set the following parameters in the corresponding field as shown below (in the Figure 11).

**Protocol**: SFTP

**Host**: Public DNS name or IP address of the EC2 instance.

**Port:** 22

**User**: Username is different for the different **A**mazon **M**achine **I**mages as given below. Enter the user name based on the AMIs of your EC2 Instance.

- Linux AMI- **root**
- Ubuntu AMI- **ubuntu**
- Default Linux AMI- **ec2-user**

<div class="wp-block-image"><figure class="aligncenter size-large">![Connect to EC2 File Directory using Filezilla.](http://149.28.53.131/wp-content/uploads/2021/01/12.png)<figcaption>Figure 11 – Connect to EC2 File Directory using Filezilla.</figcaption></figure></div>Finally, Press the **Connect** button.

You can verify if the connection is established between Filezilla and EC2 file directory by seeing the **Remote site** column in Filezilla. This is shown in the below image (Figure 12).

<div class="wp-block-image"><figure class="aligncenter size-large">![Figure 11 - Connect to EC2 File Directory using Filezilla.](http://149.28.53.131/wp-content/uploads/2021/01/13.png)<figcaption>Figure 12 – Connection established.</figcaption></figure></div>In the next step, you’ll learn how to transfer files between EC2 file directory and local machine and also access files on AWS EC2 file directory.

## <span class="ez-toc-section" id="transferring_files_between_your_local_machine_and_ec2_file_directory"></span>Transferring Files Between Your Local Machine and EC2 File Directory <span class="ez-toc-section-end"></span>

In this step, you’ll download files from EC2 instance and upload files to EC2 instance using Filezilla to your EC2 file directory.

You’ve established a connection with the EC2 file directory in the previous step. With that, Downloading and uploading files is pretty straightforward.

First, you’ll learn how to download files. Navigate to the folder (in the **Remote site** column) that you want to download.

Next, **navigate** to the folder (in the **Local site** column) where you want to download the files from EC2.

Next, **right-click** the folder name (in the **Remote site** column). You can see a **Download** button in the options as shown in the image below.

<div class="wp-block-image"><figure class="aligncenter size-large">![](http://149.28.53.131/wp-content/uploads/2021/01/14.png)<figcaption>Figure 13 Download files from EC2 File directory.</figcaption></figure></div>Finally, Press the **Download** button. You can verify if the files are downloaded by navigating to the folder using file explorer.

Similarly, you can upload the files to your EC2 file directory by **Navigating to the right locations in your Remote and Local site**.

Next, **Right-click** on the local site folder.

Finally, press the **Upload** button. Files will be uploaded.

You’ve transferred files to and from the EC2 file directory into your local system.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, You’ve successfully installed Filezilla on your local machine. You’ve created a new site in Filezilla and used it to connect to your EC2 file directory using SFTP. You’ve also learned how to download and upload files to the EC2 file directory from your local machine.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faqs"></span>FAQs<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1610977564132">### How to access files on Amazon EC2

<div class="rank-math-answer ">You can access your Amazon EC2 files using Filezilla. It establishes an SFTP connection to your EC2 instance.

</div></div><div class="rank-math-list-item" id="faq-question-1610977602263">### How do I connect FileZilla to ec2?

<div class="rank-math-answer ">You can configure a new site in Filezilla using your Host, Port, PEM file, and user. Then simply login to the new site with your password.

</div></div><div class="rank-math-list-item" id="faq-question-1610977967236">### Where is site manager in Filezilla?

<div class="rank-math-answer ">The site manager in Filezilla is under the File menu.  
File &gt; Site manager

</div></div><div class="rank-math-list-item" id="faq-question-1610985757821">### Amazon AWS Filezilla transfer permission denied

<div class="rank-math-answer ">To allow write access to the directory(E.g. public web directory) for the user ***ubuntu***. . Try the following command on your server.   
<mark>`sudo chown -R ubuntu:ubuntu /var/www/html sudo `  
`chmod -R 755 /var/www/html`</mark>

</div></div><div class="rank-math-list-item" id="faq-question-1610987500898">### How do I view EC2 files?

<div class="rank-math-answer ">You can view your EC2 files using Filezilla. Once you established a connection with EC2 instance, you will be able to view your files in the **Remote site** section.

</div></div></div></div>