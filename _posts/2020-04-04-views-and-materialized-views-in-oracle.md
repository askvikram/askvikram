---
id: 226
title: 'Fundamental Differences Between Views and Materialized Views in Oracle'
date: '2020-04-04T08:53:32+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=19'
permalink: /views-and-materialized-views-in-oracle/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '69'
    - '12'
rank_math_description:
    - 'In this article, let''s discuss about views and materialized views in Oracle, their key differences and when to use them.'
rank_math_focus_keyword:
    - 'views and materialized views'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_seo_score:
    - '67'
socialsnap_share_count_timestamp:
    - '2023-09-12 00:21:47'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, lets discuss about the difference between the Views and Materialized view in Oracle.

## <span class="ez-toc-section" id="2_views"></span>2. Views<span class="ez-toc-section-end"></span>

Views are a **virtual form of a table** created by using one or more table(s) or view(s). This virtual table consists of the data retrieved by using the query expression used to define the view.

The data in the view is **not actually precomputed or stored** in the database. Whenever the view is accessed, the data is computed and the result is provided, thus always providing the updated data from the table.

The below syntax shows the command to create the view.

<div class="wp-block-codemirror-blocks-code-block code-block">```
Create View Viewname As <Query Expression>
```

</div>In principle, CRUD operations such as **Insert, Update, Delete are possible** in view and all the operations are performed in the data of the underlying table. On the other hand, views defined with the Group by Clause, Distinct Clause, or Check constraints(If the constraint violated), or read-only option don’t allow the CRUD operations.

## <span class="ez-toc-section" id="3_materialized_views"></span>3. Materialized Views<span class="ez-toc-section-end"></span>

Materialized views are physical copy of the underlying database tables. It is like a snapshot. The data in the materialized views are precomputed and stored as an object in the database. Hence, the result from the materialized view is not always up-to-date.

The below syntax shows the command to create the materialized view.

<div class="wp-block-codemirror-blocks-code-block code-block">```
Create Materialized View M_ViewName
Build [clause] Refresh [type]
ON [trigger]
As <query expression>
```

</div>The materialized views has to be updated manually using triggers or the manual update commands. **Build \[clause\]** decides when the data will be **populated** and **Refresh \[Type\]** option in the materialized view creation statement decides when the view will be **updated**.

Unlike views, CRUD operations are not possible in the materialized views.

## <span class="ez-toc-section" id="4_key_differences"></span>4. Key Differences<span class="ez-toc-section-end"></span>

Lets see what are the key differences between Views and Materialized Views.

<figure class="wp-block-table is-style-regular">| Type | Views | Materialized View |
|---|---|---|
| Data Stored Physically | No | Yes |
| Performance | Slower | Faster |
| Memory Usage | NA | High |

</figure>## <span class="ez-toc-section" id="5_conclusion"></span>5. Conclusion<span class="ez-toc-section-end"></span>

In conclusion, we have learned about the Views and Materialized views in Oracle. Materialized views are always faster but data may not be up-to-date whereas Views are slower but data is always up-to-date. Users can make the decision on the requirements.