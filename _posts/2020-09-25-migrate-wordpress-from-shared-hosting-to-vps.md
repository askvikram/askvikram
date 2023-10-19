---
id: 2585
title: 'How to Migrate WordPress From Shared Hosting to VPS With Zero Downtime'
date: '2020-09-25T07:58:45+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://139.180.139.123/?p=2585'
permalink: /migrate-wordpress-from-shared-hosting-to-vps/
rank_math_seo_score:
    - '65'
rank_math_internal_links_processed:
    - '1'
tcb2_ready:
    - '1'
rank_math_primary_category:
    - '16'
rank_math_rich_snippet:
    - article
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
tve_content_before_more:
    - "<div class=\"thrv_wrapper tve_wp_shortcode\"><div class=\"tve_shortcode_raw\" style=\"display: none\">___TVE_SHORTCODE_RAW__&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"intro\"&gt;Introduction&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"1b4336cd-3e35-46b1-a0ac-76870caeac25\"&gt;Many bloggers start blogging with the shared hosting in the notion to pay less and get more support.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2de736e7-b86f-49c8-b744-d1043b982594\"&gt;Shared hosting is a hosting where you share the hosting space with other webmasters. This may cause problems in your websites as well, when there are problems in other sites. For eg. if there is a Malware Attack in others site, then you are also vulnerable to the attack.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"f1f58e8b-c407-4ff7-9e81-ae9862de794e\"&gt;Moving to the Virtual private cloud servers will give a server which hosts your websites alone.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d515236e-803b-4233-8c41-0ca0fb64e632\"&gt;In this tutorial, you'll learn about the steps to migrate your WordPress website from shared hosting like Godaddy to DigitalOcean or any other cloud provider.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"pre\"&gt;Prerequisites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ad20b2ca-7876-4ea0-9f1a-4732328758f7\"&gt;Create an account with Digital Ocean and create one droplet to host your wordpress site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"b2ab553b-3e4b-40a4-9150-156e0d547a9d\"&gt;Step 1 - Creating backup of Existing WordPress Sites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d214f7fd-ea6c-4022-a241-3ae38b804ab7\"&gt;In this step, you'll create a backup of your existing wordpress site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"4e209f50-4c4e-4ad8-a7db-84fc2c105c06\"&gt;This backup file can be used to import into your new server and it might also help you restore your site when there is any problem during migration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ee191360-d355-4c06-9a98-05a6992a106c\"&gt;To create a backup of your wordpress site, you need to install a plugin called All in one WP Migration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"165fc5de-3d85-4913-af5e-39ecf1c5b932\"&gt;When you install and activate this plugin, you'll be able to see the option All-in-One WP migration option in the WordPress Menu.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"92a0628e-1ffe-45b1-afe8-133f4e49d77d\"&gt;Click on that menu, and select Export option.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d74125aa-36f7-493e-9d0f-4954740a8da7\"&gt;Now, you'll see the of options where you can export the file. Select file option and export the file to your local location.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"f15df43c-a03a-4c9b-a31d-43b6ec1c9cad\"&gt;Your backup is created. Now let's move to the next step.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"1f08bf7e-fc87-4640-aa2b-ec903b5417c3\"&gt;Step 2 - Installing Wordops in New Server&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"be724bc9-1079-46aa-bc35-ce51fe562cb0\"&gt;In this step, you'll install Wordops in your new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"24e16cc6-fecb-43e9-b494-ab55841bd537\"&gt;Wordops is a tool which eases the WordPress site Installation and server administration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2671d1bd-0897-4374-a323-28f44d9ea79e\"&gt;When using this, it automatically takes care of installing the necessary software stack(Wordpress, MySQL, PhP, NGINX) installation for running wordpress sites in the server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"0093a517-bb36-4472-8562-379133889307\"&gt;You can install the WordOps using the command below.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wget -qO wo wops.cc &amp;amp;&amp;amp; sudo bash wo&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"dd5293ea-b6e9-4213-92c6-7630db69fcc2\"&gt;WordOps and the full stack required for installing WordPress is installed.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d2c7dcd4-fbf1-4215-8a69-7e5ff7519b91\"&gt;Now let's create sites on WordPress.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"1924cbe5-bd76-4813-b9b6-df1e4bfb1f10\"&gt;Step 3 - Creating Sites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"6aba3bf5-90e6-491a-a436-4d073c914b00\"&gt;In this step, you'll install the wordpress for each site that you want to configure in the new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"cee3877a-6a16-49b2-b802-9e61aea597d0\"&gt;For each site, you need to follow the below step once.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"b89845ea-42a4-458e-92a0-0955e6ab2391\"&gt;Run the below command to create wordpress site your domain.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a841ad8f-f171-4d64-b0ed-4e3d16fae705\"&gt;By default, we are creating wordpress site with Nginx fast cache.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"1ca8e916-cfab-498f-ac70-a7ffdc3f7701\"&gt;If you would like to use any other type of cache in the wordpress installation, refer the link in the &lt;a href=\"https://docs.wordops.net/commands/site/#wordpress\"&gt;Wordops official page&lt;/a&gt;.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wo site create site.tld --wpfc&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"7d2d0798-8101-42a5-9b3f-42fde98d5b6b\"&gt;&lt;em&gt;site.tld&lt;/em&gt; should be replaced with your domain name. For e.g. &lt;a href=\"https://139.180.139.123\"&gt;askvikram.com&lt;/a&gt; where askvikram is site and tld is .com extension.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"00135ae4-f60e-48c3-a780-b916ecdaab07\"&gt;The fresh wordpress site is created with the basic settings.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"03e21d2f-e529-4939-9aac-d4ec1c84585d\"&gt;Now let's move on to next step to migrate the contents from the backup to this new server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"4a93fecd-95ba-46c8-9019-59c244ab9f7f\"&gt;Step 4 - Importing the Backup to New Server&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"c54b2b25-d001-4dfa-ab0f-da59d5e1eac3\"&gt;To migrate the content from the backup to the newly installed wordpress installation, login to the newly installed wordpress installation using the IP address of your server and wp-admin.php url.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a618ad90-486d-4d79-91be-b4e914c026c6\"&gt;You'll see the default wordpress dashboard.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a16514b7-6d45-4264-ab86-716f50e1effe\"&gt;Go to Add new plugins page, Install the same All-In-WP-Migration plugin which can be used to import.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"3ef95eb4-9ae9-47c4-8474-dbfbcb7c5721\"&gt;When you install and activate this plugin, you'll be able to see the option All-in-One WP migration option in the WordPress Menu.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"949e7b12-7b9c-4b15-9a07-832684caf77a\"&gt;Click on that menu, and select Import option.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"65c0a307-5c02-4e9c-b5c2-f9db1f171c79\"&gt;Now, you'll see the of option to import the file.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"09a60e89-0606-432e-ab21-46623bed19db\"&gt;Select file option and import the file. Click Finish.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"cb55a30c-2522-4d00-80a1-13304566559e\"&gt;This operation will completely import the content of your site from the shared hosting including your usernames and passwords.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d9145cd8-46c7-4f7a-a489-3db30ef69c13\"&gt;You will also need to update the desired URL Type in the option that is shown.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ea363a8f-26a2-4d6a-a1ec-5948941e2e59\"&gt;Wordpress import is complete and now your site is available in the new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2b596c58-c2e0-4915-9848-0a7003e2f68a\"&gt;Now lets see how to encrypt it using the lets encrypt ssl certificates.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"19b00fd7-7abc-4fb8-aafd-fd3de5b001c4\"&gt;Step 5 - Updating the SSL for New Site&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"0cf5bc6c-0e2b-4853-aa0e-9323111e5851\"&gt;Use the below command to fetch the ssl certificate for your server from the site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wo site create site.tld --wp --letsencrypt&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"b8f41cae-aab4-477b-a0ad-c54d0dd6ae70\"&gt;This will update the lets encrypt certificate for your website.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"382cb02a-37ff-44bf-b141-7460a82b1353\"&gt;Step 6 - Updating DNS settings in DigitalOcean&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"e2008cc5-95b6-4f46-b309-ae536869567c\"&gt;Go to the digital ocean server and click Networks → domains.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"c2508393-7910-48ca-91ce-9bf7cfbdc43f\"&gt;Add a record for your root domain and update the IP address of the digitial ocean droplet.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"bf1084b5-0424-440d-b09f-481b17bb8b59\"&gt;Step 7 - Updating Nameservers in Domain Registrar&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"e39222ba-747c-4fe9-8d91-636a2416f5b8\"&gt;Finally, update the name servers in the domain registrar.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"73e4bb02-1eee-4309-b2b9-eb7a06e13b82\"&gt;Update the name servers as &lt;a href=\"http://ns1.digitalocean.com\"&gt;ns1.digitalocean.com&lt;/a&gt;. So this is the server which will be looked upon by the browsers to check the content of the websites.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"357b29a4-f31d-44d0-af84-30907ed3988d\"&gt;Conclusion&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"afc5a4e1-e0a6-420f-83f7-f78bfed72049\"&gt;In this article, you have migrated to the VPS hosting from the shared hosting.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2cd15dc3-cebc-400a-9c1b-cb4fb754edb9\"&gt;You've saved a lot of money and come out of the shared hosting where you were vulnerable to the issues of other webmasters.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n__TVE_SHORTCODE_RAW___</div></div><div class=\"thrv_wrapper thrv_tw_qs tve_clearfix\" data-url=\"https://twitter.com/intent/tweet\" data-via=\"\" data-use_custom_url=\"\" style=\"\" data-css=\"tve-u-174c507791f\">\n\t<div class=\"thrv_tw_qs_container\" style=\"\">\n\t\t<div class=\"thrv_tw_quote\">\n\t\t\t<p class=\"\" style=\"\">Try cloudways for Free</p>\n\t\t</div>\n\t\t<div class=\"thrv_tw_qs_button tve_p_right\">\n\t\t\t<span>\n\t\t\t\t<i></i>\n\t\t\t\t<span class=\"thrv_tw_qs_button_text\">Click to Tweet</span>\n\t\t\t</span>\n\t\t</div>\n\t</div>\n</div><div class=\"thrv_wrapper thrv-page-section tve-height-update\">\n\t<div class=\"tve-page-section-out\"></div>\n\t<div class=\"tve-page-section-in tve_empty_dropzone\" data-css=\"tve-u-174c503ea46\"></div>\n</div><div class=\"thrv_wrapper tve_wp_shortcode tcb-elem-placeholder\">\n\t<span class=\"tcb-inline-placeholder-action with-icon\">\n\t\t<svg class=\"tcb-icon tcb-icon-wordpress\"><use xlink:href=\"#tcb-icon-wordpress\"></use></svg>\t\tInsert WordPress Content\t</span>\n</div><div class=\"thrv_wrapper tcb-elem-placeholder tcb-ct-placeholder\" data-ct=\"stylebox-0\" data-tcb-elem-type=\"stylebox\" data-element-name=\"Styled Box\">\n\t<span class=\"tcb-inline-placeholder-action with-icon\"><svg class=\"tcb-icon tcb-icon-styled_box\"><use xlink:href=\"#tcb-icon-styled_box\"></use></svg>\t\tInsert Styled Box\t</span>\n</div>"
tve_content_more_found:
    - ''
tve_custom_css:
    - '@media (min-width: 300px){:not(#tve) [data-css="tve-u-174c507791f"] p, :not(#tve) [data-css="tve-u-174c507791f"] li, :not(#tve) [data-css="tve-u-174c507791f"] blockquote, :not(#tve) [data-css="tve-u-174c507791f"] address, :not(#tve) [data-css="tve-u-174c507791f"] .tcb-plain-text, :not(#tve) [data-css="tve-u-174c507791f"] label { font-size: var(--tve-font-size, 44px); }[data-css="tve-u-174c507791f"] { --tve-font-size:44px; --tve-color:rgb(0, 0, 0); --tve-applied---tve-color:rgb(0, 0, 0); }:not(#tve) [data-css="tve-u-174c507791f"] p, :not(#tve) [data-css="tve-u-174c507791f"] li, :not(#tve) [data-css="tve-u-174c507791f"] blockquote, :not(#tve) [data-css="tve-u-174c507791f"] address, :not(#tve) [data-css="tve-u-174c507791f"] .tcb-plain-text, :not(#tve) [data-css="tve-u-174c507791f"] label, :not(#tve) [data-css="tve-u-174c507791f"] h1, :not(#tve) [data-css="tve-u-174c507791f"] h2, :not(#tve) [data-css="tve-u-174c507791f"] h3, :not(#tve) [data-css="tve-u-174c507791f"] h4, :not(#tve) [data-css="tve-u-174c507791f"] h5, :not(#tve) [data-css="tve-u-174c507791f"] h6 { color: var(--tve-color, rgb(0, 0, 0)) !important; --tve-applied-color:var$(--tve-color, rgb(0, 0, 0)) !important; --tcb-applied-color:rgb(0, 0, 0); }[data-css="tve-u-174c507791f"] .thrv_tw_qs_container { background-color: rgb(201, 203, 212) !important; --tve-applied-background-color:rgb(201, 203, 212) !important; }}'
tve_user_custom_css:
    - ''
tve_page_events:
    - 'a:0:{}'
tve_updated_post:
    - "<div class=\"thrv_wrapper tve_wp_shortcode\"><div class=\"tve_shortcode_raw\" style=\"display: none\">___TVE_SHORTCODE_RAW__&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"intro\"&gt;Introduction&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"1b4336cd-3e35-46b1-a0ac-76870caeac25\"&gt;Many bloggers start blogging with the shared hosting in the notion to pay less and get more support.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2de736e7-b86f-49c8-b744-d1043b982594\"&gt;Shared hosting is a hosting where you share the hosting space with other webmasters. This may cause problems in your websites as well, when there are problems in other sites. For eg. if there is a Malware Attack in others site, then you are also vulnerable to the attack.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"f1f58e8b-c407-4ff7-9e81-ae9862de794e\"&gt;Moving to the Virtual private cloud servers will give a server which hosts your websites alone.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d515236e-803b-4233-8c41-0ca0fb64e632\"&gt;In this tutorial, you'll learn about the steps to migrate your WordPress website from shared hosting like Godaddy to DigitalOcean or any other cloud provider.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"pre\"&gt;Prerequisites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ad20b2ca-7876-4ea0-9f1a-4732328758f7\"&gt;Create an account with Digital Ocean and create one droplet to host your wordpress site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"b2ab553b-3e4b-40a4-9150-156e0d547a9d\"&gt;Step 1 - Creating backup of Existing WordPress Sites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d214f7fd-ea6c-4022-a241-3ae38b804ab7\"&gt;In this step, you'll create a backup of your existing wordpress site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"4e209f50-4c4e-4ad8-a7db-84fc2c105c06\"&gt;This backup file can be used to import into your new server and it might also help you restore your site when there is any problem during migration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ee191360-d355-4c06-9a98-05a6992a106c\"&gt;To create a backup of your wordpress site, you need to install a plugin called All in one WP Migration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"165fc5de-3d85-4913-af5e-39ecf1c5b932\"&gt;When you install and activate this plugin, you'll be able to see the option All-in-One WP migration option in the WordPress Menu.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"92a0628e-1ffe-45b1-afe8-133f4e49d77d\"&gt;Click on that menu, and select Export option.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d74125aa-36f7-493e-9d0f-4954740a8da7\"&gt;Now, you'll see the of options where you can export the file. Select file option and export the file to your local location.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"f15df43c-a03a-4c9b-a31d-43b6ec1c9cad\"&gt;Your backup is created. Now let's move to the next step.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"1f08bf7e-fc87-4640-aa2b-ec903b5417c3\"&gt;Step 2 - Installing Wordops in New Server&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"be724bc9-1079-46aa-bc35-ce51fe562cb0\"&gt;In this step, you'll install Wordops in your new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"24e16cc6-fecb-43e9-b494-ab55841bd537\"&gt;Wordops is a tool which eases the WordPress site Installation and server administration.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2671d1bd-0897-4374-a323-28f44d9ea79e\"&gt;When using this, it automatically takes care of installing the necessary software stack(Wordpress, MySQL, PhP, NGINX) installation for running wordpress sites in the server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"0093a517-bb36-4472-8562-379133889307\"&gt;You can install the WordOps using the command below.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wget -qO wo wops.cc &amp;amp;&amp;amp; sudo bash wo&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"dd5293ea-b6e9-4213-92c6-7630db69fcc2\"&gt;WordOps and the full stack required for installing WordPress is installed.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d2c7dcd4-fbf1-4215-8a69-7e5ff7519b91\"&gt;Now let's create sites on WordPress.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"1924cbe5-bd76-4813-b9b6-df1e4bfb1f10\"&gt;Step 3 - Creating Sites&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"6aba3bf5-90e6-491a-a436-4d073c914b00\"&gt;In this step, you'll install the wordpress for each site that you want to configure in the new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"cee3877a-6a16-49b2-b802-9e61aea597d0\"&gt;For each site, you need to follow the below step once.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"b89845ea-42a4-458e-92a0-0955e6ab2391\"&gt;Run the below command to create wordpress site your domain.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a841ad8f-f171-4d64-b0ed-4e3d16fae705\"&gt;By default, we are creating wordpress site with Nginx fast cache.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"1ca8e916-cfab-498f-ac70-a7ffdc3f7701\"&gt;If you would like to use any other type of cache in the wordpress installation, refer the link in the &lt;a href=\"https://docs.wordops.net/commands/site/#wordpress\"&gt;Wordops official page&lt;/a&gt;.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wo site create site.tld --wpfc&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"7d2d0798-8101-42a5-9b3f-42fde98d5b6b\"&gt;&lt;em&gt;site.tld&lt;/em&gt; should be replaced with your domain name. For e.g. &lt;a href=\"https://139.180.139.123\"&gt;askvikram.com&lt;/a&gt; where askvikram is site and tld is .com extension.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"00135ae4-f60e-48c3-a780-b916ecdaab07\"&gt;The fresh wordpress site is created with the basic settings.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"03e21d2f-e529-4939-9aac-d4ec1c84585d\"&gt;Now let's move on to next step to migrate the contents from the backup to this new server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"4a93fecd-95ba-46c8-9019-59c244ab9f7f\"&gt;Step 4 - Importing the Backup to New Server&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"c54b2b25-d001-4dfa-ab0f-da59d5e1eac3\"&gt;To migrate the content from the backup to the newly installed wordpress installation, login to the newly installed wordpress installation using the IP address of your server and wp-admin.php url.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a618ad90-486d-4d79-91be-b4e914c026c6\"&gt;You'll see the default wordpress dashboard.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"a16514b7-6d45-4264-ab86-716f50e1effe\"&gt;Go to Add new plugins page, Install the same All-In-WP-Migration plugin which can be used to import.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"3ef95eb4-9ae9-47c4-8474-dbfbcb7c5721\"&gt;When you install and activate this plugin, you'll be able to see the option All-in-One WP migration option in the WordPress Menu.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"949e7b12-7b9c-4b15-9a07-832684caf77a\"&gt;Click on that menu, and select Import option.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"65c0a307-5c02-4e9c-b5c2-f9db1f171c79\"&gt;Now, you'll see the of option to import the file.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"09a60e89-0606-432e-ab21-46623bed19db\"&gt;Select file option and import the file. Click Finish.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"cb55a30c-2522-4d00-80a1-13304566559e\"&gt;This operation will completely import the content of your site from the shared hosting including your usernames and passwords.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"d9145cd8-46c7-4f7a-a489-3db30ef69c13\"&gt;You will also need to update the desired URL Type in the option that is shown.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"ea363a8f-26a2-4d6a-a1ec-5948941e2e59\"&gt;Wordpress import is complete and now your site is available in the new VPS server.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2b596c58-c2e0-4915-9848-0a7003e2f68a\"&gt;Now lets see how to encrypt it using the lets encrypt ssl certificates.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"19b00fd7-7abc-4fb8-aafd-fd3de5b001c4\"&gt;Step 5 - Updating the SSL for New Site&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"0cf5bc6c-0e2b-4853-aa0e-9323111e5851\"&gt;Use the below command to fetch the ssl certificate for your server from the site.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:codemirror-blocks/code-block {\"mode\":\"shell\",\"mime\":\"application/x-sh\"} --&gt;&lt;/p&gt;\n&lt;div class=\"wp-block-codemirror-blocks-code-block code-block\"&gt;\n&lt;pre&gt;wo site create site.tld --wp --letsencrypt&lt;/pre&gt;\n&lt;/div&gt;\n&lt;p&gt;&lt;!-- /wp:codemirror-blocks/code-block --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"b8f41cae-aab4-477b-a0ad-c54d0dd6ae70\"&gt;This will update the lets encrypt certificate for your website.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"382cb02a-37ff-44bf-b141-7460a82b1353\"&gt;Step 6 - Updating DNS settings in DigitalOcean&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"e2008cc5-95b6-4f46-b309-ae536869567c\"&gt;Go to the digital ocean server and click Networks → domains.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"c2508393-7910-48ca-91ce-9bf7cfbdc43f\"&gt;Add a record for your root domain and update the IP address of the digitial ocean droplet.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"bf1084b5-0424-440d-b09f-481b17bb8b59\"&gt;Step 7 - Updating Nameservers in Domain Registrar&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"e39222ba-747c-4fe9-8d91-636a2416f5b8\"&gt;Finally, update the name servers in the domain registrar.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"73e4bb02-1eee-4309-b2b9-eb7a06e13b82\"&gt;Update the name servers as &lt;a href=\"http://ns1.digitalocean.com\"&gt;ns1.digitalocean.com&lt;/a&gt;. So this is the server which will be looked upon by the browsers to check the content of the websites.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:heading --&gt;&lt;/p&gt;\n&lt;h2 id=\"357b29a4-f31d-44d0-af84-30907ed3988d\"&gt;Conclusion&lt;/h2&gt;\n&lt;p&gt;&lt;!-- /wp:heading --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"afc5a4e1-e0a6-420f-83f7-f78bfed72049\"&gt;In this article, you have migrated to the VPS hosting from the shared hosting.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n&lt;p&gt;&lt;!-- wp:paragraph --&gt;&lt;/p&gt;\n&lt;p id=\"2cd15dc3-cebc-400a-9c1b-cb4fb754edb9\"&gt;You've saved a lot of money and come out of the shared hosting where you were vulnerable to the issues of other webmasters.&lt;/p&gt;\n&lt;p&gt;&lt;!-- /wp:paragraph --&gt;&lt;/p&gt;\n__TVE_SHORTCODE_RAW___</div></div><div class=\"thrv_wrapper thrv_tw_qs tve_clearfix\" data-url=\"https://twitter.com/intent/tweet\" data-via=\"\" data-use_custom_url=\"\" style=\"\" data-css=\"tve-u-174c507791f\">\n\t<div class=\"thrv_tw_qs_container\" style=\"\">\n\t\t<div class=\"thrv_tw_quote\">\n\t\t\t<p class=\"\" style=\"\">Try cloudways for Free</p>\n\t\t</div>\n\t\t<div class=\"thrv_tw_qs_button tve_p_right\">\n\t\t\t<span>\n\t\t\t\t<i></i>\n\t\t\t\t<span class=\"thrv_tw_qs_button_text\">Click to Tweet</span>\n\t\t\t</span>\n\t\t</div>\n\t</div>\n</div><div class=\"thrv_wrapper thrv-page-section tve-height-update\">\n\t<div class=\"tve-page-section-out\"></div>\n\t<div class=\"tve-page-section-in tve_empty_dropzone\" data-css=\"tve-u-174c503ea46\"></div>\n</div><div class=\"thrv_wrapper tve_wp_shortcode tcb-elem-placeholder\">\n\t<span class=\"tcb-inline-placeholder-action with-icon\">\n\t\t<svg class=\"tcb-icon tcb-icon-wordpress\"><use xlink:href=\"#tcb-icon-wordpress\"></use></svg>\t\tInsert WordPress Content\t</span>\n</div><div class=\"thrv_wrapper tcb-elem-placeholder tcb-ct-placeholder\" data-ct=\"stylebox-0\" data-tcb-elem-type=\"stylebox\" data-element-name=\"Styled Box\">\n\t<span class=\"tcb-inline-placeholder-action with-icon\"><svg class=\"tcb-icon tcb-icon-styled_box\"><use xlink:href=\"#tcb-icon-styled_box\"></use></svg>\t\tInsert Styled Box\t</span>\n</div>"
tve_globals:
    - 'a:2:{s:1:"e";s:1:"1";s:8:"font_cls";a:0:{}}'
thrive_tcb_post_fonts:
    - 'a:0:{}'
thrive_icon_pack:
    - '0'
tve_has_masonry:
    - '0'
tve_has_typefocus:
    - '0'
tve_has_wistia_popover:
    - '0'
rank_math_schema_BlogPosting:
    - 'a:8:{s:8:"metadata";a:3:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";}s:5:"image";a:2:{s:5:"@type";s:11:"ImageObject";s:3:"url";s:16:"%post_thumbnail%";}s:8:"headline";s:11:"%seo_title%";s:11:"description";s:17:"%seo_description%";s:5:"@type";s:11:"BlogPosting";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:15:"Vikram Aruchamy";}s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";}'
tcb_editor_disabled:
    - '1'
rank_math_focus_keyword:
    - 'migrate wordpress from shared hosting to vps'
rank_math_description:
    - 'In this tutorial, you''ll migrate wordpress from shared hosting to VPS server like Digital Ocean or Vultr without Zero Downtime. '
socialsnap_share_count_timestamp:
    - '2023-09-08 09:26:05'
ss_total_share_count:
    - '0'
ss_ss_click_share_count_linkedin:
    - '1'
ss_ss_click_share_count_twitter:
    - '1'
ss_social_share_disable:
    - ''
rank_math_analytic_object_id:
    - '35'
categories:
    - how-to
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

Shared hosting is a hosting which allows multiple users to share the same servers to host their websites. This makes your website prone to attack, when there is an attack on the other users websites. For e.g. if there is a malware attack in others site, then probably your site will also be targeted next.

Moving to the Virtual private cloud servers will give a server which hosts your websites alone. It gives the space which is exclusively for hosting your websites. This has lot of advantages including the security of your website.

In this tutorial, you’ll migrate WordPress to DigitalOcean cloud hosting or any other private cloud hosting provider.

If you find it difficult to migrate to Digitalocean cloud by yourself, try DigitalOcean with Cloudways for Free.

<div class="is-layout-flex wp-block-buttons aligncenter"><div class="wp-block-button is-style-fill">[**Try DigitalOcean with CloudWays for Free**](https://www.cloudways.com/en/?id=599120)</div></div>## <span class="ez-toc-section" id="prerequisites"></span>Prerequisites<span class="ez-toc-section-end"></span>

Create an account with Digital Ocean and create one droplet to host your wordpress site.

## <span class="ez-toc-section" id="step_1_%e2%80%93_creating_backup_of_existing_wordpress_sites"></span>Step 1 – Creating Backup of Existing WordPress Sites<span class="ez-toc-section-end"></span>

In this step, you’ll create a backup of your existing wordpress site.

This backup file can be used to import into your new server and it might also help you restore your site when there is any problem during migration.

To create a backup of your wordpress site, you need to install a plugin called All in one WP Migration.

When you install and activate this plugin, you’ll be able to see the option All-in-One WP migration option in the WordPress Menu.

Click on that menu, and select Export option.

Now, you’ll see the of options where you can export the file. Select file option and export the file to your local location.

Your backup is created. Now let’s move to the next step.

## <span class="ez-toc-section" id="step_2_%e2%80%93_installing_wordops_in_new_server"></span>Step 2 – Installing Wordops in New Server<span class="ez-toc-section-end"></span>

In this step, you’ll install Wordops in your new VPS server.

Wordops is a tool which eases the WordPress site Installation and server administration.

When using this, it automatically takes care of installing the necessary software stack(WordPress, MySQL, PhP, NGINX) installation for running wordpress sites in the server.

You can install the WordOps using the command below.

```
<pre class="wp-block-code"> ```
wget -qO wo wops.cc && sudo bash wo <span style="background-color: rgba(242,201,76,.35)"> site.tld </span>  --wpfc 
``` 
```

<mark>WordOps </mark>and the full stack required for installing WordPress is installed.

Now let’s create sites on WordPress.

## <span class="ez-toc-section" id="step_3_%e2%80%93_creating_sites"></span>Step 3 – Creating Sites<span class="ez-toc-section-end"></span>

In this step, you’ll install the wordpress for each site that you want to configure in the new VPS server.

For each site, you need to follow the below step once.

Run the below command to create wordpress site your domain.

By default, we are creating wordpress site with Nginx fast cache.

If you would like to use any other type of cache in the wordpress installation, refer the link in the [Wordops official page](https://docs.wordops.net/commands/site/#wordpress).

```
<pre class="wp-block-code"> ```
 wo site create <span style="background-color: rgba(242,201,76,.35)"> site.tld </span>  --wpfc 
``` 
```

*<mark>site.tld</mark>* should be replaced with your domain name. For e.g. [askvikram.com](https://139.180.139.123) where askvikram is site and tld is .com extension.

The fresh wordpress site is created with the basic settings.

Now let’s move on to next step to migrate the contents from the backup to this new server.

## <span class="ez-toc-section" id="step_4_%e2%80%93_importing_the_backup_to_new_server"></span>Step 4 – Importing the Backup to New Server<span class="ez-toc-section-end"></span>

To migrate the content from the backup to the newly installed wordpress installation, login to the newly installed wordpress installation using the IP address of your server and wp-admin.php url.

You’ll see the default wordpress dashboard.

Go to Add new plugins page, Install the same All-In-WP-Migration plugin which can be used to import.

When you install and activate this plugin, you’ll be able to see the option All-in-One WP migration option in the WordPress Menu.

Click on that menu, and select Import option.

Now, you’ll see the of option to import the file.

Select file option and import the file. Click Finish.

This operation will completely import the content of your site from the shared hosting including your usernames and passwords.

You will also need to update the desired URL Type in the option that is shown.

WordPress import is complete and now your site is available in the new VPS server.

Now lets see how to encrypt it using the lets encrypt ssl certificates.

## <span class="ez-toc-section" id="step_5_%e2%80%93_updating_the_ssl_for_new_site"></span>Step 5 – Updating the SSL for New Site<span class="ez-toc-section-end"></span>

Use the below command to fetch the ssl certificate for your server from the site.

```
<pre class="wp-block-code">wo site create site.tld --wp --letsencrypt
```

```
<pre class="wp-block-code">```
 wo site create <span style="background-color: rgba(242,201,76,.35)"> site.tld </span>  --wp --letsencrypt 
``` 
```

This will update the lets encrypt certificate for your website.

## <span class="ez-toc-section" id="step_6_%e2%80%93_updating_dns_settings_in_digitalocean"></span>Step 6 – Updating DNS Settings in DigitalOcean<span class="ez-toc-section-end"></span>

Go to the digital ocean server and click Networks → domains.

Add a record for your root domain and update the IP address of the digitial ocean droplet.

## <span class="ez-toc-section" id="step_7_%e2%80%93_updating_nameservers_in_domain_registrar"></span>Step 7 – Updating Nameservers in Domain Registrar<span class="ez-toc-section-end"></span>

Finally, update the name servers in the domain registrar.

Update the name servers as [ns1.digitalocean.com](http://ns1.digitalocean.com). So this is the server which will be looked upon by the browsers to check the content of the websites.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

In this article, you have migrated wordpress from shared hosting to VPS hosting by DigitalOcean. Here are some of the questions you may get in mind and answers to them.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1604540890593">### **How to move wordpress site from godaddy to digitalocean**?

<div class="rank-math-answer ">This guide walks you through the steps to migrate from any hosting provider to digitalocean hosting provider. Follow this guide and comment if you have any questions.

</div></div><div class="rank-math-list-item" id="faq-question-1604541047314">### **Is DigitalOcean good for WordPress?**

<div class="rank-math-answer ">Yes, it is good and the are famous for high performance VPS. They also provide one click installation options for hosting wordpress in their cloud with one click.

</div></div><div class="rank-math-list-item" id="faq-question-1604541060800">### **How do I install WordPress on cloud hosting?**

<div class="rank-math-answer ">You can follow step-2 and step-3 of this tutorial to install WordPress on cloud hosting.

</div></div><div class="rank-math-list-item" id="faq-question-1604541073222">### **What is the best hosting for WordPress?**

<div class="rank-math-answer ">The world is moving towards cloud. Hence its better to host wordpress in any of the cloud service provider to be more secure and safe.

</div></div><div class="rank-math-list-item" id="faq-question-1604541113999">### **Is DigitalOcean good for website hosting?**

<div class="rank-math-answer ">Yes, DigitalOcean is changing the hosting space by high quality cloud servers at an affordable cost.

</div></div><div class="rank-math-list-item" id="faq-question-1604541164927">### **Is DigitalOcean reliable?**

<div class="rank-math-answer ">Yes, It is reliable. With more that 5,50,000 developers already in DigitalOcean, they are one of the most reliable cloud hosting providers.

</div></div><div class="rank-math-list-item" id="faq-question-1604541202517">### **Does Cloudways have cPanel?**

<div class="rank-math-answer ">No, Cloudways doesn not have cPanel. However, it has better and simplified dashboard than cPanel to maintain your websites.

</div></div></div></div>