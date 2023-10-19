---
id: 192
title: 'What Is Default Date Format in Oracle?'
date: '2022-06-01T09:48:33+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=192'
permalink: /default-date-format-oracle/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_seo_score:
    - '59'
rank_math_focus_keyword:
    - 'default date format in oracle,default date format in oracle 12c,default date format oracle'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
ss_social_share_disable:
    - '0'
rank_math_analytic_object_id:
    - '86'
socialsnap_share_count_timestamp:
    - '2023-08-17 09:31:38'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we will discuss about the default date format in Oracle, How to change it with examples.

## <span class="ez-toc-section" id="2_default_date_format_in_oracle"></span>2. Default Date Format in Oracle<span class="ez-toc-section-end"></span>

Default date format of Oracle database is *DD-MON-RR* where RR refers to a two digit year.

## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we have seen the details about the default date format in Oracle, how to change the default date format.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1587785780974">### How to change the default date format in Oracle? (Session Level)

<div class="rank-math-answer ">ALTER SESSION SET nls\_date\_format = ‘DD/MM/YYYY’;

</div></div><div class="rank-math-list-item" id="faq-question-1587785895272">### How to View Current Date Format in Oracle? 

<div class="rank-math-answer ">SELECT \* FROM nls\_session\_parameters where paramter = ‘NLS\_DATE\_FORMAT’;

</div></div><div class="rank-math-list-item" id="faq-question-1587785938798">### How to get Current Date of System in Oracle? 

<div class="rank-math-answer ">Select SYSDATE from dual;

</div></div><div class="rank-math-list-item" id="faq-question-1587786279675">### How to change the default date format in Oracle? (System Level)

<div class="rank-math-answer ">ALTER SYSTEM SET nls\_date\_format =’DD/MM/YYYY’ scope=both;

</div></div><div class="rank-math-list-item" id="faq-question-1587817050319">### How to insert date values into table oracle?

<div class="rank-math-answer ">INSERT INTO tablename(Date\_Column\_name) VALUES(TO\_DATE(’17/12/2020′, ‘DD/MM/YYYY’));

</div></div></div></div>