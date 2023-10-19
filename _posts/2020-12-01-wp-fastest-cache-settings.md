---
id: 3352
title: 'WP Fastest Cache Recommended Settings With Cloudflare [2021]'
date: '2020-12-01T08:09:49+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3352'
permalink: /wp-fastest-cache-settings/
rank_math_seo_score:
    - '95'
bialty_cs_alt:
    - ''
ss_social_share_disable:
    - '0'
rank_math_internal_links_processed:
    - '1'
rank_math_focus_keyword:
    - 'wp fastest cache,wp fastest cache settings'
rank_math_description:
    - 'Learn how to configure wp fastest cache settings to boost your website performance, step by step.'
rank_math_facebook_description:
    - 'In this tutorial, you''ll optimize your wordpress website using the WP Fastest Cache plugin with the optimal settings for the blazing speed. '
rank_math_primary_category:
    - '16'
socialsnap_share_count_timestamp:
    - '2023-09-02 01:11:18'
ss_total_share_count:
    - '0'
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
rank_math_title:
    - '%title% %sep% %sitename%'
rank_math_analytic_object_id:
    - '26'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"a1106dd36e7127f776c10ecb9b5bdda7";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - caching
    - speed
    - wordpress
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

*Caching* is the process of storing frequently visited pages of the site locally. When a user visits the page often, the files are loaded from the local storage instead of your server, providing significant improvements to the performance of your site.

*Leverage browser caching* is a high-priority suggestion of *GTmetrix*.

How can you achieve this? By using a caching plugin.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Processing of requests without caching](https://lh6.googleusercontent.com/qGFPGUopKkj7dLlPl8hoQJY7d9_Efw9Etd7ydU-V11Tc_PEY2-CGJ96p-Xi0IYZ6nbhPVkyoCwNNtg5dpXchlQqRWhy3ZEiWZcxwuy5Y6g2pFQTGt5BbuC4MWrkz4Rj4DE6eiIAB)</figure></div>WP fastest cache is one of the best WordPress caching plugins out there. Coupled with a CDN (Content-Delivery Network) your site could achieve the peak performance.

WP fastest cache offers many features. From minification to CDN support.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Processing of requests after caching](https://lh3.googleusercontent.com/0BxzjS3f4o362YtxgFyLloeYDM1XMT169DcTtY1C8cc_ilVtK3qOup1BwEBdCWTsG0Q3xYBSHAKDHmucPwGKkjt6i1eWLmwZA6tKEtoX1rwoW4OtEPdU93FDQvvVuipy4yv4JLvy)</figure></div>It’s free and takes **5 – 10 minutes to make your site fast.**

You should use a caching plugin,

1. If your site is slow
2. If it doesn’t involve a lot of dynamic modules
3. To get high scores in GTmetrix
4. To rank better in [Google](http://149.28.53.131/localhost-google-analytics/)

If you are using a shared hosting, try switching to dedicated cloud hosting with Cloudways. As low as 10$ per month.   
[![Load WordPress Sites in as fast as 37ms!](//www.cloudways.com/affiliate/accounts/default1/banners/4869f424.jpg "Load WordPress Sites in as fast as 37ms!")](https://www.cloudways.com/en/wordpress-cloud-hosting.php?id=770792&a_bid=4869f424&chan=speedtutorials)![](https://www.cloudways.com/affiliate/scripts/imp.php?id=770792&a_bid=4869f424&chan=speedtutorials)  
In this tutorial, you are going to optimize your wodpress site without using any premium plugins.

This guide illustrates two methods,

1. By using WP Fastest cache only
2. By using WP Fastest cache and Cloudflare

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

- Take a backup of your website – Though this process isn’t as risky as other website optimizations, it’s always better to have a backup of your website. I recommend [UpDraft Plus](https://wordpress.org/plugins/updraftplus/).

- Disable all caching plugins (if any) – This avoids conflicts and having two caching plugins at once hurts the site performance.

- A Cloudflare account (Optional) – If you’re going to use Cloudflare in this tutorial, [sign up](https://dash.cloudflare.com/sign-up) for a Cloudflare account. Explained in step 5. Else skip this.

## <span class="ez-toc-section" id="step_1_%e2%80%93_installing_wp_fastest_cache"></span>Step 1 – Installing WP Fastest Cache<span class="ez-toc-section-end"></span>

Install WP Fastest cache from your Plugin Dashboard and activate it

<div class="wp-block-image"><figure class="aligncenter is-resized">![installing wp fastest cache](https://lh6.googleusercontent.com/GHu8ZG-Y5V0VimuDGkHiy1Ktmm6oav-2_a2K0C8LM_GUKTux1-BSDuA2Gu0vFDedJkNv_BQt9bGCQC1UIxc1rXBG0gIy0b2yI4AvYSVkNYjWabfhrntuwWQVt2xUiDpfYi-BYW-8)</figure></div>From your WordPress dashboard, Navigate to *Plugins* &gt; *Installed Plugins* &gt; *WP Fastest Cache* &gt; *Settings.*

## <span class="ez-toc-section" id="step_2_%e2%80%93_configuring_wp_fastest_cache_settings"></span>Step 2 – Configuring WP Fastest Cache Settings<span class="ez-toc-section-end"></span>

- **Cache system** – *Enable* this to activate the plugin.

- **Preload** (Leave this off if you use Cloudflare) –  This compiles all the *PHP* and *SQL* components of your website into a single *static HTML file*.

*Enable this* and choose *Homepage*, *posts* and *categories* as items to preload.

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp fastest cache settings > Preload](https://lh5.googleusercontent.com/2kdV9dwQEeUOniMzz2lnpQ1HIV2XCY7233_6vuQJzgVgLj9gNqzcsYj-ZUdblOpoicego6rkHLZSpgtTdBL5F18HdyTevGQ5lYlJJ1Qka33CreYAe30J4xoxU_Rntb4c2Ph8ct2b)</figure></div>If you wish to preload everything, keep an eye on your hosting resources as this might overload them.

- **Logged in Users –** *Enable* this to avoid viewing static pages of your website.

- **Mobile** – *Enable* this to avoid displaying a cached version of the desktop on mobile devices which might lead to poor user experience.

- **New Post** – *Enable* this to delete cache files of your website whenever you add a new post. Choose *Clear All Cache* and click *OK.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp fastest cache new post settings](https://lh3.googleusercontent.com/hLOY4J_q-dh79GGli9ATHxIdkSJ4MsTAVjdDbR7XyX4tJwvuj2g5QSk8n_rKitFYG_20WXIBJ_P6MEgNk-pN2mrPJ_Xv85kuz-LbKHA-bgSwOgAahGGfO9dG-kWbqmd4LzddEuyJ)</figure></div>- **Update Post** – *Enable* this to delete the specified cache files of your website whenever you update a post. Choose *Clear Cache of Post/Page* and click *OK.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp fastest cache update post options](https://lh5.googleusercontent.com/DU_Xmdd025wDVYhfTi05x-3mlDCqM-l8SYuy1z4UBTGGJXNnQK7lhwC41nal1VEBZ0UhM7Il2MZG9omuwDeAPCejgKZuWKO-Sz-NIv-W65kCqz-GAD44_orJLsalHQwf-ztSOA8f)</figure></div>- **Minification** (Leave this off if you use Cloudflare) – Minification reduces load time by compressing code when a user visits a website. ***Enable* minification** for *HTML* and *CSS.*

- **Combining** (Leave this off if you use Cloudflare) – This process bundles the *CSS* and *JS* files together, reducing the total number of *HTTP requests* generated which increases site performance. ***Enable this***.

- **GZip Compression** (Leave this off if you use Cloudflare) – Gzip compresses elements of the website before sending. It provides a significant reduction in transfer time and provides up to 85% speed improvement. ***Enable this**.*

However, if you host your website on an Nginx server, you need to turn on Gzip compression manually. The below step shows the gzip settings in nginx.

Add the following code to the file – **/etc/nginx/nginx.conf** via your file manager to enable Gzip compression.

```
<pre class="wp-block-code config">```
gzip on;
gzip_disable "msie6";

gzip_vary on;
gzip_proxied any;
gzip_comp_level 6;
gzip_buffers 16 8k;
gzip_http_version 1.1;
gzip_types image/svg+xml text/plain text/html text/xml text/css text/javascript application/xml application/xhtml+xml application/rss+xml application/javascript application/x-javascript application/x-font-ttf application/vnd.ms-fontobject font/opentype font/ttf font/eot font/otf; 
```
```

The code should be pasted under the http block of Nginx config file **/etc/nginx/nginx.conf** as highlighted below.

**/etc/nginx/nginx.conf**

```
<pre class="wp-block-code config"> ```
 user  nginx;
worker_processes  1;

error_log  /var/log/nginx/error.log warn;
pid        /var/run/nginx.pid;


events {
    worker_connections  1024;
}


http {
    include       /etc/nginx/mime.types;
    default_type  application/octet-stream;

    log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for"';

    access_log  /var/log/nginx/access.log  main;

    sendfile        on;
    #tcp_nopush     on;

    keepalive_timeout  65;

    
   <var>gzip on;
    gzip_disable "msie6";

    gzip_vary on;
    gzip_proxied any;
    gzip_comp_level 6;
    gzip_buffers 16 8k;
    gzip_http_version 1.1;
    gzip_types image/svg+xml text/plain text/html text/xml text/css text/javascript application/xml application/xhtml+xml application/rss+xml application/javascript application/x-javascript application/x-font-ttf application/vnd.ms-fontobject font/opentype font/ttf font/eot font/otf; </var>
    include /etc/nginx/conf.d/*.conf;
    server {
       rewrite ^/sitemap_index.xml$ /index.php?sitemap=1 last;
       rewrite ^/([^/]+?)-sitemap([0-9]+)?.xml$ /index.php?sitemap=$1&sitemap_n=$2 last;
    }
}

``` 
```

*Gzip* compression is a high priority item in *GTmetrix*. Cloudflare users will enable a similar compression method called *Brotli*.

- **Browser Caching** – Load times are reduced considerably by locally storing files in your visitor’s browser. *Enable this.*

- **Disable Emojis** – *Enable this* to get a tiny boost in website speed. This setting disables emojis throughout your website.

Finally, click *Submit* to save your changes. Users who only use WP Fastest cache should have the following configuration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp fastest cache options](https://lh4.googleusercontent.com/iMgpSggSBThJnJFb4EADK57rqrBT5hs2orLnXQM0sK15popH--isAreTnvujwR4ynR11b7xOaMy9-kZU9kWy32sE-xzQpX9OkUxS4CRxMbL1TttTnTNQLPZpq5mXrluK5uYDgqvk)</figure></div>Cloudflare users will have the following configuration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![fastest cache settings with cloudflare](https://lh5.googleusercontent.com/xcPYK5jv1tNIA6b_0PfWD7yAWrortWC0j5qW34qMvY6JEX63jlWevt4HJv_6nlZOwq4oz9f0oVIyx9bOPLBkAHvOY4JqjHP7R9q72fxIf8miHDnD6sxyMAZ4YchRu1oWPJas2PDl)</figure></div>## <span class="ez-toc-section" id="step_3_%e2%80%93_deleting_cache"></span>Step 3 – Deleting Cache <span class="ez-toc-section-end"></span>

Navigate to the *Delete Cache* tab. Click on *Delete Cache and Minified CSS/JS* to wipe the cache files.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Delete cache> Delete Cache and Minified CSS/JS](https://lh3.googleusercontent.com/4YsExhI9jZoS_B2ieHVfKYonTfTjsBwic894DdPjq0baPGqfdviXl_NPLEDZmG4aJpXXYSSMzEEhH5WKk0EEL-S3Pn5SBd1orRf8iam32oYcwg0RtTqIoYKI4wvI1qyw_QzgqORM)</figure></div>## <span class="ez-toc-section" id="step_4_%e2%80%93_excluding_files_optional"></span>Step 4 – Excluding Files (Optional)<span class="ez-toc-section-end"></span>

Navigate to the ***Exclude*** tab

Enabling minification (at times) may impair the functionalities of certain elements.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Exclude> Excluding problematic CSS and JS files](https://lh4.googleusercontent.com/CQx2_ooIr20olQIad9PwpnsunW3rZ0n6rqrylsg2jpad3sv1KCnK7QbLdPSqVQlD4aZD1vA0oH27PthdhwEkkFc5pztQ9wzf_R06GyRq4wl5wf-_uFQwJOTGCPKWhAgdadAnWpwi)</figure></div>If you find any problematic CSS or JS files, add them here. Else skip this step.

You’ve optimized your site **without using premium plugins**. However, if you choose to use Cloudflare, follow the steps below.

## <span class="ez-toc-section" id="step_5_%e2%80%93_setting_up_cloudflareoptional"></span>Step 5 – Setting Up Cloudflare(Optional)<span class="ez-toc-section-end"></span>

CDN(Content Delivery Networks) refers to distributed servers around the globe which helps to improve website load times. CDNs do this by physically reducing the distance between the User and the Origin Server with the help of intermediary CDN servers.

<div class="wp-block-image"><figure class="aligncenter is-resized">![How cloudflare works](https://lh3.googleusercontent.com/3InXrFcNG5XytTJUwnyDPFVrzG7yC9tUJDH26NHOBoObvCLvj3HfZleAVeux8aLQH9HBj5TPfHODf0HbFf0CMIGLQiw7FRgRSu-WT6fIwbt9zZ1PwXmpbWlUV0uuLqAg75ToZ1Mz)</figure></div>Once you’ve signed up, enter your website name and choose the free plan. Finally, click *Confirm plan.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare plans > Choose Free plan for configuring with wp fastest cache](https://lh5.googleusercontent.com/iAAP-0cEX12CsI7yGLnMXqQeLiolhWBurFGsvgigt8KzGmgAVobEQhgLFq8KL-uj4-f11tEK_wI_DXxCiSbAsNpCwcj8qZXqHyr2WUfUrR6M06kDl3jJxAws-B5A09uf9JrWH5vg)</figure></div>Now you are provided with two *nameservers*. Replace your existing nameservers in your *CPanel* with the ones provided by Cloudflare. Most hosting providers give an option to activate Cloudflare in your CPanel.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare sample name servers](https://lh6.googleusercontent.com/gyulSQbJoHkPH6f90EOx2P-_wbsXyJjob2wbP9Xn5MIBc5iIE8NJWnW_p3sbWk0wlIZ5hgfWUHkdxxq9-S9LZ46pjtQvSqmPM6Bi6s3ib0a91LVeMTb11TUD6Ptfp1MVPCY4NhRG)</figure></div>Here’s a list of instructions for [changing your nameservers on popular hosting providers](https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare).

Once you’ve changed to Cloudflare’s *name servers,* click on the drop-down menu on your top right corner, navigate to *My Profile&gt; API Tokens.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Click on my profile](https://lh5.googleusercontent.com/ukehZ_RYUp5aXTsBmV0zuOtUO3owRB5KyY5UeHNsnJWxf3RSm__aBSIzd4LdgrGNY0i6VvjDd14EUn2-wlleHAJbSenCaR-p_LrtZCyYma3T6Prs5NmJXAoEQk1KAysxI5DOJWq_)</figure></div>Click *View* on Global API Key and enter your password to view the API key.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Enter your password to view your Global  API key](https://lh4.googleusercontent.com/UUBQwrHEwAXOfDQMcAyOKWN12cNI1W4O8E5x4n1TyyC72dmy46kLupzke7OMT_E_wQ4yaNZt3SbbGoIRFCVeRJKYmk2T9PHhVgy926jgAJnI_hvTNNV6c4sztPJVVd3tqewpnzhG)</figure></div>Copy the *API key*. Now navigate to WP Fastest cache CDN settings.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Configuring cloudlflare with wpfastestcache](https://lh3.googleusercontent.com/u-hmJyM16O09cVSi1i9vPzdWyYbAhNly3xY_oCoEdXo4gsH3tm040R3NV-d8edgoPFylMJXLO1AwW3FUoGyj2w6kZgugVeZzPB0rEyK8al_tUv8QrYoyqH2ZTx9H7re_ZZvlBkg7)</figure></div>Enter your email address, paste your API key in the pop-up and click next.

<div class="wp-block-image"><figure class="aligncenter is-resized">![configuring wp fastest cache with cloudflare](https://lh6.googleusercontent.com/5wm1h7MttvbI_hVOZG87pHDg_p_fVYxGNoPd0ihu1Bg_4UseJK_BjCNj_9_B2a3Du4r2zmGigSaMHSQCZ3JTI-c6fzCgbjrZg-P5dJuquYvooLtwEAfzlqPHVRFxFoU6HKGDjLXu)</figure></div>Even if you’ve accidentally turned on minify in WP Fastest Cache settings, clicking *next* turns this off to avoid conflicts.

<div class="wp-block-image"><figure class="aligncenter is-resized">![minification with fastest cache](https://lh6.googleusercontent.com/kkbhfP0KR4X1R6RmNx3oNCHLjuvYF-VehUI9M6Vpx0Ma1DVYmU-ZZQtoiBFqgyRbpyf4mlRQ4aTbfsaFgmtxi8dq3EefRHAGtbJKzMaNRFZ-Q4WsD65dQCqp2rYLzDDOh_0SuwGl)</figure></div>*Rocket Loader* is disabled here. Don’t make any changes and click *Next*.

<div class="wp-block-image"><figure class="aligncenter is-resized">![rocket loader configuration](https://lh6.googleusercontent.com/Prkbpye1ANtAgUnqhm88nwR-ZOvg5GcIk2WvVWibtYju1amVr74k6AH0E_uqctKzIz86MsGlz1N_3RD3Q-oUtfSKIo58mzBLqwi62qLl-M17kQ7MtUj_7e4dLBPRihSwejKs6bHw)</figure></div>Set your *browser cache expiration* to **2 months**. This determines how often your website cache should get refreshed. Unless your website is super-sensitive setting it to **2 months** will do the job.

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp fastest cache options with cloudflare](https://lh4.googleusercontent.com/05ASg78uuqDZ2hnkmYLnBW66V5ZxBR6y0obSIxPzddyPlTPWJyYmqb31_DdU9d981yTiBd8E7XJCZLYncxy0NRE7-Ase4uHvKa6JDHdVKBc8q6uq1ph7MDXPiU6G_imV74d1n9AF)</figure></div>Finally, click *Finish*.

<div class="wp-block-image"><figure class="aligncenter is-resized">![wpfastest cache with cloudflare](https://lh4.googleusercontent.com/trsFhyxHgP_SjPQnjIh5OZK0samrpnuZQ0ziYyTTnJoyBwAYqXb90_D5lQG0co4Ts1Y-p-p5TrRa75dZ2SXqQzX8S26KZoI4ShLGtsshaQDc5zsaaBdf6qwmJpZECpGAaLh5qh10)</figure></div>Cloudflare is now successfully paired with WP Fastest cache.

## <span class="ez-toc-section" id="step_6_%e2%80%93_configuring_cloudflare_settings"></span>Step 6 – Configuring Cloudflare Settings<span class="ez-toc-section-end"></span>

Head on to [speed settings of Cloudflare](https://www.cloudflare.com/a/performance/). Click *Optimization.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare speed configuration](https://lh6.googleusercontent.com/mp3x2SERk-jBIRm9Rrc7b3U6gUKnusO1HlaXcE7uYbEzdh2Nj-aVbHOna-Q3H9CMi6K0AkX1lu9f9_RLrSVlYClIYeVEBHtIhPD6Ljes2kq5vl24hhm9JO1xhxceIKX8fDPWX4k5)</figure></div>Scroll down to find *Auto Minify*. Enable for minification for *Html*, *CSS* and *Js*.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Auto Minify settings of cloudflare](https://lh5.googleusercontent.com/-DcJHNU-5vfVEJV8_1b5mKT7U8ykziw2H0gM-ztNKqx_9DLOytdyui8pAyJrmiLfNDkllKHkmngmZQNqZDWGQtf4e8z6Q_lnSmwevE5WZzSGJ1p1-0R5vd2P211zZjX39Z4WqAc9)</figure></div>Turn on *Brotli*. It compresses your files before the transfer, similar to Gzip compression.

However, if you wish to use GZip instead of Brotli, turn this off before turning on Gzip from the basic settings panel of WP Fastest Cache. Here’s a post comparing both compression methodologies – [GZip vs Brotli](https://wp-rocket.me/blog/brotli-vs-gzip-compression/).

<div class="wp-block-image"><figure class="aligncenter is-resized">![Enable Brotli](https://lh4.googleusercontent.com/r5yU7YiWrZNi5m79SxLYt0u1IZFVlgf1079OkT1-42aL4N5M0MVFuIxSJI_lKUn6duk3D_yoDJslso3OBsKPza0n7rwfOqMiq3TkjC7tQZhk47UtvQhzwd_MeWQSMBTATNEQ4x50)</figure></div>Enable *Railgun*. It aids in speed improvement by leveraging compression techniques, mainly dynamic content.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Enable Railgun](https://lh4.googleusercontent.com/RIvFHtiasWT9NQZBQLHBxN562-smHjwUrDmtCMzcDha7EB0ufU1bkXnwBiszw2WOqcrkalGb9HPpM5RyRt38Kmbtrhtegf1BGkt_Ql72ite2PF1wd3W8AbDh76c8WsEZoCUubUvh)</figure></div>It’s recommended to turn off *Rocket Loader* as it’s known to cause several issues in the past. However, if you’re up for the risk, feel free to experiment with it.

You’ve successfully created a performant site using Cloudflare and WP Fastest Cache.

## <span class="ez-toc-section" id="step_7_optional_%e2%80%93_boosting_the_performance_of_your_site_far_higher"></span>Step 7 (Optional) – Boosting the Performance of Your Site Far Higher.<span class="ez-toc-section-end"></span>

Though certain features of WP Fastest cache is limited with a payment gateway, you can get their features using other plugins.

**Image optimization** – The image optimization that I recommend is *TinyPNG*.The setup is simple. Install and activate the plugin.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Other optimization plugins> Tiny PNG](https://lh3.googleusercontent.com/VsYFThOZSn3gRft9tTp3_oSseyKPbvvpvLMf3pnBzTs8B8oJLP91dAyLl9PnPInzNBkIM_0axa5dSe_CWcQT0oYk1TbxiaRuGhnRrNQ0rWj84Hilv7s-cAv9wD_Bbsu-C0pS0Exv)</figure></div>Navigate to settings using the plugin dashboard.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Tiny PNG settings](https://lh3.googleusercontent.com/gOGV9cmDhBMk3AvVNWfMxkvjBNZ6L-pG2mdPklVscbM8vdOsXbhbqyLzKBf2PmezTtRxkTA11O4WOMp4ILxtwjUEzq40hWYUk7ThP4ULAUnQMaYcCO2zM1iWovcZtbZdcIb-2ivJ)</figure></div>Enter your name, email and click *Register.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Register an account](https://lh6.googleusercontent.com/pKzmKnVb7a2ZXlOAQ6AiJKVl57sYNJysLvdbEdGlk6cv0a6esBX5pjMuW_ZrdXQpygqR7U131r0mfTZBF7skRuQAXZL_dn4QjLoSPZBkiF5abq5IX5kflT9_Pt8ra09bw47S2nff)</figure></div>Now head on to your email to Activate your account.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Activating your image compression account](https://lh5.googleusercontent.com/0NI9w8LvgQz7KoDU2RfcccdEnNmXVRZtXVKen42Gz6La3ErAGcNy5DOtAQc9OS47-8CBLvjciQE5A0bFRNor9s15adRKsUfye4NcM_0AkXhMXu1XlYPZGycXPyqfFOcYmce6F7nI)</figure></div>Now head back to the TinyPNG dashboard in WordPress. You can find that your account has been activated successfully. TinyPNG allows up to 500 compressions per month for free.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Connected account](https://lh3.googleusercontent.com/MGnxEuHI_S9Oxf97NENSgJYxaRO16C4vAIcaGQmp_YeVTe-QYkVZWaIc14whm24eKxvi41g3Up14npoHne6wNZoY7IVp6Fn1_ZtCW0qY5HviiLHEUr0yCyzpAODiuSHP3ZdAABsV)</figure></div>Choose your settings according to your requirements and finally hit *Save Changes.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Tiny PNG settings](https://lh5.googleusercontent.com/fyW7Etp-JHMkM_H2Nl-w5xUvwXIwixHWymtHXpSpA5DKfy_S78LYNtMj2qV7oNSIHegQECYf4YEpG5uD3Boxi5xSvkdYlWqgoU_Zuw3WkPK1HNcD9X8Aq_ltE-3l119MYADwkYdP)</figure></div>That’s it.

**Database Cleanup** – This is done to remove unnecessary files and to make your site load faster. You’re going to achieve this using the WP-Optimize plugin.

Once you’ve installed it, click the settings option for WP-Optimize through the Plugin dashboard.

Make sure to create a backup before proceeding any further.

Now click *Database*.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Click Database](https://lh6.googleusercontent.com/bmL6rB_dQwzLCWKHNxK_4xuJ4Am2CGQD_LA4bIxKC9iQmhKATna9frSvNBMgBQKiHUVFerBRXwhLa2jkRDutc1ST0IMrTxrb7nQGSQdG2dgvXtAdxeFUeEVTFS1oY7SneWVk3SHe)</figure></div>You’ll be provided with several optimizations.

- Optimize database tables: It’s a good idea to optimize your database from time to time.

- Clean all post revisions: Post revisions are older versions of the same post. If you’ve edited an article 50 times, 50 variants of the same article are stored. Though it’s a useful feature, over time, your database gets bulked up and it’s better to delete those unwanted files from your database.

- Clean all auto-draft posts: Auto-draft is a useful feature similar to Post revisions. It auto-saves your posts while writing them. If something goes wrong, you can recover your posts through this functionality. To avoid bulking your database, clean them once in a while.

- Clean all trashed posts: Deletes trashed posts and save storage space.

- Remove spam and trashed comments: If you’re using anti-spam plugins, spam comments are automatically stored in your database. Using this, you can delete spam and trashed comments with a single click.

- Remove unapproved comments: Allows you to delete unapproved comments at once.

<div class="wp-block-image"><figure class="aligncenter is-resized">![WP Optimize configurations](https://lh5.googleusercontent.com/IIt3F-VOCWszYAYVPPU9MqzpZhsun8F175BJG2wD5qZHKVVipkOGfCiI7icme7dK-WS_fhKxUE2lg3-LajrPQxuI7S5liBLWhqBTt_OzHlOAPrrsJGQJRkzyYD4g3baa14sUsMqJ)</figure></div>This amount of database optimization is sufficient for most websites. However, if you wish to work around with other settings of WP-Optimize, proceed with caution.

You’ve successfully optimized your website to run at peak performance using WP Fastest Cache, Cloudflare, Tiny Png and WP – Optimize.

If you’re willing to go the extra mile by investing in a premium plugin, I highly recommend WP Rocket instead of WP Fastest Cache. Because WP Rocket offers more features for the same price and set-up process is much simpler. However, do your research before paying for a plugin.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

To summarize, you’ve configured WP Fastest cache settings to improve your site performance. In addition to Fastest cache, you’ve also used a variety of tools from CDNs to Database Optimization plugins to create a performant site without using any premium plugins.

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

Caching is not the only to make your site faster. As a wordpress user, you may also need to do few other things to make your site faster.

1. [Update to PHP to latest Version](http://149.28.53.131/update-php-on-wordpress/)
2. Remove the bloating plugins
3. Use the lightweight themes such as GeneratePress
4. Use the Fast hosting such as CloudWays.

## <span class="ez-toc-section" id="faq"></span>FAQ<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1606462088769">### 1. Does WP Fastest Cache work with Nginx?

<div class="rank-math-answer ">Yes, it works with Nginx properly.

</div></div><div class="rank-math-list-item" id="faq-question-1606462115927">### 2. Is WP Fastest cache sufficient by itself or should I install and configure any other plugins?

<div class="rank-math-answer ">Though the fastest cache gives a boost in speed, I highly recommend you install and configure image optimization and database cleanup plugins for improved site performance.

</div></div><div class="rank-math-list-item" id="faq-question-1606462142064">### 3. Do I need a caching plugin?

<div class="rank-math-answer ">Yes, because whenever a user visits your website, pages are downloaded every single time from the server. When a caching plugin is used, files are loaded from the visitor’s browser instead of the servers providing a significant boost in site performance. It saves bandwidth too.

</div></div><div class="rank-math-list-item" id="faq-question-1606831484993">### 4. What is gzip in nginx?

<div class="rank-math-answer ">gzip is used to compress the files before sending it to the browsers. GZIP in nginx is compressing the files when you are serving files using the nginx.

</div></div><div class="rank-math-list-item" id="faq-question-1606831636722">### 5. Do all browsers support gzip?

<div class="rank-math-answer ">Yes, It is supported by all major browser.

</div></div><div class="rank-math-list-item" id="faq-question-1606831702066">### 6. Should I use gzip?

<div class="rank-math-answer ">Yes, you should enable and use gzip as it improves the initial page load times as much as 90% which may result in better search engine rankings and better sales.

</div></div><div class="rank-math-list-item" id="faq-question-1606831832169">### 7. How do I know if gzip is enabled nginx?

<div class="rank-math-answer ">You can check if gzip is enabled byusing the tools like gzip compression checker https://smallseotools.com/check-gzip-compression/

</div></div></div></div>