---
id: 3478
title: 'How to Host a Static Website on AWS S3 [Step by Step]'
date: '2020-12-03T08:40:29+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3478'
permalink: /host-a-static-website-on-amazon-s3/
rank_math_seo_score:
    - '76'
bialty_cs_alt:
    - ''
ss_social_share_disable:
    - ''
rank_math_internal_links_processed:
    - '1'
rank_math_primary_category:
    - '16'
rank_math_focus_keyword:
    - 'host a static website on aws s3,host a static website on aws'
rank_math_description:
    - 'In this tutorial, you''ll host a static website on aws s3 without using custom domain name. '
socialsnap_share_count_timestamp:
    - '2023-09-17 05:45:09'
ss_total_share_count:
    - '0'
tcb2_ready:
    - '1'
ss_ss_click_share_count_linkedin:
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
    - '25'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"a5c57ecfe6aa476565c4d1becaa370df";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - aws
    - s3
    - 'static webstie'
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

AWS S3 is an object-based storage service that provides highly scalable, reliable, fast, inexpensive data storage infrastructure. It allows you to store, retrieve and modify data from anywhere as long as you are connected to the internet.

Static hosting is hosting static web pages where you will be uploading only HTML, CSS, and Javascript files. In contrast to Dynamic hosting where you can manipulate these files from the server and are able to add user interactions.

You can also host static files for free from sources like Github.

In this tutorial, you’ll host a static website using AWS S3 **both without and a custom domain name**.

When you’re finished, you’ll be having a static website in AWS S3 without or with a custom domain.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

– Create an account in aws.amazon.com and login to the AWS console.

– You should have rights to use S3 service in the AWS Account if you are using an IAM account created by your organization.

## <span class="ez-toc-section" id="step_1_%e2%80%93_selecting_s3_from_aws_console"></span>Step 1 – Selecting S3 From AWS Console<span class="ez-toc-section-end"></span>

In this step, you will navigate to the S3 (Simple Storage Service) page from the AWS home page to create a S3 Bucket.

First, Click **Services** option available in the top left. You’ll see all the available AWS services.

Next, Select **S3** under the **Storage** section of the page.

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/F12WGGEp9NiOXzjp5SWtDxud7P2E_45ZxjShI0RrHcXphyT7NAa807txitZrEVeuto3i3W92kO00N1MPCWlWoFmcshs10BmJKq_twLL8KV-MM52jbRp2Zv7R7PbUFzJoWChrTvsO)</figure>You’ll be taken to the S3 home page. In the next step, you will create a S3 Bucket.

###  

## <span class="ez-toc-section" id="step_2_%e2%80%93_creating_your_s3_bucket"></span>Step 2 – Creating Your S3 Bucket<span class="ez-toc-section-end"></span>

In this step, you will create and name your S3 bucket. A bucket is a container for storing objects in Amazon S3. Any file you upload will be saved as an object in this container.

First, In the S3 home page, select the **Create bucket** button as shown below to configure a new S3 bucket. This bucket will be holding the files of your static website.

<figure class="wp-block-image">![host a static website on aws s3](https://lh5.googleusercontent.com/MCUm23VEu8Dd-ce7lsv4iTlPMbSDbH3YQHL89-I-Q4NCj4rGVxWCqkIBosRFcXmz59j6wRRz9zHRGWF3-RmnxCMTV9lz6kQk7By5LrwDSqxNjHCP4tn_kJ4hlNWz_J0VOmmYAyMR)</figure>You’ll be taken to create a bucket page in S3.

Next, choose a **name** for your bucket and enter it in the box shown below. This name will be used for viewing your static website once it has been hosted. Bucket name must be unique and must not contain spaces or uppercase letters.

If you’re going to use your custom domain name then enter the custom domain name as bucket name. (eg. [*www.guidingdog.com*](http://www.guidingdog.com), where guidingdog is the domain name).

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/fDawZrx5HGCuRNyvYK3LXbcozZYL6uRXPYqUrk1RQP1E5QiUhEDQGPJQF2iV5h6su5E1f5hFF1-1VMBkzJjmEduFC_pJUEOgcJswY2AzL7tHZFPgI8N01VKGykVTY3w6Iptl8nWc)</figure>You have created a S3 Bucket with its name.

In the next step, you’ll configure the Bucket for public access.

## <span class="ez-toc-section" id="step_3_%e2%80%93_configuring_your_bucket_for_public_access"></span>Step 3 – Configuring Your Bucket for Public Access<span class="ez-toc-section-end"></span>

In this step, you’ll assign public access to your S3 Bucket. So that the website can be viewed by anyone. If you don’t assign public access, the objects can only be viewed from the AWS console and it will not be accessible for the public via the browser.

First, **uncheck** the **Block all public access** checkbox. Next, **acknowledge** that you are sure to unblock all public access by **checking** the **acknowledge c**heckbox.

Now your bucket is ready for public access.

<figure class="wp-block-image">![host a static website on aws s3](https://lh6.googleusercontent.com/zFi_dkJYfwzlr7QyC1O4gydy-60EdGUFSH8-WvkRlh4aJEbZvjPIblh6HoU7ZwVBPH3AkjSX8ONra9ztI7NGMoU761is9SqxURblRd-T3yOXSfRmULuehz-AWJ3-oFWRaLxl4aKy)</figure>Since your bucket is configured for public access, you can leave the remaining settings to default as this is not important for static website hosting.

Finally, scroll to the bottom of this page. you’ll find the **Create bucket** button. Click it. Your bucket will be created.

You will be redirected to the S3 home page after the bucket is created. Your S3 Bucket with public access is created.

![](https://lh4.googleusercontent.com/0yKEUTskUKO8313cg2hecWYTVc4VWq3OnjXsbT92J-02Fv4XDDKv6smiuZeFeq0XfcVQDE5ZS2v1FPC5v7E_k9cmxPEBnacnOCi4OLqDHy5MgMqzSo7gJQzdrlnpQOLKcN6Fis1U)

In the next step, you will enable the static hosting in your S3 Bucket.

###  

## <span class="ez-toc-section" id="step_4_%e2%80%93_enabling_static_website_hosting_in_your_s3_bucket"></span>Step 4 – Enabling Static Website Hosting in Your S3 Bucket<span class="ez-toc-section-end"></span>

In AWS S3, you can directly declare objects in a bucket as a web page by enabling static hosting.

In this step, you’ll enable static hosting functionality to your bucket that you created in the previous step. Your bucket will be listed in the buckets as shown in the image below.![](https://lh5.googleusercontent.com/zKTCfnpX3wDSjGGjlCJLu64dDTFtywe7ehDKzjnz4JP6QYTEX6Lb86db6CIGDSkn9dkXeP5vkXg-gh2_qSujxY2lKRGtTLjeYAKBqnqKsHnlwG6MA31raDWoI0rJKsz2Il0AC3Om)

First, click on the bucket name.

You’ll be taken to the bucket overview page as shown in the image below.

<figure class="wp-block-image">![host a static website on aws s3](https://lh3.googleusercontent.com/BpvUfMSED68jeIrky2umT5dBVMR61I9qdmIBZgR96fS8TyvfUd_STV-7z7_6uDdHWIbtDoEhc2fPm722Of717q23rDCdOQVk6e4kPdsEmXeIYuZCXcgri1l_Dm0lgg0YGD7I32hK)</figure>Next, **Select Properties** from the option tab.

Next, in the properties tab, **Scroll to the bottom** of the page where you’ll find the static website option. By *default* static hosting will be **disabled**. You have to enable this to support static hosting.

Click on the **Edit** button.

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/e9lPSxZFOt5cE8EbbMxvs8poFdyEJV8bB6nWEcqS1wOD0T_vKhO7mzWhkx7KOj_MoUMIr1_8FzRM3844eQHtUkCUTtCAdGex7WoYNxJaiXkXNhkjmlEGbVIutNrJk1OYGSUz1QQr)</figure>You will be taken to the **“Edit static website hosting”** page.

Finally, select **Enable** in the radio buttons.

<figure class="wp-block-image">![host a static website on aws s3](https://lh6.googleusercontent.com/lFBGg49loJhinJ7M9TfL739H5306UTSeMCheOPLJWRd4-PjvQBHfhQEllL1hHxLriDV3M1PHbxiVwCD5syKxXOaNfxNYNOZVESZ47YfF2btppMct47vbktgPUNJnL21JjEmGqde0)</figure>Static Hosting is now enabled in your bucket. As a next step, you will edit the static hosting properties and choose your index and error files.

## <span class="ez-toc-section" id="step_5_%e2%80%93_editing_the_static_website_hosting"></span>Step 5 – Editing the Static Website Hosting<span class="ez-toc-section-end"></span>

In this step, you’ll add your index and error files and complete adding static hosting functionality to your S3 bucket. On most web servers, if the browser requests a URL that maps to a local directory, the server will check that directory for a file called *index.html, index.htm* (or on some servers, *default.html*). If found, the server will return that file. If not found, the browser lists the files in the directory.

Similarly, if the browser requests a URL that is **not** in a local directory, the server will return the *404.html*

Make sure you enter the correct name for the index document because this file will be first loaded from the bucket.

You’ll see that editing options are enabled.

First, you’ll select the **Hosting type** as **Host a static website.**

Next**,** In the Index document textbox type **“index.html”** and in the error document textbox type **“404.html”.**

<figure class="wp-block-image">![host a static website on aws s3](https://lh3.googleusercontent.com/kAKOD-yfZWeSyel1AQ6kIuQzTcZe3buD8c3wuqhbSLruCOjMmAh7LX4kNZl-lBSrKCsGPA2ahsxEUNMqFM0TaVSoQl9W7caCmhexgovGkz99Dwms_0j8_zhzFT8vGPxilLafpE6Z)</figure>You don’t need any redirection rules for your site. So you’ll leave the redirection rules blank and click the **“Save changes”** button.

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/Evx9CIQY-iLPywK9ZgrmcHzTqDkW83KFJTbk5bdtaCtujIf7OHmPaollGLv_e9unHXaZXQ9X5PiLXjJO5pKAO2Lte_hxt6aYwX8A698QWSZyutBhnvJZMOky3EsZvsRjiIY5D7zO)</figure>Now, you have enabled static hosting for your website. You’ll find a URL for your static website under the static hosting column.

In the next step, you will add bucket policy.

## <span class="ez-toc-section" id="step_6_%e2%80%93_adding_bucket_policy_for_your_s3_bucket"></span>Step 6 – Adding Bucket Policy for Your S3 Bucket<span class="ez-toc-section-end"></span>

In this step you will configure the permissions to add a bucket policy. You will add a **bucket policy** to a **bucket** to grant other **AWS** accounts or **IAM** users access **permissions** for the **bucket** and the objects in it. Object **permissions** apply only to the objects that the **bucket** owner creates.

First, click **Permissions**.

Next, Scroll down to Bucket policy and **add** the following **bucket policy**. Make sure that you **change** the [www.guidingdog.com](http://www.guidingdog.com) under “**Resource**” to **your Bucket name.**

```
<pre class="wp-block-code config">```
{
    "Version": "2012-10-17",
    "Id": "Policy1548223592786",
    "Statement": [
        {
            "Sid": "Stmt1548223591553",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::<var>www.guidingdog.com</var>/*"
        }
    ]
}

``` 
```

Finally, Press the **Save Changes** button

In the next step, you will upload the files for static hosting.

## <span class="ez-toc-section" id="step_7_%e2%80%93_uploading_files_for_static_website_pages_in_your_bucket"></span>Step 7 – Uploading Files for Static Website Pages in Your Bucket<span class="ez-toc-section-end"></span>

Make sure you have static website files available with you before you proceed. If you don’t have static website files you can[ ](https://github.com/gnanaganesh1999/static-hosting-in-aws-s3-without-custom-domain)download from here.

In this step, you will upload the files to the S3 bucket that will be hosted on your static website.

First, select the **Objects** tab from the options.

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/mUJf0twbULO4B72MOphI8baY2KZqSc904c1G41SJP0OlxTPgYKd1sPqKQWxhj9Imwg5qUMZkw-91bhjw1Sl8m8nQSTxv_CDuqwB1NiChNVzWy4AE3D8ZrVXdNTfipvZGdAJToos8)</figure>Next, click **Upload** in the table below.

<figure class="wp-block-image">![host a static website on aws s3](https://lh5.googleusercontent.com/5ieNwbHOApRfE_1hFMZ170cAY91DWJdcnwMm1LZdgvAYLACEU3DjLbySiNkdnl5B5Etrdlv2CalQ2rUJrYu4Ok3P2XVUcEBKa6Rx7Fryrn19GOjU6XShLTA5zNwytsMLWHAtJphX)</figure>You’ll be redirected to the upload page. You can add files one by one or simply drag and drop them in the box as shown in the image.![](https://lh4.googleusercontent.com/3pnW8oKK7qoPdR_XGk-rGuI0QIu_kBqNt6w1ZSobAYBS0s4GzlzAI9TptHybsLPkibaYrtLHvjd7Hn3pyvJWMSHaqFstv04nY5UdmToNgVassEEAFhFoYVrOYykRZqPPMX1JJ10w)

Next. press the **Upload** button at the **bottom** of the page.

<figure class="wp-block-image">![](https://lh6.googleusercontent.com/mUS9wsZwnyJiyLE9kdUZ7n_bNynldqKA_FchJbg-uJghYoCt7ncRc0GvAo5S-WKyG2kfLNilU7uoONQcNPquDO0RtWgA6msI97O21N_KSypoh2x8MBtxWZBqpba1s0-9MNwawCvV)</figure>You can see the status of the files, whether it has been uploaded successfully or not.![](https://lh5.googleusercontent.com/ZElQHpZG0jUyDVpzyp6z7QaHOjYfIIIKCgfau4Dy0nf3x9nSc057j-gKtwkdM5x1Gjjetdg5j4zZfy6vuavbz3xwCGA8KYULELc7B9FHkin81wmHfntMMZEN1k9yPZPji_kZe_Jy)

You can come back to the Buckets page by pressing the Exit button at the **top right corner** of the page.

<figure class="wp-block-image">![host a static website on aws s3](https://lh3.googleusercontent.com/GQRAimVs-Q6oZ1Dwkl3FP3l4as-NpJ0FR2wft4CJX5NgZaEe7X8-0VMEqHXCAP0z_fJ8KDuy2aEzhSastP-fD5NcSziJCssIl7mZ1YOnXmAH_pWOq-WyNhrDk63UBVdaE7rqVvjl)</figure>You’ll be redirected to the Bucket home page. You have successfully uploaded the files in your S3 bucket.

In the next step, you’ll declare the objects in your bucket as public.

## <span class="ez-toc-section" id="step_8_%e2%80%93_making_the_files_in_your_s3_bucket_as_public"></span>Step 8 – Making the Files in Your S3 Bucket as Public<span class="ez-toc-section-end"></span>

In this step, you’ll make files in your bucket as public. This step is important because it helps in loading up the file when the user visits your website.

First, **Select all** files and Press the **Actions** button.![](https://lh4.googleusercontent.com/W__gTv86ZV2xiPNflg3REaBMdx4g3U9bljVxaIYqR12zO4ai56Apegc648KIzsU5d81o-nQVDiWnRXjRQZsBYJ-3sTFlV7CmUzi405CVlAjyuNmA689HhmiRv1TbwvNpFICKa-EV)

Next, from the dropdown, **Select make public** option

<figure class="wp-block-image">![host a static website on aws s3](https://lh4.googleusercontent.com/TXMeYAvdWq4sfYMMB-_PmBJTyha3XjpGmVO1Bc26-U427OMwcyJ3WBOqFv7Qo7K3r-HLcTzw13Kn7pKuA21LXtOw6uN1B_HlVZ2JQgN9lFC214lldUvMqYeqA3n0W0o75slVebiw)</figure>You’ll be redirected to the **“Make public”** page. Next, press the Make **public** button at the bottom of the page.

<figure class="wp-block-image">![](https://lh4.googleusercontent.com/-pVvb62ANvImJ5Bm_9zdYnuGRbDKynCUSteYv9_jvrN7Y0XqV8lByDuw6PYpRt7F_Hv10cG5kYZI8Eu9Dbpwgej3qKNTOsSDnh3WQTXkzIhYN5j4GhH7E4zhdOFhZq1WkYv0_YLi)</figure>Finally, press the **Exit** button at the top right corner of the page to go to the buckets page.

<figure class="wp-block-image">![](https://lh4.googleusercontent.com/D94kgPNdL7Bv3xk7GaesiUeemfHVx5UjS52vR39YJr3MoqhK3RX8cIFrFvaicw-0M4qs95RhAJC5wCnpltQ-GzhkeH-Xb41089K-jfuqwklNd0utjc1vQNV4yD-Q3FEgOlFFFhiH)</figure>In this step, you have made your files public. In the next step, you can view your website from the URL given in the static hosting properties of the bucket.

If you are using custom domain, follow Step 9 &amp; 10 or you can skip through to Step 11

## <span class="ez-toc-section" id="step_9_%e2%80%93_configuring_route_53_for_custom_domain_name_optional"></span>Step 9 – Configuring Route 53 for Custom Domain Name \[Optional\]<span class="ez-toc-section-end"></span>

In this step, you’ll set up the routing to your domain. Google Domains is taken as an example but the steps followed are straightforward and can be followed in your domain providers.  
First, Click **Services**, then, search **Route 53** , and Click it.

Next, Click **Create hosted zones**

Next, type your domain name **without** www (**eg.** guidingdog.com).

Next, Click the **Create Record** button.

Select **Simple routing**.

Next, Create a record with *www* as subdomain. Select **Alias to S3 endpoint,** then, select your **region** and **bucket.** Your configuration looks similar to this.

**Next, create another record, this time, leave the subdomain empty.**

You have successfully created the route settings using Route 53. Make sure you note the name servers you have in your Route 53 Dashboard. You can find it under **Hosted Zone Details.**

 In the next step, you will add the nameservers in Google Domain.

## <span class="ez-toc-section" id="step_10_%e2%80%93_adding_name_server_to_the_dns"></span>Step 10 – Adding Name Server to the DNS<span class="ez-toc-section-end"></span>

In this step, you will configure the DNS of your provider and add custom name servers. Google domains is taken for example.

First, Go to **DNS.**

Next, select **Use custom name servers.** Press the **‘+’** button 4 times.

From the previous step under Route 53, you should have the name servers. Enter the name servers in the text fields.

Finally Click **Save**.

Now you are ready to view your website. Note that the changes you made may take some time to reflect. You can check the status in this [link](https://www.whatsmydns.net/).

## <span class="ez-toc-section" id="step_11_%e2%80%93_accessing_your_website"></span>Step 11 – Accessing Your Website<span class="ez-toc-section-end"></span>

In this step, you will visit your website and confirm that you have successfully hosted your website using S3 Bucket.

If you configured to use custom domain name and followed through Step 9 and Step 10, then, type your domain name as <mark>example.com</mark>. You will be taken to the website that is stored in Bucket. If you are not using Custom Domain Name follow the below steps)

First, select the **Properties** tab from the options.![](https://lh6.googleusercontent.com/phJdP8J5vLgxcF7jcwgwTzDEjnDAr3qX7tVqjEWgq-BAhq5ipumPlZ0bADZ-wHgnZZ3ouEj1gyRQPOuf6ZqDvbZOxDNd6yIZFESsrq12JZrB7mGUUL_J1MIeQuFAqn4fTefgpYVe)

Next, **Scroll to the bottom** of the page where we will find the **link** under the **Static website hosting**![](https://lh5.googleusercontent.com/VXY_1qxsRIzbqjy4Tk3vbhqmI-QOKcgD8jjD2z6iHmT7zFNJwos4Vo4tIOk6efFV1v7QFvT7B88dpBriU6Op5wNn0-tlqb61EEjDEJVtKxR-tZNYMfdjCXD72LjaLhbJVq0tBLqu)

Finally, **Click the link** and you’ll be redirected to the site that is uploaded by you.

Now, you can see that your site is loaded from the URL which confirms you have successfully hosted your static files in AWS S3.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this tutorial, you have successfully hosted a static website using S3 without custom domain in AWS. As a next step, you can go ahead and host dynamic websites or add custom domain name to your websites.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

## <span class="ez-toc-section" id="faq"></span>FAQ<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1606964565144">### 1. How do I host a static website on AWS s3?

<div class="rank-math-answer ">You can host a static website on S3 by placing your files in the S3 bucket and making the access to public. Follow this complete tutorial for step by step instructions.

</div></div><div class="rank-math-list-item" id="faq-question-1606964644470">### 2. What is static website hosting in s3?

<div class="rank-math-answer ">Static website hosting in S3 is hosting a website which will not change dynamically based on user inputs using the S3 bucket.

</div></div><div class="rank-math-list-item" id="faq-question-1606964761124">### 3. How do I setup a s3 bucket for my website?

<div class="rank-math-answer ">Follow Step-3 and step-4 for of this tutorial to configure your S3 bucket for hosting a website.

</div></div></div></div>