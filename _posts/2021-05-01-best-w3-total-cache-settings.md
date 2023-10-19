---
id: 5728
title: 'Best W3 Total Cache Settings [with Cloudflare]'
date: '2021-05-01T09:53:26+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=5728'
permalink: /best-w3-total-cache-settings/
rank_math_seo_score:
    - '94'
rank_math_focus_keyword:
    - 'W3 total cache settings,W3 total cache best settings,w3 total cache cloudflare,how to configure w3 total cache plugin,w3 total cache tutorial'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
ss_social_share_disable:
    - '0'
rank_math_internal_links_processed:
    - '1'
rank_math_description:
    - 'Website performance is one of the key indicators of a successful website. Learn how to configure w3 total cache settings for increased performance.'
rank_math_analytic_object_id:
    - '43'
socialsnap_share_count_timestamp:
    - '2023-08-31 10:35:06'
ss_total_share_count:
    - '0'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"813af045f27acd4560a5e9bd40f03b6f";s:6:"images";a:0:{}}'
categories:
    - how-to
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

<div class="ez-toc-v2_0_55 counter-hierarchy ez-toc-counter ez-toc-grey ez-toc-container-direction" id="ez-toc-container">Contents

<nav>- [Introduction](https://www.askvikram.com/best-w3-total-cache-settings/#introduction "Introduction")
- [Prerequisites](https://www.askvikram.com/best-w3-total-cache-settings/#prerequisites "Prerequisites")
- [Step 1 – Installing W3 Total Cache](https://www.askvikram.com/best-w3-total-cache-settings/#step_1_%e2%80%93_installing_w3_total_cache "Step 1 – Installing W3 Total Cache")
- [Step 2 – Configuring General Settings of W3 Total Cache](https://www.askvikram.com/best-w3-total-cache-settings/#step_2_%e2%80%93_configuring_general_settings_of_w3_total_cache "Step 2 – Configuring General Settings of W3 Total Cache")
- [Step 3 – Configuring Page Cache Settings of W3 Total Cache](https://www.askvikram.com/best-w3-total-cache-settings/#step_3_%e2%80%93_configuring_page_cache_settings_of_w3_total_cache "Step 3 – Configuring Page Cache Settings of W3 Total Cache")
- [Step 4 – Minify, Database Cache and Object Cache Settings](https://www.askvikram.com/best-w3-total-cache-settings/#step_4_%e2%80%93_minify_database_cache_and_object_cache_settings "Step 4 – Minify, Database Cache and Object Cache Settings")
- [Step 5 – Configuring Browser Cache](https://www.askvikram.com/best-w3-total-cache-settings/#step_5_%e2%80%93_configuring_browser_cache "Step 5 – Configuring Browser Cache")
- [Step 6 – Configuring Cache Groups](https://www.askvikram.com/best-w3-total-cache-settings/#step_6_%e2%80%93_configuring_cache_groups "Step 6 – Configuring Cache Groups")
- [Step 7 – Configuring Cloudflare With W3 Total Cache (Optional)](https://www.askvikram.com/best-w3-total-cache-settings/#step_7_%e2%80%93_configuring_cloudflare_with_w3_total_cache_optional "Step 7 – Configuring Cloudflare With W3 Total Cache (Optional)")
- [How to Purge Cache in W3 Total Cache](https://www.askvikram.com/best-w3-total-cache-settings/#how_to_purge_cache_in_w3_total_cache "How to Purge Cache in W3 Total Cache")
- [Importing and Exporting W3 Total Cache Settings](https://www.askvikram.com/best-w3-total-cache-settings/#importing_and_exporting_w3_total_cache_settings "Importing and Exporting W3 Total Cache Settings")
- [Other Things You Could Do to Speed Up WordPress](https://www.askvikram.com/best-w3-total-cache-settings/#other_things_you_could_do_to_speed_up_wordpress "Other Things You Could Do to Speed Up WordPress")
- [Conclusion](https://www.askvikram.com/best-w3-total-cache-settings/#conclusion "Conclusion")
- [Frequently Asked Questions](https://www.askvikram.com/best-w3-total-cache-settings/#frequently_asked_questions "Frequently Asked Questions")

</nav></div>A cache plugin creates static copies of your website. These files are loaded to the local file system of the user. Then they are served with these cached copies that are faster than a dynamic version of the website. It reduces load time with a significant reduction in server resource usage.

This process is called browser caching. *Leverage browser caching* is one of the crucial performance suggestions in the GTMetrix report.

There are a ton of caching plugins. WP Rocket is your best bet when it comes to premium plugins. However, with free plugins, you have a few options,

1. W3 Total Cache
2. [WP Super Cache](http://149.28.53.131/wp-super-cache-settings/?swcfpc=1)
3. [WP Fastest Cache](http://149.28.53.131/wp-fastest-cache-settings/?swcfpc=1)

W3 Total cache is a great freemium cache plugin. But it has a few cons – no support for database cleanup/ google fonts optimization. However, each plugin has its disadvantages.

This tutorial is focused on speeding your website using free plugins at **no cost!**

You should use a cache plugin if,

1. If your website is slow
2. To get higher scores in speed tests like GTmetrix and Pingdom.
3. If your website doesn’t use a lot of dynamic modules.
4. To make google love you more.

This w3 total cache tutorial illustrates two different ways of optimizing your website,

1. Using W3 Total Cache settings
2. Using W3 Total Cache and Cloudflare

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

- Backup of your website – Using a cache plugin isn’t going to break your website in most cases, but it’s better to be safe. I recommend [Updraft Plus](https://wordpress.org/plugins/updraftplus/).

- Turn off caching plugins (if any) – Having multiple caching plugins running at the same time negatively impacts SEO. So turn all caching plugins off.

- Cloudflare account(Optional) **–** If you are using Cloudflare during this tutorial, [sign up](https://dash.cloudflare.com/sign-up) for a free account.

## <span class="ez-toc-section" id="step_1_%e2%80%93_installing_w3_total_cache"></span>Step 1 – Installing W3 Total Cache<span class="ez-toc-section-end"></span>

1. In your WordPress dashboard, click *Add New* under “Plugins”. Then type in W3 Total Cache.

2. Install and activate the plugin. WordPress redirects you to the plugin dashboard on activation.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Installing W3 total cache plugin](https://lh6.googleusercontent.com/Jh7ZopprhHnUpr4bWs_YOjQ1Uamon1262ItUOUllHFgrAVqHdSBxG8qncQx4u5t8UFx5k55HkCZ6vP1zqnzSlC9H1eHhEhJx-4i_jNjvN3b8an70ywBT7M6xvXOU_f_hp5y8bH11)<figcaption>Installing W3 total cache plugin</figcaption></figure></div>3. Scroll down to the bottom of your plugin dashboard. Find W3 Total Cache. Click settings.

<div class="wp-block-image"><figure class="aligncenter is-resized">![W3 total cache settings tab](https://lh3.googleusercontent.com/zqI7BU6gHLhjXGDM4_iTqaud269XEe8CwHwRcO8R_QEaICEcdKLp0MCqH4r27KQV2SOhidF6yyRg5_oje0zVhT5oGvoWpEF959p8b26ntp-7pcODdZusCa-l-ECAg7bLMjDAoWTD)<figcaption>W3 total cache settings</figcaption></figure></div>## <span class="ez-toc-section" id="step_2_%e2%80%93_configuring_general_settings_of_w3_total_cache"></span>Step 2 – Configuring General Settings of W3 Total Cache<span class="ez-toc-section-end"></span>

**1. Page cache** – Responsible for creating static versions of your website. ***Enable this.***

**2. Page cache method** – There are three different page cache methods.

- Disk enhanced is optimized for shared hosting environments, so lesser resources are consumed. ***Enable this.***

- Opcode cache compiles the PHP code in memory and increases the performance of the website. For smaller websites with lower traffic, opcode cache does not make a difference.

- With Memcache, the data is stored in the RAM instead of the hard disk. It speeds up the transfer at the expense of server resources.

Here is a detailed explanation of these [methods](https://stackoverflow.com/questions/25933887/wordpress-w3total-cache-disk-opcache-or-memcache#:~:text=It%20is%20important%20to%20understand,pages%2C%20database%20queries%20or%20objects.&text=Memcache%20stores%20data%20in%20the,than%20accessing%20the%20Hard%20Disk.).

Note – This tutorial primarily focuses on optimizing websites that run on shared hosting. If you use cloud hosting, use *Memcached* under the Page Cache method.

Click *Save all settings.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![W3 total cache -  page cache settings](https://lh6.googleusercontent.com/6PJ8J8Nh-Vy_br3c3kqmlFjnTQErxtX_fCpcwE99FvD_azxkuJwW6mxgdeNE_b75w99gS0pdJcIdMMwfwYoxBv2zkQzc8Jwo-K6lbM3c-huJR36I59c7dSBZaX5ewdBzE-kqEusM)</figure></div>**3. Minification** – It is the process of removing unnecessary lines of code from your script files. Lesser lines of code = fast execution. ***Enable this.***

<div class="wp-block-image"><figure class="aligncenter">![minification settings of w3 total cache](https://lh5.googleusercontent.com/N9hSDAKVACyEk4C4nH4-RI4Jb1djl-NVgpTKgieEYKgozzud1TbhS7R-jpHhv2dwHbJQNGSr-N3s7G4PTzDYjSzJfafBMvg7eQKQB_jV7pNTCikED9ETdMnx0l2fc13XCLUQxbFA)</figure></div>**4. Opcode cache** – Leave everything untouched.

**5. Database cache** – Increases site speed by caching database files.

Not recommended for shared hosting environments. Leave it disabled as it overloads the server, mainly on shared hosting environments.

**6. Object cache** – It takes off the server load for generating database queries in complex websites. Ex: Shopping sites.

New websites should avoid it, as it slows your WordPress site and your dashboard. Leave this untouched.

**7. Browser cache** – It is responsible for creating cached copies in the local file system of the visitor. Enable this if it isn’t already enabled. Click *Save all Settings.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Browser cache settings of w3 total cache](https://lh5.googleusercontent.com/jdI8YQ9UVFSN-7OWSTKo-UFNEjb4-i6HJu7JhIQ1WfJmgG6h53IBdH4uCA1L1Zarq-TFcIvvm-fihl01xltkS_8slWKC_HBqRF-6NWp4sCH_nlqgFDJKPb79XvKYrJyyM72OpePP)</figure></div>**8. CDN** – Leave it disabled if you are going to use Cloudflare/ not using a CDN. Enable it if you use other CDNs like bunny CDN, stack path CDN or max CDN.

**9. Reverse proxy** – It is present before the webserver and intercepts the connection from the client.

Reverse proxies are highly useful in websites with an enormous amount of traffic. They help with load balancing, speed up connections and free up valuable resources for encrypting SSL certificates for each client.

Leave this untouched unless you have a site of high traffic and substantial technical expertise.

**User experience settings**

**10. Lazy loading –** It is the process of deferring all images of a page when a website loads up. Images are displayed only when the user reaches specific sections of the webpage.

Lazy loading provides a significant performance boost.

**11. Disable emoji** – Enable this if you don’t use emojis on your website.

**12. Wp-embed script** – Turn this on if you don’t embed other WordPress posts on your pages.

**13. Disable jquery migrate on the front end** – From WordPress 3.6, jquery is added automatically into the WordPress installations. In most cases, jquery need not run in the foreground.

However, if you use plugins and themes that use an older version of jquery, you shouldn’t disable this. (in most cases, you won’t be using an older version)

<div class="wp-block-image"><figure class="aligncenter">![W3 total cache best settings - user experience](https://lh6.googleusercontent.com/0hw7Q20kmEqVtvg-2B2hW1Vvhl0nTrdwRZgvILmUdHKv9MvMs2c8D7SoMZrZ5qgE98AElZWIX7atEqMshkGLwpnkoKSqqfxwn2n38CQx3mb8HU7mj6S3LeF8571OHKaJJaHFLHqA)</figure></div>If you are skeptical, try turning this on and see if any errors pop up in the front end of your website. Here’s a [guide](https://joewp.com/en/remove-jquery-migrate/#:~:text=If%20current%20designs%20and%20plugins,load%20a%20little%20faster%20again!) about it.

Once you have made your changes, click Save all settings.

Leave everything else untouched.

**14. Disabling anonymous tracking** (optional)- If you do not wish to be tracked anonymously for using w3 total cache, scroll to miscellaneous settings and disable *Anonymously track usage to improve product quality.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Disabling anonymous product tracking](https://lh4.googleusercontent.com/o7PkDhmwAHvAmg2OfBvOW1J5SbQ0fPcuqmrf3t8NHUaC6mqfAhCdL2NAqdGtznT9RP64wDRwpgKsqzOB4N6U6h70r8ngv4cnesVE9cXk7Y-VAXeAHCQ0yAKqdCb1ObQtrZJapH-y)</figure></div>## <span class="ez-toc-section" id="step_3_%e2%80%93_configuring_page_cache_settings_of_w3_total_cache"></span>Step 3 – Configuring Page Cache Settings of W3 Total Cache<span class="ez-toc-section-end"></span>

**General settings**

**1. Cache front page** – This setting caches the front page of your website. It is on by default. If not, enable this.

**2. Cache feeds** – RSS feeds are generated by WordPress – to display your website in apps and services. Enable this to cache these fields.

**3. Cache SSL** – If your website forces all your requests as HTTPS, enable this.

One of the prominent differences between HTTP and HTTPS is the SSL certificate. HTTPS has one which makes it more secure and prevents middleman attacks. So, always force your requests through HTTPS instead of HTTP.

Enabling this caches the SSL certificate and improves website performance.

**4. Cache URIs with query string variables** – Certain websites add a string parameter at the end of their URL. Ex: vers/9.

It is used to display specific data from the WordPress database. If you do not serve a unique version of your website depending upon the user, leave this off.

**5. Cache 404** – If disk enhanced is the preferred method of caching web pages, turning this on will lead to 200 page error. So leave this off.

**6. Don’t cached pages for logged in users** – Logged in users like admin make constant changes to the website content. If pages are cached for logged in users (like admin), live changes to the website will not be noticeable in real-time. Enable this.

**7. Don’t cache pages for the following users** – Enable this. Click the check box for admin, editor and author. It helps them to view the changes in real-time.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Page cache settings configuration](https://lh3.googleusercontent.com/MyY_QAo8m6uSqwjn_--pmtqMz82UGwmkZO7GBg_qhwd-FzcBUIzrIKnIz9Rk-hsUZT8Ua8VC49VLdUwLgp4fTpu2Nf-_pJ6Avyi4zbZszr83fEWwipKVU8nQkxbna5vvyuo1vtEL)</figure></div>**8. Cache preload** – Enable this.

**9. Update interval –** For every 15 minutes (900 seconds), your website is cached. The lower the number, the higher amount of server resources are used and vice versa. You can set it to lower counts if you are on cloud hosting.

**10. Pages per interval** – It is the total number of pages that is loaded every batch. Set the value to 10 for servers running on shared hosting.

**11. Sitemap URL –** Paste the URL of your sitemap. In most cases, it is website.com/sitemap.xml (replace *website* with your site name).

Depending on the order of indexation of pages in the sitemap, page caching occurs.

**12. Preload post cache on publish events** – This setting preloads post cache every time the publish button is clicked. Enable this.

Leave the purge policy untouched. These settings are responsible for maintaining what pages to be cached.

<div class="wp-block-image"><figure class="aligncenter is-resized">![cache preload settings](https://lh6.googleusercontent.com/zTYYNm7i6QiYFYtoEdMNOwLBIO0kjmKe3Lu23015PFV4lOnCNkZfcGQjQ4F8fi6HOLnt2qnn20lHZDJvgQWlq4jPINobvSRUMBps8TykjIZKegD4CZtWBz0EMGQAez0t_x1rQg6D)</figure></div>**Advanced settings**

**13. Enable compatibility mode –** Enable this. (Recommended by the plugin developer)

**14. Garbage collection interval –** Specify the period for the removal of expired cache data. Lower values are better for high traffic sites.

**15. Comment cookie lifetime –** When a visitor comments on a blog post, the data entered is withheld for a specific time. When they revisit the same page, they need not reenter all the data. Ex: Name, email etc…

This interval of holding that data is comment cookie lifetime. Leave this untouched.

Scroll to the end and click “Save all settings”

<div class="wp-block-image"><figure class="aligncenter is-resized">![garbage collection settings](https://lh3.googleusercontent.com/q_YU3DUVDNJTKlKmMh31ZpVQH-W6ASd_CtDi_noa3T-ZcDlZ-oTx65_3t5iEpu5E7hCfX-_DRDiQDIdMJ6Rnz_UtYJVedvBATMg1ozsWUDTokL-SMZpZaPiZTIc9zltnH3iwKe4A)</figure></div>## <span class="ez-toc-section" id="step_4_%e2%80%93_minify_database_cache_and_object_cache_settings"></span>Step 4 – Minify, Database Cache and Object Cache Settings<span class="ez-toc-section-end"></span>

Leave everything untouched as the current configuration is set to optimal performance of the website.

<div class="wp-block-image"><figure class="aligncenter is-resized">![developer instructions for configuring w3 total cache](https://lh4.googleusercontent.com/EF_FlMBDWj3dEarGEp3CapSVsuCBJB5-3MeJh7Bad_2P0MhSUTdXh46VXfItrbwc5jLjxKpQvNhiYaA3jo_TsGA_UZ4GuuxMFD6udojsNV7J2kCWsZ1GHtYJwG6eMfoVk1DYmg35)</figure></div>## <span class="ez-toc-section" id="step_5_%e2%80%93_configuring_browser_cache"></span>Step 5 – Configuring Browser Cache<span class="ez-toc-section-end"></span>

Scroll down to the CSS and JS section

**1. Expires Headers Lifetime** – A longer expires header time leads to efficient browser caching. Set the expires headers value to 31536000 seconds. (1 year)

**2. Cache-control policy** – Set this value to – “*cache with max age(“public, max\_age=EXPIRES SECONDS)”*.

It ensures that all the static resources are cached by the plugin.

**3. Enable Gzip compression** – It compresses the files before the transfer, therefore, providing a reduction of 80% in load time. If you are going to use brotli instead of gzip, leave it off in here. You can turn on brotli compression in Cloudflare settings.

**4. Remove query strings from static resources** – Query strings are additional texts present at the end of the URL. Enabling this increases server speed. Removing these query strings increases server speed.

But since these query strings are used to serve visitors with the latest version of CSS and JS files, leave this disabled.

Repeat this process for all files. (JS files, images and media)

<div class="wp-block-image"><figure class="aligncenter size-large is-resized">![Configuring expires header](http://149.28.53.131/wp-content/uploads/2021/05/expires-header.png)</figure></div>## <span class="ez-toc-section" id="step_6_%e2%80%93_configuring_cache_groups"></span>Step 6 – Configuring Cache Groups<span class="ez-toc-section-end"></span>

**1. Manage User Agent Groups –** It is to specify if you use a separate mobile theme. If you are using a responsive mobile theme, ignore this.

Note – Always use a responsive mobile theme. Responsive themes are faster, more flexible and secure compared to outdated non-responsive themes. Consider switching to lightweight and responsive themes like [Astra](https://wpastra.com/), [OceanWP](https://oceanwp.org/) or [Generate Press](https://generatepress.com/).

**2. Referrer groups** – It is used to serve a specific version of the website depending on the source of traffic(Google/ Duckduckgo/ Bing). Leave this disabled.

**3. Cookie groups** – Uses cookies to create a unique cached version of the website for every visitor. Leave this untouched.

You have successfully configured a performant website W3 Total cache. Proceed further if you use cloudflare along with Total cache.

## <span class="ez-toc-section" id="step_7_%e2%80%93_configuring_cloudflare_with_w3_total_cache_optional"></span>Step 7 – Configuring Cloudflare With W3 Total Cache (Optional)<span class="ez-toc-section-end"></span>

**CDNs** – Content delivery networks are a collection of a large number of servers spread throughout the world. These servers reduce the physical distance between the origin server and the client. Reduced physical range leads to improved performance.

Using a CDN is one of the most vital recommendations in the GTmetrix report.

1\. Visit [cloudflare.com](http://cloudflare.com).

2\. After signing up for an account, choose the free Cloudflare plan.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare pricing plans](https://lh4.googleusercontent.com/gXbTBk1aCCoYd5QlzlzAkP5ftIwjuui0eLzxwcwY2pRDRVox0v6cgBG22XgLyNPIhCEEpYTreptg5L_imCa_IkrMRgwAlQIBpZNGGep9gu2BJiBtwvKWURwDJPIxsHPp9QgS4OlT)</figure></div>3\. After choosing the free plan, Cloudflare provides you with two nameservers. Replace your existing ones with the nameservers provided by Cloudflare. Many hosting providers give an option to activate Cloudflare via your CPanel account.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare nameservers](https://lh5.googleusercontent.com/8liGWQ6Zkp1LfapvSxs-OYjWURrya0WR8k0qX98TfaT5mHr2S2qo8LkqFbNlRjK5pxb8sl-yN8OetL-yLs83etkkx1Nz8KdOIzeAveKxSNlvWmD_zbYrk0FZVgYb2bYP1dk2wXyR)</figure></div>Here are instructions for changing [nameservers in popular hosting providers](https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare). If you cannot find your hosting provider, perform a google search or contact them for support.

4\. Once you have changed the name servers, navigate to the speed optimization settings in Cloudflare.

<div class="wp-block-image"><figure class="aligncenter is-resized">![W3 total cache cloudflare speed optimization](https://lh3.googleusercontent.com/yYaKQiIWuq-LTioCAyx_pD5PlkAn_MfDxFObdzg7pQzE5rpON8C85N4Z5iAgEOtY5Jc9TddwLfSsOA962vUyWNZz7b8uBSjdgiFrkbUW8FA-cqbY-FmFvrnzP4o7fNF7pe-VdAXS)</figure></div>5\. As you scroll down, you can find an option called Brotli. It is a similar compression technique like gzip. Turn this on.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Brotli settings in cloudflare](https://lh6.googleusercontent.com/TH0LAv4ZT_1zSIODYcJrXzJacji257dtqdas3nZceFb9Rc0jy7nOCJSa3and-gL_EOrtn0CxeXQPY74skfhiFW6CIOPQ4upF8NQt4TBI0gCeeD2cGOo0Q63A9qTKEdT42aBPQWKQ)</figure></div>If you prefer using gzip to brotli, turn this off before turning on gzip in w3 total cache settings. Here is a detailed article comparing both these compression techniques – [GZip vs Brotli](https://wp-rocket.me/blog/brotli-vs-gzip-compression/).

6\. Turn on Railgun. It improves website performance by using compression techniques, especially for dynamic content.

<div class="wp-block-image"><figure class="aligncenter is-resized">![railgun settings in cloudflare](https://lh4.googleusercontent.com/lO7T4UTMrZTllE-lhOdrWNHdV7W3Ty2BUGhFrnmPBFph7DcuAOhRAPxTmZ50QEZLQY7re3YA7Z2ndv0s_OFQgKYPcjWdkGc0g9ZOXI9eskck2RGbjXPITxea0MG3iGFvjKqA0GNC)</figure></div>Do not turn on minification. W3 total cache already does that for you. If you are sceptical about it, try out minification in W3 total cache settings and Cloudflare. After testing with both of them, choose the one which provides the best performance for your blog. But make sure not to turn them on at the same time.

To take speed optimization a notch higher, set page rules. Cloudflare’s free plan allows you to set 5-page rules. Here is a post that helps you set [Cloudflare page rules](https://onlinemediamasters.com/cloudflare-page-rules-for-wordpress/).

You have successfully created a performant website using W3 total cache and Cloudflare.

## <span class="ez-toc-section" id="how_to_purge_cache_in_w3_total_cache"></span>How to Purge Cache in W3 Total Cache<span class="ez-toc-section-end"></span>

In a few instances, making changes to a page will not be visible in real-time. In such cases, you need to purge the cache to view changes made.

To purge your website cache, log on to your WordPress dashboard.

At the top of your WordPress dashboard, you can find an icon called *performance*. Hovering over it gives you two options to purge cache,

1\. Purge All Caches – Clicking this purges all caches of the website.

2\. Purge Modules – With this setting, you can cache specific modules like minification and opcode cache.

In most cases, *purge all caches* would do the job. Once you have purged the cache, reload the site to view the updated changes.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Purging all caches in W3 total cache](https://lh4.googleusercontent.com/rtwWaHuYOue3Ufmx1-WSbFei_z01SQ-iv69TpEBiEZDEW-ctnIUal_k5X3sekzHD2FdJtKuAHweMc5tic_QQFoIxRReZRI4qW19kH7jqCkCXAtZzl0AL3dOTKQi5BCPdgIKbku28)</figure></div>## <span class="ez-toc-section" id="importing_and_exporting_w3_total_cache_settings"></span>Importing and Exporting W3 Total Cache Settings<span class="ez-toc-section-end"></span>

If you are in a hurry, you can [download these settings](https://drive.google.com/file/d/1WFK23pK643RIXEDxGt1VdoQOLr48xVqc/view?usp=sharing). And replace it with your current ones.

Note – These settings are for shared hosting environments

1\. Once you have downloaded the configuration, click performance from the left side of your dashboard.

2\. Click General Settings

3\. Scroll to the bottom of the page where you can find ”Import / Export Settings”.

4\. Click the button named “Choose file”. Upload your settings that you have just downloaded. Finally, click Save. All the configurations explained will be applied to your WordPress website with just a click.

<div class="wp-block-image"><figure class="aligncenter is-resized">![W3 total cache settings import/export](https://lh4.googleusercontent.com/XEGLGcmAJFoLK76fOt4jbcGljCHi8XQ0FSmsQgUi1fdYpPfnqOQBXhHouul-GbOk3vr9mGkIvKUDOkz68G2shNm5TA2SdS6bhiDp_etCU1ZiJAWFpTBKvaOi-OYLKkUb2sB669h5)</figure></div>If you are not satisfied with the recommended settings, click restore default settings to revert to the default configuration.

## <span class="ez-toc-section" id="other_things_you_could_do_to_speed_up_wordpress"></span>Other Things You Could Do to Speed Up WordPress<span class="ez-toc-section-end"></span>

Installing a cache plugin isn’t the only way to speed up a WordPress site. Here are a few tips to increase your site speed.

**1. Use a good hosting**

Cloudways Digital ocean is one of the most affordable yet powerful hosting providers out there. If you are serious about improving your website speed, consider switching from shared hosting to cloud hosting.

**2. Use fewer plugins**

Plugins are additional pieces of code that run every single time you load a website. The higher the number of plugins, the greater is the load and pressure on the website. This impacts shared hosting environments even worse.

Limit your plugin usage. A good rule of thumb is to keep your plugin count under 20. Try to install a single plugin that does multiple jobs. Remove plugins that you don’t need.

**3. Updating to the latest PHP version**

Update your website to the latest supported version of [PHP](http://149.28.53.131/update-php-on-wordpress/) to improve performance.

**4. Using a lightweight responsive theme.**

You can use a lightweight responsive theme such as Generate Press, Astra or Ocean WP. This helps you make your website load much faster.

**5. Compress your images**

Images play a crucial role in the performance of a website. The higher the size of the image, the longer is the load time.

Always compress and lazy load your images. I recommend using [ShortPixel](https://wordpress.org/plugins/shortpixel-image-optimiser/) for image compression.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

You have successfully created a performant website using W3 Total Cache free of cost. You have also improved your scores in GTMetrix reports.

## <span class="ez-toc-section" id="frequently_asked_questions"></span>Frequently Asked Questions<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1619838402829">### 1. **What does the W3 total cache plugin do?**

<div class="rank-math-answer ">W3 total cache improves the performance of your website by implementing several techniques like caching, gzip compression, minification. It reduces transfer time and enhances the performance of the website.

</div></div><div class="rank-math-list-item" id="faq-question-1619838434850">### 2. **How to check if the W3 total cache plugin is working?**

<div class="rank-math-answer ">Open your website in a new window, right-click anywhere on the website and click view page source. Now search for the term “Performance” by clicking Ctrl + F. If you find a section like the one mentioned below, you can ensure that W3 total cache is working.

</div></div><div class="rank-math-list-item" id="faq-question-1619838447967">### 3. **How to safely remove W3 total cache?**

<div class="rank-math-answer ">Disable all settings under general settings in w3 total cache. Now head to the plugin dashboard and scroll to the bottom to find w3 total cache. Deactivate and delete the plugin.

</div></div></div></div>