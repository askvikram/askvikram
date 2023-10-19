---
id: 225
title: 'How to Solve ORA-28001: The Password Has Expired Error?'
date: '2020-05-05T06:46:45+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=225'
permalink: /ora-28001-the-password-has-expired-error/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '72'
    - '3'
rank_math_seo_score:
    - '60'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_focus_keyword:
    - 'ORA-28001: The password has Expired Error'
rank_math_description:
    - 'In this article, we''ll discuss about the cause and solution for ORA-28001: the password has Expired error in Oracle. '
rank_math_primary_category:
    - '3'
socialsnap_share_count_timestamp:
    - '2023-09-15 11:04:48'
ss_total_share_count:
    - '0'
categories:
    - ora-err
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we’ll discuss root cause and solution for ORA-28001: the password has expired error in oracle.

## <span class="ez-toc-section" id="2_ora-28001_cause"></span>2. ORA-28001 Cause<span class="ez-toc-section-end"></span>

The error normally occurs when the password for your oracle database is expired and it must be changed.

Expiry happens when the password has reached the limit set in the **PASSWORD\_LIFE\_TIME** parameter of your Oracle user profile.

## <span class="ez-toc-section" id="3_ora-28001_solution"></span>3. ORA-28001 Solution<span class="ez-toc-section-end"></span>

The password of the user account must be reset for solving this error. To reset the account password the following query can be used.

<div class="wp-block-codemirror-blocks-code-block code-block">```
ALTER USER oraclesoy IDENTIFIED by '<New password>';
```

</div>If you are trying to access the database using SQL developer, then it will prompt you to enter a new password in order to change the expired password.

In case if the user account is also locked, it can be unlocked by following the steps [here](http://oracle.soy/ora-28000-the-account-is-locked-error/).

To prevent the password expiry of the Oracle user account, set the password life time to unlimited using the following query. (Requires DBA privilege)

<div class="wp-block-codemirror-blocks-code-block code-block">```
ALTER PROFILE DEFAULT LIMIT PASSWORD_LIFE_TIME UNLIMITED;
```

</div>## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we’ve discussed about the root cause and the solution for solving **ORA-28001: The password has Expired** Error.

Feel free to comment if you have any clarifications.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1588640964332">### How to set Password lifetime to unlimited in Oracle?

<div class="rank-math-answer ">ALTER PROFILE DEFAULT LIMIT PASSWORD\_LIFE\_TIME UNLIMITED;

</div></div><div class="rank-math-list-item" id="faq-question-1588641019940">### How to check password lifetime in Oracle?

<div class="rank-math-answer ">SELECT resource\_name, limit FROM dba\_profiles WHERE profile = ‘DEFAULT’ AND resource\_type = ‘PASSWORD’;

</div></div><div class="rank-math-list-item" id="faq-question-1588641202256">### How to change password in oracle database?

<div class="rank-math-answer ">ALTER USER username IDENTIFIED by ‘&lt;New Password&gt;’;

</div></div></div></div>