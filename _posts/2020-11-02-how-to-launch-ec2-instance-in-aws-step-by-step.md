---
id: 2886
title: 'How to Launch EC2 Instance in AWS[Step by Step]?'
date: '2020-11-02T18:31:16+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://139.180.139.123/?p=2886'
permalink: /how-to-launch-ec2-instance-in-aws-step-by-step/
rank_math_seo_score:
    - '84'
rank_math_internal_links_processed:
    - '1'
rank_math_focus_keyword:
    - 'launch ec2 instance in aws'
rank_math_description:
    - 'In this tutorial, You''ll launch EC2 instance in AWS step by step using the AWS Free tier option alone with the storage and security configurations. '
bialty_cs_alt:
    - ''
rank_math_primary_category:
    - '16'
socialsnap_share_count_timestamp:
    - '2023-09-05 23:46:17'
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
    - '32'
ss_ss_click_share_count_linkedin:
    - '1'
image: /wp-content/uploads/2020/11/how-to-launch-ec2-instance-in-aws.jpg
categories:
    - how-to
tags:
    - aws
    - ec2
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

AWS EC2 is a virtual machine that provides secure, resizable compute capacity in the cloud. It provides dedicated server resources to host your web sites.

In this tutorial, you’ll launch EC2 instance in AWS step by step with the free tier eligible options.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

- Create an account in aws.amazon.com and login to the aws console.
- Ensure you have EC2 Creation rights in the AWS Account if you are using an account created by your organization.

## <span class="ez-toc-section" id="step_1_%e2%80%93_selecting_ec2_from_aws_console"></span>Step 1 – Selecting EC2 From AWS Console<span class="ez-toc-section-end"></span>

In this step, you will navigate the EC2 home page from the AWS console home page to create the EC2 Instance.

Click **Services** option available in the top left. You’ll see all the available AWS services. Select **EC2** under the **compute** section of the page.

<figure class="wp-block-image">![launch ec2 instance in aws  select EC2 service](http://149.28.53.131/wp-content/uploads/2020/11/null-1.png)</figure>You’ll be taken to the **EC2** home page. Select **Launch instance** button as shown below to launch an EC2 instance.

<figure class="wp-block-image size-large">![launch ec2 instance in aws select launch Instance option](https://139.180.139.123/wp-content/uploads/2020/11/launch-EC2-instance-in-AWS.jpg)</figure>## <span class="ez-toc-section" id="step_2_%e2%80%93_choosing_an_amazon_machine_image"></span>Step 2 – Choosing an Amazon Machine Image<span class="ez-toc-section-end"></span>

Amazon machine image is a template which contains the complete software stack such as Operating system, application servers and other applications which are necessary to host an EC2 Instance.

AMIs are provided by AWS, the user community and also other providers in the AWS Marketplace.

Here, you’ll select the **AMI** provided by Amazon AWS which is eligible for the free tier.

Select the option as shown in the image and click next to select the instance type.

<figure class="wp-block-image size-large">![launch ec2 instance in aws  shoosing machine image](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-select-machine-image-1024x380.jpg)</figure>## <span class="ez-toc-section" id="step_3_%e2%80%93_choosing_an_instance_type"></span>Step 3 – Choosing an Instance Type<span class="ez-toc-section-end"></span>

Instances are different types of servers which can run the applications.

Each instance type comprises CPU, memory, storage, and networking capacity which gives you the flexibility to choose the appropriate mix of resources for your applications.

In this tutorial, you’ll select **t2.micro** instance type which is free tier eligible. You get up to 750 hours of micro instances each month.

<figure class="wp-block-image size-large">![launch ec2 instance in aws  choosing instance type](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-select-instance-type-1024x431.jpg)</figure>**t2.Micro** has 1 virtual CPU, 1GiB memory with low to moderate network performance. This is sufficient to try out the AWS EC2. This is scalable at the later point of time. So if you need more computing capacity based on your growth, you can scale as required.

## <span class="ez-toc-section" id="step_4_%e2%80%93_configuring_instance"></span>Step 4 – Configuring Instance<span class="ez-toc-section-end"></span>

In this step, you’ll configure the selected instance such as the number of instances to be launched and other networking options for the instances.

Most of the options can be let as it is with the default value.

<figure class="wp-block-image size-large">![launch ec2 instance in aws  configuring instance details](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-configure-instance-details-1024x587.jpg)</figure>In section 7 on this page as marked in red, you can optionally **enable termination protection** to prevent accidental termination. If enabled, this instance cannot be terminated using the AWS Console.

You can also select **Monitoring** to enable cloudwatch detailed monitoring functionality.

This will Monitor, collect, and analyze instance metrics through Amazon CloudWatch where data is available in *1-minute* periods. The default monitoring with Cloudwatch is free, basic monitoring, where data is available in *5-minute* periods.

If you would like to have any packages installed by default in your instance, you can specify it in the **Advanced details** -&gt; **User Data** section. For e.g. If you would like to install WordPress by default in your EC2 instance, place the below script the User data section.

```
<pre class="wp-block-code config">```
yum install httpd php php-mysql -y
cd /var/www/html
wget https://wordpress.org/latest.tar.gz
tar -xzf wordpress-latest.tar.gz
cp -r wordpress/* /var/www/html/
rm -rf wordpress
rm -rf wordpress-latest.tar.gz
chmod -R 755 wp-content
chown -R apache:apache wp-content
service httpd start
chkconfig httpd on
```
```

- **yum install httpd php php-mysql -y** – To install httpd apache server, php, mysql servers. These are the packages required to run WordPress
- **cd /var/www/html** – to navingae to the html directory from where the apache will server files
- **wget https://wordpress.org/latest.tar.gz** – To download the WordPress latest stable version to your local directory
- **tar -xzf wordpress-latest.tar.gz** – To extract the wordpress zip file to the local directory
- **cp -r wordpress/\* /var/www/html/** – To copy the WordPress sources files to the HTML directory
- **rm -rf wordpress** – Remove extracted wordpress version
- **rm -rf wordpress-latest.tar.gz** – Remove the WordPress installation
- **chmod -R 755 wp-content** – To change the necessary permissions of the wp-content folder so that its accessible
- **chown -R apache:apache wp-content**  – To provide apache user the necessary access to the wp-content folder
- **service httpd start** – To start the Apache tomcat server
- **chkconfig httpd on** – To check if the apache server is working

With this, wordpress will be installed by default when you launch the ec2 instance.

Now, click next to configure storage to your instance.

## <span class="ez-toc-section" id="step_5_%e2%80%93_adding_storage"></span>Step 5 – Adding Storage<span class="ez-toc-section-end"></span>

In this step, you’ll configure storage for your instance. Storage is the place where the operating system data and the user data will be stored.

By default, a root volume is added with the default configuration, 8 GiB storage with the **general purpose SSD volume** type. Volume types are the different types of storage volumes available for different purposes. To know more about other volume types, read about [different volume types available](https://docs.aws.amazon.com/console/ec2/ebs/volumes/types).

You can increase or decrease the size of the storage volume in the **size** column. Upto 30GB of EBS General Purpose (SSD) is eligible for the free tier.

<figure class="wp-block-image size-large">![launch ec2 instance in aws - adding storage](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-add-storage-1024x424.jpg)</figure>Next you’ll configure what should happen to the storage volume when this instance is deleted.

**Delete on Termination** is enabled by default. This will delete this storage when you terminate the instance. If you would like to retain this storage *even after deleting* this instance, unselect **Delete on Termination** option.

Additionally, if you would like to enable **Encryption** of the data in this volume, you can enable it in the **Encryption** column by selecting the *default Key Value* created by amazon. You can also create keys for encryption by yourself.

Now, you have completed configuring the storage for your instance. Click next to add tags.

## <span class="ez-toc-section" id="step_6_%e2%80%93_adding_tags"></span>Step 6 – Adding Tags<span class="ez-toc-section-end"></span>

In this step, you’ll add tags to your instances and storage volumes.

Tags are used to easily categorize or group the resources in the aws. It consists of the case sensitive key value pair.

If you would like to tag your instance and storage, add a tag and assign to this instance. If you don’t want to group this instance, you can leave it empty.

<figure class="wp-block-image size-large">![launch ec2 instance in aws - adding tags](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-add-tags-1024x428.jpg)</figure>Now, click next to **configure security** group.

## <span class="ez-toc-section" id="step_7_%e2%80%93_configuring_security_group"></span>Step 7 – Configuring Security Group<span class="ez-toc-section-end"></span>

Security group is a set of firewall rules to control the traffic for your instance. In other words, You can define which IP address is allowed to access your instance via a defined port.

You can create a security group by adding a security group name and security group description. This will save the security group and it can be reused while creating other instances.

By default, a rule with ***ssh*** type, port ***22*** with source ip ***0.0.0.0/0*** is added.

SSH is a type which is used to connect to a linux instance using the port 22. 0.0.0.0/0 means it **will allow all IP addresses** to access your instance using the port 22.

If you are planning to host a website in this instance and make it visible to the public, you can add a rule **https** type with port **443** with source ip as **0.0.0.0/0**. This will allow **any IP address** to access this instance with the port 443 with https instance.

<figure class="wp-block-image size-large">![launch ec2 instance in aws  - configuring security group](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-consfiguring-security-group-1024x359.jpg)</figure>Now, you have **configured security** group. Click next to review your instance settings and finally launch it.

## <span class="ez-toc-section" id="step_8_%e2%80%93_reviewing_and_launching"></span>Step 8 – Reviewing and Launching<span class="ez-toc-section-end"></span>

This is the final step before launching your instance.

You can review the AMI details, Instance type, security groups, instance details, storage, tags to ensure if its correctly configured for your requirement.

If you’re ok with the configuration details, you can click **Launch**.

This will ask you to create a new key pair which can allow you to connect to your instance securely.

Select the option **Create a new key pair** option in the first combo box. Enter name for your key pair and click **Download** to download your private key. The private key will be downloaded in pem format which you can use to login to your instance.

<figure class="wp-block-image size-large">![launch ec2 instance in aws  - creating a key pair ](https://139.180.139.123/wp-content/uploads/2020/11/launch-ec2-instance-in-aws-launch-instance.jpg)</figure>If you would like to proceed without a keypair, you must know the password built into the Amazon Machine image you have selected in the step-1 of this tutorial. However, it’s recommended to use the key pair for authentication for the better security of your instance.

Finally click **Launch** to launch the instance.

Now, your instance will be launched based on the configuration you’ve selected.

Check how to [connect to your instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstances.html?icmpid=docs_ec2_console) in various ways.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you have launched an EC2 instance in aws step by step with the free tier eligible options. You can go ahead and host any dynamic or static websites in this instance.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1604319648368">### how to launch linux ec2 instance in aws?

<div class="rank-math-answer ">Select the Linux Amazon Machine image in the step 2 of this tutorial. Then you can launch Linux EC2 instance.

</div></div><div class="rank-math-list-item" id="faq-question-1604319703639">### What is the cost to launch ec2 instance in aws marketplace?

<div class="rank-math-answer ">One year free tier is available when you do it by following this guide. However, if you are using the lightsail option available in AWS, then one month is free and thereafter, you’ll be charged minimum 5$.

</div></div><div class="rank-math-list-item" id="faq-question-1604319817547">### What is the cheapest EC2 instance?

<div class="rank-math-answer ">T2 instances are a low-cost, general purpose instance type that provides a baseline level of CPU performance with the ability to burst above the baseline when needed.

</div></div><div class="rank-math-list-item" id="faq-question-1604320087331">### How long does it take to start an ec2 instance?

<div class="rank-math-answer ">Linux instances are frequently ready **60-90 seconds** after launch. Windows instances take considerably longer because the AMI has been configured for `sysprep`, which involves a reboot.

</div></div><div class="rank-math-list-item" id="faq-question-1604320138796">### Does a stopped ec2 instance cost money?

<div class="rank-math-answer ">No AWS doesn’t charge for the stopped EC2 instance. However, you’ll be charged for the other resources such as **storage** you have attached to your instance.

</div></div><div class="rank-math-list-item" id="faq-question-1604320215747">### Can I restart a terminated ec2 instance?

<div class="rank-math-answer ">No, you cannot restart the terminated instance. When you terminate, your instance is destroyed.

</div></div><div class="rank-math-list-item" id="faq-question-1604320276102">### how to **create amazon** ec2 instance **windows**

<div class="rank-math-answer ">Select the windows Amazon Machine image in the step 2 of this tutorial. Then you can launch Windows EC2 instance.

</div></div></div></div>