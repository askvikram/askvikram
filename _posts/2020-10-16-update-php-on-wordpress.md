---
id: 2758
title: 'How to Update PHP on WordPress [In 5 Minutes]?'
date: '2020-10-16T17:46:47+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://139.180.139.123/?p=2758'
permalink: /update-php-on-wordpress/
rank_math_seo_score:
    - '82'
rank_math_focus_keyword:
    - 'update php on wordpress'
rank_math_description:
    - 'This guide explains step-by-step procedure to safely update PHP on WordPress on both shared hosting and dedicated hosting, without breaking your website. '
rank_math_title:
    - '%title%  '
rank_math_internal_links_processed:
    - '1'
rank_math_primary_category:
    - '16'
ss_social_share_disable:
    - ''
tcb2_ready:
    - '1'
ss_ss_share_count_facebook:
    - '3'
socialsnap_share_count_timestamp:
    - '2023-09-12 12:01:06'
ss_total_share_count:
    - '3'
rank_math_analytic_object_id:
    - '33'
image: /wp-content/uploads/2020/10/how-to-update-php-in-wordpress.png
categories:
    - how-to
---

PHP is a scripting language used to create responsive and interactive websites. WordPress is developed using PHP. PHP Developers fix vulnerabilities and provide several improvements with every PHP update. Staying updated with the latest version of PHP secures your website from cyber-attacks and gives an immense boost in performance.

You should update PHP on WordPress if,

1. Your site is slow
2. Your site undergoes a lot of online attacks
3. For improved performance and security

Using this guide, you will update PHP on WordPress to the latest version and make your site faster and secure.

## <span class="ez-toc-section" id="advantages"></span>**Advantages**<span class="ez-toc-section-end"></span>

**1. Improved security –** Average PHP vulnerability fixes per year are **30**, which are great opportunities for infiltrators to exploit your website if left unfixed.

**2. Improved performance –** Every PHP update gives a boost in performance. Some updates provide massive improvements than the others.

For example, PHP 7 operates at half the *latency* of PHP 5.6. That’s 50% improved performance and the number of *requests made/ second* is double that of PHP 5.6*.*

**3. Better support –** Older PHP versions cannot be supported by developers for a prolonged period and have a higher chance of being abandoned.

If a core functionality of your website runs on an older version of PHP, in addition to less security and slow performance, it is hard to find support if your site runs into an issue. It’s impossible to fix your site without any support.

You get support with newer PHP versions, and your site becomes compatible with a vast array of plugins.

## <span class="ez-toc-section" id="prerequisites"></span>**Prerequisites**<span class="ez-toc-section-end"></span>

**1. Update Plugins and Themes**

It’s a good practice to update your WordPress core, themes and plugins which helps to stay on top in terms of security and performance.

**Note:** If you’ve made any changes to your live theme’s code, create a *child theme* and replicate those changes. This will avoid loosing the data during the update.

**2. Backup your website**

Updating your PHP version could break your site if something goes wrong. As a safety measure, it’s better to backup your entire site. I recommend [Updraft Plus](https://wordpress.org/plugins/updraftplus/) for easy site backups.

**3. Check your current PHP version**

Knowing what version of PHP you’re running on will serve as a guide for updating it.

To find the current PHP version:

I. Log on to your *WordPress dashboard*

II. In the *Tools* tab, click *“Site health”.*

<div class="wp-block-image"><figure class="aligncenter">![Tools>Site health](https://lh4.googleusercontent.com/37ZV0G1XVJtDoZM-Xt7hK3rHpDTe2W3GJIPbaRRW4pytkJC12I0i9aHN52-A-nAM9tgL32ZiZLQfguOc5MPse3bHtdZYpc7KO_n9b7fy98QUlTgmK330nwXxutipEGoPq2Wln9b6)<figcaption>Click Site health</figcaption></figure></div>III. Click *Info*

<div class="wp-block-image"><figure class="aligncenter">![Info](https://lh6.googleusercontent.com/zPwIAVklQpFgSxcxi8NTgrhrasIA0VYdjcHUBWQblAQYsxifz8WdPcTv5LInfUnwvWCkss3nS57dfjcJ3h914E_iIAQQjM8xQGFE4tfGGkM1LINxP_bmqSgfYRftjTh3UJCoim7M)<figcaption> Click Info</figcaption></figure></div>IV. Click *Server*. You can find your *PHP version* here.

<div class="wp-block-image"><figure class="aligncenter">![Server>PHP version](https://lh5.googleusercontent.com/3hD76tlFBHUFFVYS8bBxC86heuQ55n2OL4vzlH7aHfo0pJsU5bEQxh2kr_khOLvW-UUikGNgT3qJf3CqGpZ5i3s-jiHnIELmiuHzVJwgFWZpImiybZl_cZWmp5SNfvtKMlapH2IV)<figcaption>Your website’s PHP version can be found here</figcaption></figure></div>**4. Check PHP compatibility**

You’re going to check if all your plugins and themes support the latest version of PHP using a plugin called PHP Compatibility checker.

1\. Download [PHP compatibility checker](https://wordpress.org/plugins/php-compatibility-checker/) and activate it.

<div class="wp-block-image"><figure class="aligncenter">![Install PHP Compatibility checker](https://lh4.googleusercontent.com/Awq9QNL13h57-cTCa2Vp7yV7Hv40hWVc9nLn9BL5JKEmDV4umx2FdcalPjpMSRaD_1Xicsnza6caKvE8MBPU_Ab56HkUgdWZgsdT2vY4qbDVRItcZUgEaBfzguFpOvTs__22bylV)<figcaption>Install the plugin</figcaption></figure></div>2\. In your installed plugin dashboard, find this plugin and click *“Start Scan”*.

<div class="wp-block-image"><figure class="aligncenter">![Click Start Scan from Plugin dashboard](https://lh5.googleusercontent.com/gGFuaWBknm4qvFoWBIXWj6Z3VH20WM64VFEx6ia361GO6_R6EjGmj4dOg5_pLGZL1d3_5OmE1MtMA0QcKY8eGRXFOC-DB0zy7Zttrt3DtTYpVLO9Iewqqd-chiQXi3Af4JtQpPn0)<figcaption>Click Start Scan</figcaption></figure></div>3\. Click on the latest PHP version. Choose a “*Plugin/ Theme Status”* depending on your requirements. Click *“Scan site”* to perform a scan.

<div class="wp-block-image"><figure class="aligncenter">![Choose your scan options](https://lh5.googleusercontent.com/M7kF4Vrh229ZaBMCIEV1AB52Jf3aPnwYV8ZaKNZf74sNytscykYRp6FlVCNN-GK-bEn-rF8JkvQTxav1i_xaTlxV6UiSGvU-CuMsXnRLBQKlSG-uoIH_IkcZcxGCZ17KKEk9Skj3)<figcaption>Select your desired options</figcaption></figure></div>The scan time may vary depending upon the number of plugins and themes you use.

4\. Once the scan is complete, each plugin is denoted with three possible results.

i. Compatible – The plugin fits with the desired PHP version

<div class="wp-block-image"><figure class="aligncenter">![Compatible result](https://lh3.googleusercontent.com/lJs7KQcyyEg7VNaiSEYZRy-riHlkifrX43OlNO24-STAjasKO6DRitYByYZSC26erb3WBQ8oZH1mxxfvGuLaS_0uk3167lZqWvOzPmF3LsDjWr4Jv7KE6CY_seL4e8Xgx5FfVZJ_)<figcaption>*Compatible Result*</figcaption></figure></div>ii. Error – The plugin is not compatible, and you’ve to start looking for an alternative plugin or contact the developer to find if the plugin will support your desired PHP version soon.

<div class="wp-block-image"><figure class="aligncenter">![Error result - Not compatible](https://lh5.googleusercontent.com/qTcZ5qai5Nua5YJVzqNAzCJfCsAWMQ15TF3VCvwfWpb7hgSBMbiJNfd4NOJ73VHD8LgC9FNbtmVrc_6k6cExDsJ1YZJL2kcl55Ib-XIiqDJUQJAwZpGy0_z-YImoS3Yia3sjRzs-)<figcaption>*Error Result*</figcaption></figure></div>iii. Unknown – This isn’t an error. As the size of the plugin was too large, it is skipped. Google or contact the developer to find if the plugin supports your desired PHP version. If not look for other plugins with similar functionalities and higher PHP support.

<div class="wp-block-image"><figure class="aligncenter">![Unknown result - Because of the huge plugin size](https://lh3.googleusercontent.com/MxJ9pq-pgvhDFjkU_pMSmWSJs_-po5UGfrjASFOWbsr48tgKZ6UyyOuN01OAUxkiSbgFKo7s_1apn0Bw8ayP1E7SFZa52Dq8qjpVmFcDbNNEMbyKRNmkSBBu7UBqoZB7ndS5z9g_)<figcaption>*Unknown Result*</figcaption></figure></div>Unless you’re clear that all your plugins and themes support the latest PHP version, **DO NOT** proceed further. Updating your PHP without following the above requirements will more likely break plugin functionality or the entire site.

## <span class="ez-toc-section" id="shared_hosting_%e2%80%93_using_cpanel_to_update_your_php"></span>Shared Hosting – Using CPanel to Update Your PHP <span class="ez-toc-section-end"></span>

Updating PHP varies amongst different hosting providers. Here’s a generalized procedure on how to update your PHP.

1\. Login to your CPanel dashboard.

2\. In the search bar type in “PHP”. Click on the result that matches with *“Select PHP version”.*

<div class="wp-block-image"><figure class="aligncenter">![Search for select PHP version](https://lh4.googleusercontent.com/u0jhf1hcQb4eDGUllqykz8gEjMIqepISDAoAX13gj9d6epzIabQcFmnoYO0MkmUGcilvi4_OxueL0nSG_dHJRGpIjlhnYSQaLaeigjS643lhwQXdYHUJ9eqsMZVX8u4DH69GCk0I)</figure></div>3\. Choose your desired PHP version under “*Current PHP version*” and click “Set as current”. Your PHP version is updated.

<div class="wp-block-image"><figure class="aligncenter">![Choose your desired PHP version](https://lh5.googleusercontent.com/w6WYUFVDKx4EjamLudwiCK-Vr7XaO4YIvf0rh7ARdfEFrmNqMpet2LluoLF5SddtLS9BSukIu2Z9B8Zxjm1IgoXe_kDoQA13oxlArzGAM70-ycc0s9R6hyvSOOHPvAsiAnoD8phj)<figcaption>*Choose PHP version and click “Set as current”*</figcaption></figure></div>4\. Now, php is updated to latest version. To ensure there are no errors, Navigate through your website to spot errors and missing functionalities. In most cases, there would be none. If such an error exists, find the plugin that causes it and replace it with one that offers a higher PHP support.

## <span class="ez-toc-section" id="dedicated_hosting_%e2%80%93_using_web_host_manager"></span>Dedicated Hosting – Using Web Host Manager<span class="ez-toc-section-end"></span>

1\. Log in to your WHM(Web Host Manager) dashboard as the **root** user.

2\. In the search bar type in *“easy”* and click on the *“easy-apache”*.

<div class="wp-block-image"><figure class="aligncenter">![Find Easy Apache](https://lh4.googleusercontent.com/Ex8ZwGfKwMEGcNpLsZgrHQ8INudHI34rlneDc2k8-Pt5F2w-00nB2DM1aFEt6YdCOvJ0iXzALPAfhhz78tSh-uo184CBeSJ_DwyVvIW9buRF4U_4comXVDIVcx66NqxxaxwiBheM)<figcaption>*Click EasyApache*</figcaption></figure></div>3\. Click the *“customize”*.

<div class="wp-block-image"><figure class="aligncenter">![find customize option](https://lh4.googleusercontent.com/OPvWSN3WJNRiFxCh__xNMi1piaearxrlloAwSVo-1U8qqXxpCijPZSEOyNbUdfRtT4us_pm57B2Fk_4TT5Cq_4ZNSqKET1QWL4LBGvbubp_G1kvAbh5PYI3OVUJ7AIsDGdonNgR4)<figcaption>*Click Customize*</figcaption></figure></div>4\. Click on *“PHP versions”*.

<div class="wp-block-image"><figure class="aligncenter">![find PHP versions](https://lh3.googleusercontent.com/VeSN4M8F-qxqTREV5xp4Kff7VbGVwSSHNVwbjc9D5fBQqjE_j3MRrYOSQVM7dXFDPsWckWI-oGcI7WzwqjUFsNEj0F_ymS8w1KfYFuUpphxIttsdTO7QenXTOz0e8VEsuFmR4TiN)</figure></div>5\. Click the slider to install your desired PHP version. In this case, it’s PHP 7.2.

<div class="wp-block-image"><figure class="aligncenter">![update php on wordpress](https://lh3.googleusercontent.com/8hMBaBDASfiHVq0iO-1Tb0xZFRWBguej4VG-ejzPADZ9bfuEER2sZZczwOugsGihNoA368IFuMfFzL4s0x7yBvv7mi5yAtwBEljmtR-ON7DDqf9i5eXAtq1eUr4nrzN5ZXUGJO9n)<figcaption>*Install slider*</figcaption></figure></div>6\. Finally click *review* (from the left sidebar) to update. The process may take a few minutes to complete. You’ll now be displayed with a list of changes you’re about to make. Click the *Provision* button to proceed. Wait for a few minutes.

<div class="wp-block-image"><figure class="aligncenter">![Finally hit Provision to finish](https://lh5.googleusercontent.com/waoUC1_tK5UtNyoMZvlB31AexGylGreJWBYIKnUXgSz5OcxERBnNHfUyj8WeTzYIrbnvlizbm1iKzqb3dINg2iBOuClSXThKyT8BM2yVDxml_OoposKB1GGNYGrJTDccN846ixs1)</figure></div>7\. A message stating *Provision* process is complete is displayed. This marks the end of the PHP update. Click *Done* to finish the process.

## <span class="ez-toc-section" id="getting_help_from_your_hosting_provider"></span>**Getting Help From Your Hosting Provider**<span class="ez-toc-section-end"></span>

If the above guide doesn’t support your hosting provider, you can find [hosting specific tutorials on how to update your PHP in WordPress](https://github.com/WordPress/servehappy-resources/blob/master/tutorials/hosting-specific/tutorials-en.md).

Alternatively, you can send an email with [this context](https://wordpress.org/support/update-php/#how-to-update-your-websites-php-version-for-a-faster-more-secure-website) to your hosting provider to update php on WordPress.

## <span class="ez-toc-section" id="conclusion"></span>**Conclusion**<span class="ez-toc-section-end"></span>

To summarize, you’ve updated your PHP version in WordPress.

You’ve also improved your WordPress speed and security by updating the PHP version of your website.

Feel free to comment if you’ve any questions.

## <span class="ez-toc-section" id="faq"></span>**FAQ**<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1602754796123">### 1. How to update PHP on WordPress Bluehost?

<div class="rank-math-answer ">To update your PHP in BlueHost, read this [Bluehost specific tutorial. Check out this page to find domain-specific instructions for updating your PHP in WordPress.](https://www.bluehost.com/help/article/php-version-selection)

</div></div><div class="rank-math-list-item" id="faq-question-1602754844556">### 2. How to downgrade the PHP version in WordPress?

<div class="rank-math-answer ">Repeat the process of updating your PHP, but choose a lower PHP version instead of choosing the higher one that your WordPress site supports. It is **not recommended** unless it’s necessary.

</div></div><div class="rank-math-list-item" id="faq-question-1602754903372">### 3. Some of my plugins don’t support the latest PHP version. Should I replace them before updating or vice versa?

<div class="rank-math-answer ">I recommend replacing them with plugins that support higher PHP versions, or you can contact the developer to check if they could offer support for the latest PHP version soon. **DO NOT** update your PHP until all your plugins are compatible.

</div></div><div class="rank-math-list-item" id="faq-question-1602754929865">### 4. What is the latest version of PHP for WordPress?

<div class="rank-math-answer ">Though PHP 7.2 and 7.3 are supported, WordPress.org recommends PHP 7.4 which is the latest version of PHP for WordPress.

</div></div><div class="rank-math-list-item" id="faq-question-1602754957055">### 5. How long does it take to update PHP on WordPress?

<div class="rank-math-answer ">Updating your PHP in WordPress takes less than 5 minutes and you won’t experience any downtime.

</div></div><div class="rank-math-list-item" id="faq-question-1602850005812">### 6. How can I check my PHP version? 

<div class="rank-math-answer ">You can check your PHP WordPress in WordPress -&gt; Tools -&gt; Site Health -&gt; Info -&gt; Server. You’ll see the version of the PHP which your site is using.

</div></div><div class="rank-math-list-item" id="faq-question-1602850314323">### 7. Should I update PHP?

<div class="rank-math-answer ">Yes, Its recommended to update PHP to latest version always to avoid any security and stability issues.

</div></div></div></div>