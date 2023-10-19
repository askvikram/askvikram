---
id: 154
title: 'Basic Differences Between SQL Inner Join and Outer Join'
date: '2022-06-01T09:48:32+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=154'
permalink: /difference-between-sql-inner-join-and-outer-join/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_seo_score:
    - '68'
rank_math_focus_keyword:
    - 'SQL Inner Join and Outer Join,Inner Join,Outer Join,Joins'
rank_math_description:
    - 'In this article, Let''s discuss the difference between SQL Inner Join and Outer Join. '
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
ss_social_share_disable:
    - '0'
rank_math_analytic_object_id:
    - '87'
socialsnap_share_count_timestamp:
    - '2023-08-25 15:06:48'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, let’s discuss the difference between SQL Inner Join and Outer Join.

## <span class="ez-toc-section" id="2_joins"></span>2. Joins<span class="ez-toc-section-end"></span>

A **Join clause** helps the user to combine values from *two or more tables based on a correlation between them*. The relation between them is typically lying on the columns of Table A and Table B that have matching values.

### 2.1. Uses of Joins

In a relational database, data is distributed in many related tables. Join Clause helps the programmer to obtain the data from more than 1 table by using the values common to each. It pieces the data together and makes it useful and understandable. In most cases, it matches the column value of one table with another table.

## <span class="ez-toc-section" id="3_inner_join"></span>3. Inner Join<span class="ez-toc-section-end"></span>

**Inner Join** is also called as *EQUIJOIN*. This matches the left table to the right table. It retrieves the data by combining the values of two tables. This Join returns the rows from table 1 that matches with the rows from table 2. The column values of matched rows of the two tables are combined into a result row.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT     table1.column1, 
           table2.column2... 
FROM       table1 
INNER JOIN table2 
ON         table1.common_field = table2.common_field;
```

</div>## <span class="ez-toc-section" id="4_outer_join"></span>4. Outer Join<span class="ez-toc-section-end"></span>

An Outer Join returns a set of records that includes what an Inner Join would but also includes other rows for which no match is found.

### 4.1. Full Join

**Full Outer Join** or ***Full Join***. This Join not only return the rows that are matched, but also the rows which are mismatched. These mismatched sides will have NULLS.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT    table1.column1, 
          table2.column2... 
FROM      table1 
FULL JOIN table2 
ON        table1.common_field = table2.common_field;
```

</div>### 4.2. Left Outer Join

A Left Outer Join will return all the data in Table 1 and also the shared data that the Table 2 had in common.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT table1.column1, 
       table2.column2, 
FROM   table1 
LEFT OUTER JOIN table2 
ON table1.common_field = table1.common_field2; 
```

</div>### 4.3. Right Outer Join

A Right Outer Join is a reverse form of Left Outer Join where it returns all the data in Table 2 and also the data Table 1 had in common.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT table1.column1, 
       table2.column2, 
FROM   table1 
RIGHT OUTER JOIN table2 
ON table1.common_field = table1.common_field2; 
```

</div>## <span class="ez-toc-section" id="5_differences_between_sql_inner_join_and_outer_join"></span>5. Differences Between Sql Inner Join and Outer Join<span class="ez-toc-section-end"></span>

<figure class="wp-block-table is-style-regular">| Inner Join | Outer Join |
|---|---|
| Inner Joins don’t tweak non-matching rows | Outer Joins includes both matching and non-matching rows in the result set |
| No types of Inner Join | Three types of Outer Join   Left Outer Join   Right Outer Join   Full Outer Join |
| Size of the results returned by the Inner Join is comparatively smaller than Outer Join | Outer Join returns larger database |

</figure>## <span class="ez-toc-section" id="6_conclusion"></span>6. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we have the differences between SQL Inner Join and Outer Join.