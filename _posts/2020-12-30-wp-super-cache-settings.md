---
id: 4152
title: 'Best WP Super Cache Settings With Cloudflare[2021]'
date: '2020-12-30T23:31:07+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=4152'
permalink: /wp-super-cache-settings/
rank_math_seo_score:
    - '89'
rank_math_focus_keyword:
    - 'wp super cache settings'
rank_math_title:
    - '%title% %sep% %sitename%'
rank_math_description:
    - 'Learn to configure wp super cache the right way using this step by step guide and make your website faster.'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
ss_social_share_disable:
    - ''
rank_math_internal_links_processed:
    - '1'
socialsnap_share_count_timestamp:
    - '2023-09-14 01:46:53'
ss_total_share_count:
    - '0'
rank_math_primary_category:
    - '16'
rank_math_analytic_object_id:
    - '12'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"1ff4f38b54cf2553637abaa6121fd5c2";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - 'cache settings'
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

*Caching* is the process of storing frequently visited web pages, locally. If a webpage is cached, your browser loads the files from your local storage instead of the server. It provides significant improvements to your website performance and saves your server resources.

*Leverage browser caching* is a high priority suggestion of *GTmetrix* report.

You can use **WP Super cache plugin to cache your website.**

WP Super Cache is most popular, yet has a major drawback. Setting up WP Super Cache is hard (even harder for *Nginx* users).

This guide **shows the best WP super cache settings**. It illustrates two methods,

1. Using WP Super cache
2. Using WP Super Cache with Cloudflare

If you are using an *Nginx* server, you need to edit the configuration file to make full use of WP Super Cache. A simple error in the configuration file may break your site. If you do not have experience editing the configuration files, I recommend to use [WP Fastest cache](http://149.28.53.131/wp-fastest-cache-settings/?swcfpc=1) plugin. **In [WP Fastest cache](http://149.28.53.131/wp-fastest-cache-settings/?swcfpc=1) you need not configure *Nginx* files, and the setup process is much simpler**.

## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

- **Backup your site** – Incorrect configuration of Super Cache **may** break your site. So it is always better to have a backup. I recommend you to use [*UpdraftPlus*](https://wordpress.org/plugins/updraftplus/).
- **Disable other caching plugins** – Enabling two caching plugins simultaneously hurts your website performance. I recommend you turn them off.
- **Cloudflare account(Optional)** – If you are going to use a Cloudflare in this guide, [sign up](https://dash.cloudflare.com/sign-up) for an account (Explained in step 7) Else skip this.

## <span class="ez-toc-section" id="step_1_%e2%80%93_installing_wp_super_cache"></span>Step 1 – Installing WP Super Cache<span class="ez-toc-section-end"></span>

Install and activate WP Super Cache from your Plugin Dashboard

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp super cache installation page](https://lh6.googleusercontent.com/X2tbiZYKJ_CobWXylOwTsQYFBcJJjNl300oawSG6yCu7TVQ5JjpkJx2KPmtxqDLbTo_SLZ2HrICZq7MKChwmhQGahGz_UeYzG7WN426jj2jmGwanICI3DXYPtrr9g0I-BkXYiFYV)</figure></div>WordPress takes you to the installed plugins dashboard, on WP Super Cache activation. Scroll down to the bottom where you can find WP Super Cache. Now **click *Settings***

<div class="wp-block-image"><figure class="aligncenter is-resized">![wp super cache settings page](https://lh5.googleusercontent.com/caaExjTkXX4e9oslwKJDznmfLcvdZRvQN78r8BXR_EElJbt0a3TLoDbmk-A-R_mWEPcUexUbEZy7nrQ2oNlXKxzvH3qkiTgqP_SdDs1AMQKO_sGtFvNg_k7XkPdWy2hGsu2LQ5fn)</figure></div>## <span class="ez-toc-section" id="step_2_%e2%80%93_configuring_wp_super_cache_%e2%80%93_easy_settings"></span>Step 2 – Configuring WP Super Cache – Easy Settings <span class="ez-toc-section-end"></span>

**Caching –** The easiest way to boost the performance of a website. ****Enable this**.**

Once enabled, click on *Update Status* to save this configuration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![easy settings of wp super cache](https://lh5.googleusercontent.com/JkdPof4bGhZbFlf-HDJM_lEyOfromB5DrAxtAfz970YDBagqxS_r87AlWu4JH8uvSbuoCzO6iPCpFZ0X1zKnQPT6c_8KZiHnR4O9I0KfAImpE-if9UkD-FPZMbbjxsHvdPjPQ-2A)</figure></div>Besides turning on caching, WP Super cache provides you with few tools to manage it. You’ll set them in next steps.

**Test cache (Does not work if you use Cloudflare)-** You can test if WP Super Cache works by clicking this.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cache tester](https://lh6.googleusercontent.com/9cHLFZJjWw6vKxOi0sKEfMdfuGlivulXLKlmYT0xpkalsvINY7tR3LDsDm3m_X3ga1nMAtTEsAZ7l9a3AWr_Yw4G56MLNLJdwGOdjqzI5E1HoiMM7WXoOXItm3y5hCOhnv4f8Xjs)</figure></div>**Delete cache –** If you see an older version of your page, click this to delete your website cache. It helps you view the latest content of your site.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Delete cache button](https://lh5.googleusercontent.com/tsUOYWTD7gTXiL-ETbwY_msI8PPu87DPrrBd82OAQa3e1d1h7iJ0EQH5OVIgQvweTTaOAkyz7Ffmm5eE_msJAY_7EdnbH40A5rUkiE-vue39cqvni4Og_OV8di2chK8E1Kkp9ijl)</figure></div>## <span class="ez-toc-section" id="step_3_%e2%80%93_configuring_wp_super_cache_%e2%80%93_advanced_settings"></span>Step 3 – Configuring WP Super Cache – Advanced Settings<span class="ez-toc-section-end"></span>

Click on the advanced tab.

**1.** **Enable caching –** If it is not already on, **Enable this**.

**Miscellaneous settings**

**2.Cache delivery method –** WP super cache uses two ways to serve cache files.

**Simple caching** – Simple method uses PHP to serve cached static files. It is enough for most websites. **Enable this**.

**Expert caching** – Expert method provides better performance than simple caching. It uses an Apache module for serving files.

To use this method, you need to tweak your .htaccess file and set up mod\_rewrite module.

In addition to this, you need to set custom rules if you host your site on an Nginx server.

If you are not confident about what you are doing, do not make any changes to the .htaccess or Nginx Configuration file. A small error could break your site.

**3.Cache restrictions**

1.**Enable caching for all visitors –** Displays cached pages for all visitors, including yourself. This prevents you from viewing live pages of your site.

2.**Disable caching for visitors who have a cookie set in their browser –** If the visitor sets cookies, live content is served. This takes a toll on site performance.

3.**Disable caching for logged-in visitors –** Enables caching for all visitors except admin. This helps you view live pages without consuming a ton of server resources. **Enable this.**

<div class="wp-block-image"><figure class="aligncenter is-resized">![Advanced settings of wp super cache](https://lh6.googleusercontent.com/AUIcOF0SyX6Yxu8BdSf7IhrOmpCX_-qHBlTKDZAe-ZkEsYAwJcInCi_WDyNFGpf6GHxAYz4SGs82B-l5FThVTYpJ1G4nqUiSO5g5E9y_f8zi3NfOt-x4TSd41uflPOXw2mIvAqpd)</figure></div>4.**Do not cache pages with GET parameters –** It caches the same page that is unique for different users. Ex: The same google ads will be displayed to two unique visitors. No personalized ads = reduced probability of a user clicking an ad. **Leave this off.**

5.**Compress pages so they’re served more quickly to visitors (Turn off if you use Cloudflare) –** a.k.a Gzip Compression. It helps you compress the elements of the site before transfer. Reduces transfer time and improves performance by 85%. **Enable this.**

Gzip compression is a high priority item in *GTmetrix report.* Cloudflare users will use a similar compression method called *Brotli*.

6.**Cache rebuild. Serve a supercache file to anonymous users while a new file is being generated –** Shows an older cached version of the site when a new cache file is generated. **Enable this**.

7.**Cache HTTP headers with page content –** Makes PHP file delivery slower in exchange for increased speed in static file delivery. Simple caching uses PHP file delivery to serve static files and enabling this slows the process. **Leave this off.**

8.**304 Browser caching. Improves site performance by checking if the page has changed since the browser last requested it. –** Tells the browser if a page is updated since the browser last requested it.

**If the page is updated –** Browser re-caches the new files from the site.

**If the page is not updated –** Browser loads files from visitor’s local storage.

Provides a significant performance boost. **Enable this.**

9.**Make known users anonymous so they’re served supercached static files –** This setting overrides the earlier setting, *Do not cache pages for known users* (Option 3)  and serves static files for everyone. **Leave this off.**

Non-Cloudflare users will have the following configuration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Advanced setting configuration for non-Cloudflare users](https://lh5.googleusercontent.com/Zz2OvVTC2kfJDtJFfFTxLjOnOpbuCwUy6ScXXyEflO7gzNKJN6hcXmZ1P8MCH-x0XI5-SV-W7EVkrI5-FacaUOptBrL9WnfBgza3ZumDuBq7o4_5P-K1ztnUy7CmqkD-QBgKtQ4Y)</figure></div>Cloudflare users will have the following configuration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Advanced setting configuration for Cloudflare users](https://lh6.googleusercontent.com/ZcMutusPCMe6feeVNzNxAgO884V2Nn9DSP2KBC_s3dI93Uq-bcm1WIoKnz6C-hAMQ3i6ciiKHteaB6p5eZ_i-qoCpEsBEDQtGqnQYdysZ8nlwS3V8Z_YwZLhvZLJqXlccBskJNuH)</figure></div>**Advanced settings**

10.**Enable dynamic caching –** Enables caching of dynamic modules such as Google ads and share count. **Leave this off.**

11.**Mobile device support –** (Requires extra plugins to work) – Responsive website themes adapt to the device it is displayed on. Non-responsive themes don’t. To make your non-responsive themes responsive, **enable this.**

Install any one of the following plugins and configure them to complete the process.

1. [Wp Touch](https://wordpress.org/plugins/wptouch/)
2. [WordPress Mobile Pack](https://wordpress.org/plugins/wordpress-mobile-pack/) – (Untested with 3 major releases of WordPress, may have compatibility issues)

**Leave this off** if you use a responsive theme.

I recommend you to switch to a lightweight and responsive theme if you have not changed yet. [OceanWP](https://wordpress.org/themes/oceanwp/),[ Astra](https://wordpress.org/themes/astra/) and[ Generate Press](https://wordpress.org/themes/generatepress/) are great options. This is because non-responsive themes are not mobile-friendly and mobile-friendly pages are a crucial part of Onpage SEO.

12.**Remove UTF8/blog charset support from .htaccess file –** If your site displays incorrect punctuation marks or odd characters enable this. Else **leave this off**.

13.**Clear all cache files when a post or page is published or updated –** Clears cache files when a post/ page is updated. This allows visitors to view fresh content. **Enable this.**

14.**Extra home page checks –** Makes sure that your latest posts are visible on your homepage. **Enable this.**

15.**Only refresh current page when comments are made –** Useful if your site receives a ton of comments. Helps you re-cache those pages with new comments instead of re-caching the entire site. This allows visitors to view the latest comments, with little expense in server resources. **Enable this.**

16.**List the newest cached pages on this page** – Shows a list of cached pages for the visitor. **Leave this off**.

17.**Coarse file locking. You do not need this as it will slow down your website – Leave this off**.

18.**Late init. Display cached files after WordPress has loaded –** Fixes the error, *super cache dynamic page detected but late init not set*. **Enable this.**

19.**Cache location –** The default cache location works well. **Leave this unchanged.**

The following would be the resulting configuration for both Cloudflare and non-Cloudflare users.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Other settings in advanced tab](https://lh3.googleusercontent.com/admggQsnp9kH1NH8Q5HbAiWj3mA0Cy1_lSwgvN6j4czmt1aCJY411CNTZ1Ik8ebbvNn2AzXHEkycNjIn2BXL0HNXC4qWzo-BxbcMDXZdwv9YovGaZysE6qqqkebJgAx2Lvx-Fqgu)</figure></div>Click *Update Status* to save your changes.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cache location and Update status button](https://lh5.googleusercontent.com/TZR57Y41zfGR42kd7fsVM5b-t73ShVbH5jCb4DdQTXmAXtVQcsXJxqirEVwvcOKxXuH1Mu9DPtjOPGRPO12QqQ9l5rZpG-T4TRx69hzxn039tw1KaUXdOTlrxlExftP-1u-zTkTT)</figure></div>## <span class="ez-toc-section" id="step_4_%e2%80%93_configuring_cache_settings_of_wp_super_cache"></span>Step 4 – Configuring Cache Settings of WP Super Cache.<span class="ez-toc-section-end"></span>

1.**Cache timeout –** Determines the time interval at which pages are re-cached and served.

Set cache timeout to 3600 seconds, unless you have high traffic site. If you do, set it 1800. This determines life of a cached page. The lower the cache timeout, the faster your server resources get consumed. If the timeout is very high, cached pages may not be visible to your users.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Garbage collection settings](https://lh5.googleusercontent.com/JgbcRT4eEMxESjn8ebbY84-XveAa8tUp3hkdvVmmWpDKvoUA23XuJMCsz74qqCZ0pee-3V9qQLP5W2ErlW2AsClzFiL_u9e6BQlllX8_kpf8BIjVw6Udg7Kgk_AKXUhU4K1IqQVj)</figure></div>Now click Change Expiration.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Change Expiration button](https://lh4.googleusercontent.com/5kII9Eloe-6YAfuQf-6vs4JlnBhm7pgS-h9ruYsxjle5YJnXt5Ly3QD69KdXRpro0ap7f2a-TgVDuQLozIgv9wbKrc1nb5JeX3wq6SvLOFce6RAV8UBG3svLyAZGDjmOjQcozpjX)</figure></div>2.***Accepted file names and rejected URIs (Optional)-*** Specify page types, which you do not wish cache. Ex: e-commerce pages. Once you have chosen page types, **click Save settings.**

<div class="wp-block-image"><figure class="aligncenter is-resized">![Save settings button](https://lh5.googleusercontent.com/pws8XqG8M5bRUQIE5OltAURIfAuswY_wVE_6aTj4NQUH9izQtrmdoMJMDjCogIvGGQPFwBknFw-oxejGTtnraS35QtwDRcCwx4iPHnskH43R_pCrUVi5ZrklBO0ggK9xFMx4hKlc)</figure></div>3\. ***Strings (Optional) –*** Detects similar strings from URLs and forces a page not to be cached. For example, if you specify the string as ‘/2019/’, URLs containing the string 2019 will not be cached. **Click *Save Strings*** once you have added required strings.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Save strings button](https://lh3.googleusercontent.com/CmjNFR-GSRKoAVfgaQZ_l173W9cEJ5gxjIT2OlZcPs2gHJ3VuJONBobVwxwE_sBNHL1ChV7JTWuFSV9sEASSD2irfFzVzaKzaCkMaz_Xzc7h16CNX_nnHdqmBwBFIEyCyf-tsGvX)</figure></div>4.**Filenames (Optional) –** Using the strings feature, you have disabled caching for URLs with the string 2019. Posts published in 2019 are not cached. Now, what if you wish to cache a specific post from 2019*?* This is where filenames feature helps.

Add filenames of pages which you do not wish to cache in the filename box. In this case it’s *cache-page.php.*

Using this method, you can cache specific files even if you have excluded them in Strings.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Save files button in filename settings](https://lh4.googleusercontent.com/xWaj6oxhfsyA4u5wED4cCRXzPD9YAqT7ysAqctZV2N-QNDa0EJ4r2pJTeUT0hVKTFXOVU7wohZDpJZRTSShwPXCF-uqS9ZLbFFVaa0apV8piD8OaiaL5iTYjGn_2Hc2tEisEtetc)</figure></div>Once you’ve added them, **click *Save Files****.*

5.**Rejected User Agents(Optional) –** Prevents user agents search engines from viewing cached pages. Leave this untouched. Because accidental deletion of Google’s crawler bot causes google to view cached pages. This may lead to poor rankings.

<div class="wp-block-image"><figure class="aligncenter is-resized">![rejected user agents settings](https://lh5.googleusercontent.com/LnknVmFetxF8QPG206_Dc2A32sJaEclVxaXaxk_eqAlAQt6QV-OpGHTxnqO-PFx2PuKwthW_d41dJ3RGGTfUChYNy5iI3ZKovvB2Yx2wvch_9k1f393SogEJ7Nr-yg9-d6Wf8Umj)</figure></div>***Leave this box untouched***

6.**Lock Down(Optional) –** Enable only if there is a significant increase in site traffic within a short period. This prevents websites from crashing.

Turning this on overrides our earlier setting, *doesn’t cache separate pages when a new comment is posted(Advanced settings option 15).* A new cache is not generated even when a new comment is posted. It preserves server resources and prevents your site from crashing.

<div class="wp-block-image"><figure class="aligncenter is-resized">![lock down settings](https://lh5.googleusercontent.com/2n7F55xUfR6sQndjr49pK9TizE0UoSFILAIZE0QUC2_Dh4lIl3tz1YhPT0dC_qxEnm_KdyJB6saRp5v9M0Oq-EVWOacSCkQbV-Y8oAi-I5fe0HfEH1TUsjisJ4N1vQr5R-l5zbCt)</figure></div>## <span class="ez-toc-section" id="step_5_%e2%80%93_optionalunderstanding_contents_settings_of_wp_super_cache"></span>Step 5 – (Optional)Understanding Contents Settings of WP Super Cache<span class="ez-toc-section-end"></span>

Your site’s cached pages expire automatically. This prevents visitors from viewing stale content.

But if your cached pages don’t expire due to errors, you can clear them off using the *delete cache* button. This clears your entire cache database.

If you want to clear cache files of a specific page, you can click *list all cached files*, find pages you wish to refresh and delete their cache.

<div class="wp-block-image"><figure class="aligncenter is-resized">![contents tab](https://lh6.googleusercontent.com/bq43L-Q50hW37aQ_0SWyJFYcCEbOizhT-88l0Yx6qtGUMr4Fk4BzfIsAhtDZ2EfKlVsHsfD74bRJZOJJg5Guz2oJ2vOB-0e2rgQAmY1IAPL2WyXrrx9q0iMn-B6g1wKlS9EaaRUx)</figure></div>## <span class="ez-toc-section" id="step_6_%e2%80%93_configuring_preload_settings_of_wp_super_cache"></span>Step 6 – Configuring Preload Settings of WP Super Cache<span class="ez-toc-section-end"></span>

Navigate to the Preload tab.

<div class="wp-block-image"><figure class="aligncenter is-resized">![preload setting configuration](https://lh5.googleusercontent.com/w6USD8HRaH1NT5ALBI5TE327WpWWpEiYM6iflPuXYoYHjDcuHal6MBrmuFGkumPCl-eyHvpq7Rc755gJ7EigZ1n_YkFf3otgd245K6UQ1a8bmpEtBpCvVA6qWbavbF6m935JFiNb)</figure></div>Preload caches all your website’s posts and pages periodically. Here, the time interval is a critical setting.

If you don’t update your site twice a day/ use shared hosting, I recommend you set it to 1440 minutes. (1 day). It’s not recommended to set the time interval to lower values. This is because recaching consumes a ton of server resources and may exhaust your monthly bandwidth (especially in shared hosting environments) and overloads your server.

If you update your website twice a day, set it to 720 minutes. You can also set this value to 0 if you don’t want static files to expire until you manually refresh the cache.

**Enable this** to improve indexing and website speed. Select *preload mode(garbage collection disabled. Recommended)*.

## <span class="ez-toc-section" id="step_6_%e2%80%93_optionalconfiguring_plugin_settings_of_wp_super_cache"></span>Step 6 – (Optional)Configuring Plugin Settings of WP Super Cache <span class="ez-toc-section-end"></span>

Leave this tab unchanged, unless you use any of the following plugins,

1. [Bad Behavior plugin](https://wordpress.org/plugins/bad-behavior/)
2. [WordPress MU Domain Mapping plugin](https://wordpress.org/plugins/wordpress-mu-domain-mapping/)
3. [WPtouch plugin](https://wordpress.org/plugins/wptouch/)

If you do use any one of the above plugins, Click *Enable* and *Update.*

<div class="wp-block-image"><figure class="aligncenter is-resized">![Additional compatible plugins](https://lh5.googleusercontent.com/9K1so8UyFLXl7lwR0GViqzDSZhfuPaHxCmPJZSvIyktKLZtAijPKvmmCfTic7lo2eEoKwjT89RnBtkOb4HE_aMuzZ2AVqz1H9E_MVD-R5KXlwsmNJR7yExXY_P2jq4KUnq0SBFlw)</figure></div>Leave the debug settings and CDN settings undisturbed.

You’ve successfully configured WP super cache settings and made your site faster.

If you’re a Cloudflare user, continue to the settings below.

## <span class="ez-toc-section" id="step_7cloudflare_users_only_%e2%80%93_configuring_cdn_settings_of_wp_super_cache"></span>Step 7(Cloudflare Users Only) – Configuring CDN Settings of WP Super Cache <span class="ez-toc-section-end"></span>

CDN(Content Delivery Networks) refers to geographically distributed servers around the globe. It uses intermediary servers to reduce the physical distance between the User and the Origin Server.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare working diagram](https://lh4.googleusercontent.com/V4x-4rLwLw9QTexcy63mHiPs-Ps5NlQCm-BAnQa_YhLw8vDHISlqMqPWYKVVODpnw2QojtHdAuoFGrOtH7F4UPLnX-OeVkSkqOLMMpuftsQKVqxS5nRc09RM_Nye4gawBhA3ycjL)</figure></div>Using a CDN is a crucial recommendation in *GTmetrix* report.

1.Login to your cloudflare account.

2.Once you’ve signed up, enter your website name and choose the free plan. Finally, **click *Confirm plan.***

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare plans](https://lh6.googleusercontent.com/haFo72RNJplFiwymb3bqNqB9puqdgOCjz-PI4wSsaFPyJNcWnXFur3C6csieNX_pe9yh7DmlpiejJ0B98lNZQP_7pDNmXSiFfnHuPz1hKGvueEpCP5CkKDXmkmsmsSf2fIZlZPt_)</figure></div>3.Cloudflare gives you two *nameservers*. Replace your existing nameservers with the ones provided by Cloudflare in your *CPanel*. Most hosting providers provide an option to activate Cloudflare in your CPanel.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare name servers](https://lh5.googleusercontent.com/5xn5Qcb1SCyJVA9sFvm29vquli97OltMIZmt-Ka1PLb9fNkKAT2GlN5BTZ_EvH15DgtcOytV41jPq0yKiiicNjp5sYkyYw-ysDXDuDsY7-GMGjbyyLe9iIeAeXdmC9cgSxzmgqXk)</figure></div>Here’s a list of instructions for [changing your nameservers on popular hosting providers](https://support.cloudflare.com/hc/en-us/articles/205195708-Changing-your-domain-nameservers-to-Cloudflare). If you cannot find your hosting provider, perform a google search or contact them for support.

4.Navigate to [speed settings of Cloudflare once you have changed the name servers](https://www.cloudflare.com/a/performance/). **Click Optimization**.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare speed settings](https://lh3.googleusercontent.com/xrOjjWM92FZhZPXlQX3g2iIx1c4GuBs2uTq-CwoSe-uAtPXUHnIFzAByeTNpk8hToeF13BW6YXUTC3qKEdlBUzzbTdoCEzrezem3Sl5u-f-8QCigutUG-sD-J_wLqGp02H7C5sAx)</figure></div>5.Scroll down to find Brotli. It’s a similar compression technique like Gzip. **Turn this on**.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Cloudflare brotli settings](https://lh3.googleusercontent.com/rpJ70oYMK10GmOLiLO0yXVkBZ_zbGh1b_5jzUfPownIT742E-qHmrzgY2B76fPrxBFSTI1HHznsggjFTMDUT_aXfBroXaAfz_5yTTQViNLJc8G1puTBZhj4vvmuG6WkaNcdaeTp8)</figure></div>But, if you wish to use GZip, turn this off before turning on Gzip from the basic settings panel of WP Super Cache. Here’s a post comparing both compression methodologies – [GZip vs Brotli](https://wp-rocket.me/blog/brotli-vs-gzip-compression/).

6.Enable *Railgun*. It aids in speed improvement by leveraging compression techniques, mainly dynamic content.

<div class="wp-block-image"><figure class="aligncenter is-resized">![Railgun settings](https://lh6.googleusercontent.com/XE8fQS3K2jvYq6V-Ixl552i89WFeoxMU4fof998fqRJQQZpyB1BjiDeM8F7ahYzqcdkLwAVlszKFmwe9_UXM-qoKQ-vQv9TGkrcXSNtk9fc49iETbiVm1cZ6AJKQy7bUpSWRQdyB)</figure></div>You shouldn’t turn on minification in Cloudflare because WP Super cache does that for you. Feel free to set page rules and configure other settings of Cloudflare **ONLY IF** you know what you’re doing.

You have successfully configured WP super cache along with Cloudflare to create a performant site.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

To summarize, you’ve configured WP Super cache settings. You have also used Cloudflare to improve website performance.

## <span class="ez-toc-section" id="what%e2%80%99s_next"></span>What’s Next<span class="ez-toc-section-end"></span>

Caching is not the only way to make your site faster. As a WordPress user, you can also do a few other things to make your website faster

1. [Update to PHP to latest Version](http://149.28.53.131/update-php-on-wordpress/)
2. Remove the bloating plugins
3. Use lightweight themes such as GeneratePress and Astra
4. Use Fast hosting such as CloudWays.

## <span class="ez-toc-section" id="faq"></span>FAQ<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1609349856936">### 1. What other performance plugins do I need besides WP Super Cache?

<div class="rank-math-answer ">Besides, WP Super Cache, you can use   
1\. [OMGF](https://wordpress.org/plugins/host-webfonts-local/) to localhost your google fonts.  
2\. [CAOS](https://wordpress.org/plugins/host-webfonts-local/)(if you use google analytics) to localhost google analytics.  
3\. [WP-Optimize](https://wordpress.org/plugins/host-webfonts-local/) to optimize your database   
4\. [TinyPNG](https://wordpress.org/plugins/host-webfonts-local/) for image optimization and lazy loading.   
All the above mentioned plugins are free

</div></div><div class="rank-math-list-item" id="faq-question-1609350071013">### 2. Which are the best cache plugins for WordPress?

<div class="rank-math-answer ">WP Super Cache, WP Fastest Cache are some of the best free caching plugins. If you’re ready to invest in a premium plugin, I recommend WP Rocket.

</div></div><div class="rank-math-list-item" id="faq-question-1609350275675">### 3. How do I clear WP Super Cache’s Cache files?

<div class="rank-math-answer ">Navigate to WP Super Cache Settings, click on the *Contents* tab and click *Delete cache.*

</div></div><div class="rank-math-list-item" id="faq-question-1609350318188">### 4. How do I uninstall Wp super cache?

<div class="rank-math-answer ">Before deleting WP Super Cache, go to WP Super Cache settings page and turn off all caching. *Delete Cache* using the button available at the bottom of the same page. Now deactivate and delete the plugin via the plugin dashboard.

</div></div><div class="rank-math-list-item" id="faq-question-1609350344984">### 5. Is WP Super Cache free?

<div class="rank-math-answer ">WP Super Cache is a free plugin packed with a ton of features from caching to Gzip compression.

</div></div></div></div>