---
id: 60
title: 'Important Differences Between SQL HAVING vs WHERE Clause'
date: '2020-04-21T12:15:48+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=60'
permalink: /sql-having-vs-where-clause/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '65'
    - '9'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_seo_score:
    - '75'
rank_math_focus_keyword:
    - 'SQL Having vs Where,SQL Having and Where'
rank_math_description:
    - 'In this article, We''ll discuss the difference between SQL Having vs Where Clauses. Additionally let''s also see "How to use", "when to use" these Clauses.'
rank_math_pillar_content:
    - 'off'
socialsnap_share_count_timestamp:
    - '2023-09-17 05:45:09'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, We’ll discuss the difference between **SQL Having** vs **Where** **Clauses**. Additionally let’s also see “**How** to use”, “**when** to use” these Clauses.

## <span class="ez-toc-section" id="2_sql_having"></span>2. SQL Having<span class="ez-toc-section-end"></span>

**Having clause** is used with **Select statement** in combination with the **GROUP BY** Clause.

The aggregate functions (*Average, Count, Count (\*), Max, Min, Sum*) summarizes the data and enables us to organize it into categories and subgroups with the help of Having Clause. This Clause retrieves the data from the Group rows not on individual rows which enables it to interact easily with Aggregate functions.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT column1, 
       Count(column2) 
FROM   table_name 
GROUP  BY column1 
HAVING column1 = 1; 
```

</div>## <span class="ez-toc-section" id="3_sql_where"></span>3. SQL Where<span class="ez-toc-section-end"></span>

**Where clause** fetches the data from an individual row where it specifies a search condition of a Select Statement.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT column1, 
       column2, 
       column3, 
       column4, 
FROM   table_name 
WHERE  column1 = 101; 
```

</div>## <span class="ez-toc-section" id="4_when_to_use_having_vs_where"></span>4. When to Use Having vs Where<span class="ez-toc-section-end"></span>

Use **Where Clause** retrieve data from an *individual row* and it applies on each and every row.

Use **Having Clause** to filter data from group of rows alongside the *GROUP BY* Clause.

**NOTE:** Both of these Clauses can be used in the same *SELECT* query with an *aggregate function*. Before returning the data **Where** Clause will be applied first on individual rows to filter and results in creating groups only for which have been passed the condition then comes the **Having** Clause to filter Groups based upon the condition specified.

## <span class="ez-toc-section" id="5_sql_having_vs_where_clause"></span>5. SQL Having vs Where clause<span class="ez-toc-section-end"></span>

<figure class="wp-block-table">| Where | Having |
|---|---|
| It is processed **before** the groups are created | It is processed **after** the groups are created |
| SQL evaluates the condition **before** the aggregates take place | SQL evaluates the condition **after** the aggregates take place |

</figure>## <span class="ez-toc-section" id="6_conclusion"></span>6. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we have seen differences between SQL Having vs where clause and also when to use it appropriately.

## <span class="ez-toc-section" id="frequently_asked_questions"></span>Frequently asked questions<span class="ez-toc-section-end"></span>

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1587470078905">### What are Oracle Reserved Keywords?

<div class="rank-math-answer ">Oracle reserved keywords can be found in this [Link](https://docs.oracle.com/cd/B10501_01/appdev.920/a42525/apb.htm).

</div></div><div class="rank-math-list-item" id="faq-question-1587470167619">### How to use Oracle reserved keywords for object names?

<div class="rank-math-answer ">Enclose the Oracle reserved keyword inside a “double-quotes” to indicate that is being used for object names.

</div></div><div class="rank-math-list-item" id="faq-question-1587471031341">### Can we just use Having instead of Where? 

<div class="rank-math-answer ">Well, sometimes we can and sometimes we can’t. Since they both filter records it depends on what we’re filtering on.

</div></div></div></div>