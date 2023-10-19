---
id: 2671
title: 'How to Localhost Google Analytics?[in 5 Mins]'
date: '2020-09-29T01:31:26+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://139.180.139.123/?p=2671'
permalink: /localhost-google-analytics/
rank_math_seo_score:
    - '81'
rank_math_internal_links_processed:
    - '1'
rank_math_focus_keyword:
    - 'localhost google analytics,local analytics,localhost google'
rank_math_description:
    - 'A step-by-step guide that helps you localhost google analytics and fix the leverage caching issue found in GTmetrix report.'
ss_social_share_disable:
    - '0'
tcb2_ready:
    - '1'
socialsnap_share_count_timestamp:
    - '2023-09-12 06:47:23'
ss_total_share_count:
    - '0'
rank_math_analytic_object_id:
    - '34'
rank_math_og_content_image:
    - 'a:2:{s:5:"check";s:32:"b0b54db5eb725ff93c89736e1ebd1161";s:6:"images";a:0:{}}'
categories:
    - how-to
tags:
    - tutorials
---

## <span class="ez-toc-section" id="introduction"></span>**Intro**duction<span class="ez-toc-section-end"></span>

If you use Google Analytics on your blog, you will find the leverage browser caching suggestion in your GTmetrix report.

What does this exactly mean?

Whenever your site loads, there’s a Javascript file called *analytics.js*(about 18kb) that loads with your website every single time. It’s responsible for tracking user demographics and other useful statistics in real-time.

This adds more seconds to your site’s load time. As we know, *higher load-time leads to poor user experience.*

<figure class="wp-block-image is-resized">![leverage browser caching issue](https://lh4.googleusercontent.com/dmEG97xXJydgWQpNg6BHRR4wK2SsX2P3W9kjTbqRmZBCgrGDbfclFFnWnRONtEL9THEj8-zG5IV21THX8Rr7FTP5rjI-cdy3tCBGnWXZ6Ky6egST7sE0lJiInZuhYwKvAzsqcH1l)</figure>The solution? You can localhost Google analytics.

It is done by *caching* the .js file locally in the user’s browse. Instead of loading the file via google server, it loads the file from the user’s device. By the end of this tutorial, you would have made your slow site into a lightning-fast site.

There are a variety of plugins to achieve this. I recommend four of them. (2 free and 2 premium plugins)

## <span class="ez-toc-section" id="advantages_of_local_hosting_google_analytics"></span>**Advantages of Local Hosting Google Analytics**<span class="ez-toc-section-end"></span>

1. Minimize DNS lookups
2. Fix *leverage browser caching* warning in GTMetrix
3. Boost your website performance
4. [Google loves you more](https://developers.google.com/web/updates/2018/07/search-ads-speed)

## <span class="ez-toc-section" id="drawbacks_of_hosting_local_analyticsno_plugins_used"></span>**Drawbacks of Hosting Local Analytics(no Plugins Used)**<span class="ez-toc-section-end"></span>

Though there are plugins to achieve this, people sometimes opt into the non-plugin way. For which there are a few disadvantages to be considered.

1. It’s difficult to update the .js file regularly as google updates its .js files periodically.
2. Creating a CRON job to do this automatically is not for not techies. Though you do this by scheduling a cron job in your CPanel account, not everybody is comfortable to get their hands dirty by messing with codes.

Note: Using a plugin resolves all these disadvantages

## <span class="ez-toc-section" id="backing_up_your_analytics_data"></span>**Backing Up Your Analytics Data**<span class="ez-toc-section-end"></span>

It’s ideal to backup your Google Analytics data in case anything goes wrong. Though the chances are between slim to nothing, it’s still a good safety measure.

**Step 1** – Sign-in to your Google Analytics dashboard

**Step 2** – To your left, you can find a column called reports.

<div class="wp-block-image"><figure class="aligncenter size-large">![Find the reports column](https://139.180.139.123/wp-content/uploads/2020/10/av0.png)</figure></div>**Step 3** – Click on the report you wish to export. (in this case, it’s the audience overview) Note: Select the desired date range as the report’s data is similar to what you view on the screen.

<div class="wp-block-image"><figure class="aligncenter size-large">![Hit export](https://139.180.139.123/wp-content/uploads/2020/10/av1.png)</figure></div>**Step 4** – Hit export and click your desired format to download your backup. The file would automatically be downloaded to your local disk.

Now that we’ve backed up our analytics data, let’s make your site faster.

## <span class="ez-toc-section" id="plugin_1_%e2%80%93_caos_%e2%80%93_complete_analytics_optimization_suite_free"></span>Plugin 1 – CAOS – Complete Analytics Optimization Suite (Free)<span class="ez-toc-section-end"></span>

CAOS is one of the free yet highest rated plugins in the market.

**Step 1 –** Install and activate the plugin via your plugin dashboard.

<div class="wp-block-image"><figure class="aligncenter size-large">![Install CAOS plugin](https://139.180.139.123/wp-content/uploads/2020/10/av2.png)</figure></div>**Step 2** – Open CAOS settings.

<div class="wp-block-image"><figure class="aligncenter size-large">![Click settings](https://139.180.139.123/wp-content/uploads/2020/10/av3.png)</figure></div>**Step 3** – Open a new tab and navigate to your Google Analytics dashboard.

**Step 4 –** In the search bar type admin and hit enter.

**Step 5** – In the property menu, select the desired property(your website)

**Step 6** – Click on *tracking info* &gt; *tracking code*

<div class="wp-block-image"><figure class="aligncenter size-large">![Choose Tracking Code](https://139.180.139.123/wp-content/uploads/2020/10/av4-2.png)</figure></div>**Step 7** – Copy the tracking ID. (UA-XXXXXXXXX-X)

**Step 8** – Paste in the Google Analytics Tracking ID.

Choose *“Always”* if your blog collects only anonymous data or it doesn’t use any cookies.

Choose *“when cookie is set”* or *“when cookie has a value”* if you wish to [configure your website with a cookie notice](https://daan.dev/wordpress/gdpr-compliance-google-analytics/).

.![](https://lh5.googleusercontent.com/_kPr_DQO42wYmFc5Eh-aA_7SDqWowG9cla8tepC82nTpIFcUq3bmChMMHqshWtzyQL50ZNDRK9CoHp_rmRuj7X5bDC8WiEx__dUla6U8X85EVIjCakUDUMBkaSJFIbd-lzAfsywI)

**Step 9** – Configuring Snippet Type

Leave it as default for accurate statistics.

Choose *asynchronous* for a little boost in performance. This *eliminates render-blocking resources* which increases website speed time.

Choose Minimal Analytics If you only need pageview stats. This boosts your website performance significantly at the cost of other stats.

**Step 10** – Anonymizing IP

Turn on *“anonymize IP”* to prevent IP Tracking. . This is required by law in some countries.

Though you cannot view user’s IP addresses in your reports, google collects and strips them before processing the report.

**Step 11** – Positioning the Tracking code

Position the code in your *footer* if you have a fast-hosting. Else leave the setting unchanged.

Finally, *save changes*.

## <span class="ez-toc-section" id="plugin_2_%e2%80%93_swift_performance_lite_free"></span>Plugin 2 – Swift Performance Lite (Free)<span class="ez-toc-section-end"></span>

Swift performance lite is a simplified version of CAOS with additional features like *lazy loading*, *CSS, JS optimization*.

Install the plugin and click bypass Google analytics and paste your *tracking ID*

Now click *anonymize IP* to prevent IP tracking.

<div class="wp-block-image"><figure class="aligncenter size-large">![localhost google using Swift performance lite](https://139.180.139.123/wp-content/uploads/2020/10/av5.png)</figure></div>## <span class="ez-toc-section" id="plugin_3_%e2%80%93_wp_rocket_paid"></span>Plugin 3 – WP Rocket (Paid)<span class="ez-toc-section-end"></span>

It’s a single plugin that packs more features than one could ask.

Most importantly it’s easy for newbies to set it up without going through the hassle of reading guides for setting up the plugin.

Under Google analytics turn ON, and you’re done.

<div class="wp-block-image"><figure class="aligncenter">![hosting google analytics locally using WP Rocket](https://lh4.googleusercontent.com/iN125xNaUaLU69JSre23suJ4YKCKpEXcswACl1Tw4HDoLxeocJTdBGVlWPi5BIVIrWcF_TD53Z-vm70-L77dSEowguMSe-CE_OhiYBtdP1SkSOJ1srcqN6-n9DPhpVY24CmMz442)</figure></div>In addition to this, the plugin offers a plethora of features like *Page caching*, *localhost google analytics*, *Gzip compression*, *Defer JS loading*, *eliminates render-blocking resources*, *Optimizes google fonts*, *Database Optimization* and a lot more.

Out of the four featured plugins, this stands out because of its simplicity and elegance.

## <span class="ez-toc-section" id="plugin_4_%e2%80%93_perfmatters_paid"></span>Plugin 4 – Perfmatters (Paid)<span class="ez-toc-section-end"></span>

Like WP Rocket, Perfmatters is yet another great plugin which offers many features for half the price of WP Rocket.

Once you install the plugin, paste your *tracking ID*, set the tracking position as a *footer* (only if you have a fast hosting provider), choose *your script type* and *anonymize IP.Disable display features* as it generates a second HTTP/2 request and leave the other settings unchanged.

<div class="wp-block-image"><figure class="aligncenter">![localhost google analytics using perfmatters](https://lh6.googleusercontent.com/4vQAdFuPyK0sqr3nYsf6-9ztzRZmT8sap3sa12KZ6VTn8Ld-6E_gsRPvx_zErmPzK5z6uaz6FQywB0LSUbIXCua_U6nf0D62d3_n90AAtpgVxszVAOnL_oiCMvpiGETih6GMmuTb)</figure></div>## <span class="ez-toc-section" id="conclusion"></span>**Conclusion**<span class="ez-toc-section-end"></span>

To summarize, you’ve optimized your WordPress site speed by local hosting google analytics. You’ve also resolved the *leverage browser caching* issue by minimizing the extra DNS lookups.

Feel free to ask questions if you have any doubts in the comments.

## <span class="ez-toc-section" id="faq"></span>FAQ<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1604372746417">### 1. How do I host locally in Google Analytics?

<div class="rank-math-answer ">You can use any of the four mentioned above plugins to localhost google analytics

</div></div><div class="rank-math-list-item" id="faq-question-1604372982847">### 2. Does Google Analytics work on Localhost?

<div class="rank-math-answer ">Yes, you can localhost google analytics by copying the tracking code into any one of the above-mentioned plugin’s tracking ID.

</div></div><div class="rank-math-list-item" id="faq-question-1604373070754">### 3. How do you resolve leverage browser caching?

<div class="rank-math-answer ">You can resolve leverage browser caching issue by locally hosting google analytics. You can use CAOS, Swift Performance lite, WP Rocket or Perfmatters.

</div></div></div></div>