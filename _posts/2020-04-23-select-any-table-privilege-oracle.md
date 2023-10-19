---
id: 169
title: 'Oracle Grant Select Any Table Privilege &#8211; Definitive Guide'
date: '2020-04-23T13:10:05+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=169'
permalink: /select-any-table-privilege-oracle/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '68'
    - '8'
rank_math_seo_score:
    - '70'
rank_math_focus_keyword:
    - 'select any table privilege,select any table privilege oracle 12c,grant select any table privilege to user'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
socialsnap_share_count_timestamp:
    - '2023-09-13 06:37:38'
ss_total_share_count:
    - '0'
ss_ss_click_share_count_facebook:
    - '1'
categories:
    - sql
tags:
    - privileges
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we will discuss about the oracle **Select Any Table Privilege**.

## <span class="ez-toc-section" id="2_select_any_table_privilege"></span>2. Select Any Table Privilege<span class="ez-toc-section-end"></span>

[Select Any table privilege](https://docs.oracle.com/en/database/oracle/oracle-database/12.2/sqlrf/GRANT.html#GUID-20B4E2C0-A7F8-4BC8-A5E8-BE61BDC41AC3__BABEFFEE) is a system privilege which allows the grantee to query any Table, View or a Materialized views from any schema except the sys Schema.

It is a standalone single privilege visible in *dba\_sys\_privs*.

When Oracle wants to check if the user is allowed to access an object, it first checks in the system privileges. If the user is privileged, then Oracle allows the select operation…

..If the user is not having the system privilege, then object level privilege of the user is checked(**Visible in *dba\_tab\_privs***) to check if the user is allowed to access the object. If yes, then it allows select operation.

### 2.1. Grant Select Any Table Privilege

The following SQl query shows how to *Grant Select Any Table* to user.

<div class="wp-block-codemirror-blocks-code-block code-block">```
GRANT SELECT ANY TABLE TO USERNAME; 
```

</div>**Caution:** Do not Grant Select ANY table privilege to Public as this privilege is only for trusted users.

### 2.2. Revoke Select Any Table Privilege

The follow SQL query shows how to *Revoke Select Any table* privilege to a user.

<div class="wp-block-codemirror-blocks-code-block code-block">```
REVOKE SELECT ANY TABLE FROM USERNAME;
```

</div>## <span class="ez-toc-section" id="3_conclusion"></span>3. Conclusion<span class="ez-toc-section-end"></span>

To Summarize, we have discussed about the Select Any table privilege in Oracle, Its Grant and Revoke Syntax and the cautions before using it. For more details about Roles and Privileges, refer Oracle Guide in this [link](https://docs.oracle.com/en/database/oracle/oracle-database/12.2/dbseg/configuring-privilege-and-role-authorization.html#GUID-89CE989D-C97F-4CFD-941F-18203090A1AC).

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1587646791463">### Is it possible to Grant select any table with Grant Option? 

<div class="rank-math-answer ">No, its not possible to Grant select any table with Grant option as it is a system privilege.

</div></div><div class="rank-math-list-item" id="faq-question-1587646920650">### Is it possible to Grant select any table with Admin Option?

<div class="rank-math-answer ">Yes, its possible to Grant Select any table with Admin option as select any table is a system privilege.

</div></div></div></div>