---
id: 240
title: 'How to Solve Ora-28000: The Account Is Locked Error?'
date: '2020-04-29T13:21:11+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=240'
permalink: /ora-28000-the-account-is-locked-error/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '71'
    - '6'
rank_math_seo_score:
    - '55'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_focus_keyword:
    - 'Ora-28000: The Account Is Locked,ora-28000 the account is locked error,ora-28000 the account is locked solution'
rank_math_description:
    - 'In this article, we will discuss about the root cause and solution for the error ORA-28000: The account is locked error in oracle.'
rank_math_rich_snippet:
    - article
rank_math_primary_category:
    - '3'
rank_math_schema_Article:
    - 'a:7:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:5:"9ezfd";}s:11:"description";s:130:"In this article, we will discuss about the root cause and solution for the error ORA-28000: The account is locked error in oracle.";s:8:"metadata";a:3:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";}}'
socialsnap_share_count_timestamp:
    - '2023-09-16 13:05:26'
ss_total_share_count:
    - '0'
categories:
    - ora-err
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we will discuss about the root cause and solutions for the error Ora-28000: The Account is locked in oracle.

## <span class="ez-toc-section" id="2_ora-28000_cause"></span>2. ORA-28000 Cause<span class="ez-toc-section-end"></span>

The error normally occurs when the database user account is locked either locked after the multiple wrong password attempts or the DBA manually locks the account for any reason.

Also the user account will be locked if you try to login multiple times when the password is expired.

## <span class="ez-toc-section" id="3_ora-28000_solution"></span>3. ORA-28000 Solution<span class="ez-toc-section-end"></span>

The user account must be unlocked by DBA by using the following query.

<div class="wp-block-codemirror-blocks-code-block code-block">```
ALTER USER USER_NAME ACCOUNT UNLOCK;
```

</div>As a preventive option, we can increase the number of FAILED\_LOGIN\_ATTEMPTS parameter set in the Oracle database.

This would increase number of failed login attempt before password is locked. On the other hand, the **security of the database is compromised** with the increased number of Failed Login attempts.

## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

Finally, we have discussed the root cause for the error ORA-28000: the account is unlocked error and the different ways to solve the error. Feel free to comment if you have any questions.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1588145977625">### How to unlock Oracle user account?

<div class="rank-math-answer ">ALTER USER USER\_NAME ACCOUNT UNLOCK;

</div></div><div class="rank-math-list-item" id="faq-question-1588146053441">### What are the privileges required to unlock the user account in Oracle? 

<div class="rank-math-answer ">DBA privileges are required to unlock a user account in Oracle.

</div></div><div class="rank-math-list-item" id="faq-question-1588146179398">### How to change password lifetime in Oracle? 

<div class="rank-math-answer ">you can set the password\_life\_time using the query:  
`ALTER PROFILE DEFAULT LIMIT PASSWORD_LIFE_TIME 10;`

</div></div><div class="rank-math-list-item" id="faq-question-1588146263194">### How to check password lifetime in Oracle? 

<div class="rank-math-answer ">Password life time depends on the profile assigned to each user. Check the password life time of the profile assigned to the user using the query.   
`SELECT resource_name, limit FROM dba_profiles WHERE profile = 'DEFAULT' AND resource_type = 'PASSWORD';`

</div></div><div class="rank-math-list-item" id="faq-question-1588146376437">### How to set Password lifetime to unlimited in Oracle?

<div class="rank-math-answer ">ALTER PROFILE DEFAULT LIMIT PASSWORD\_LIFE\_TIME UNLIMITED;

</div></div></div></div>