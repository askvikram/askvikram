---
id: 162
title: 'How to Use Group by Clause in Sql in Multiple Columns'
date: '2020-04-23T10:39:46+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=162'
permalink: /how-to-use-group-by-clause-in-sql-in-multiple-columns/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_seo_score:
    - '61'
rank_math_focus_keyword:
    - 'Use Group by Clause in Sql in Multiple Columns,Group by Clause in Multiple Columns'
rank_math_description:
    - 'In this article, we''ll discuss how to Use Group By Clause in Sql in Multiple Columns'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
ss_social_share_disable:
    - '0'
rank_math_analytic_object_id:
    - '88'
socialsnap_share_count_timestamp:
    - '2023-08-19 17:57:38'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="introduction"></span>Introduction<span class="ez-toc-section-end"></span>

In this article, we’ll discuss how to Use Group By Clause in Sql in Multiple Columns

## <span class="ez-toc-section" id="group_by_clause"></span>Group by Clause<span class="ez-toc-section-end"></span>

**Group By Clause** is used in a *SELECT* statement often with *Aggregate Function*. It combines rows into groups on the basis of matching value in the columns mentioned. One row will be returned for each group.

**NOTE**: It is not always mandatory to use an aggregate function with a SELECT query. However, if we use an aggregate function it will eventually bring us the summary value of each group.

In a query a Group Clause should be placed *after* the **WHERE** Clause but *before* the **Order By** Clause.

#### 2.1. Syntax of Group by Clause in a SELECT Query Without Using Aggregate Functions

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT select_list 
FROM   table_name 
GROUP  BY column_name1;
```

</div>2.2. Syntax of Group By clause in a SELECT query with using Aggregate functions

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT   column1, 
         Function_name(column2) 
FROM     table_name 
WHERE    condition 
GROUP BY column1, 
         column2;
         
FUNCTION_NAME: name OF the FUNCTION used FOR example, sum() , avg().
TABLE_NAME: name OF the TABLE.
CONDITION: condition used.
```

</div>## <span class="ez-toc-section" id="using_group_by_clause_in_multiple_columns"></span>Using Group by Clause in Multiple Columns<span class="ez-toc-section-end"></span>

Group By multiple column means to place all the rows having same values of both columns 1 and 2 in one group.

For instance, A shopkeeper wants to find out on a particular date how many products were sold. Then the query would look like

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT Date_purchased,
       Products, 
       Sum(Product_purchased) AS "Total Items" 
FROM   Purchases 
GROUP  BY Products, 
          Date_purchased;
```

</div>In the above scenario, for a given date how many individual items have been sold out. Obviously, we are dividing the result and Sql returns the data exactly how we wanted it to return.

## <span class="ez-toc-section" id="conclusion"></span>Conclusion<span class="ez-toc-section-end"></span>

To summarize, we have seen about how to use Group By clause in Sql in multiple column.