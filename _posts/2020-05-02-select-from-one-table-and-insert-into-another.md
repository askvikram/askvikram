---
id: 250
title: 'How to Select From One Table and Insert Into Another?'
date: '2020-05-02T19:12:24+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=250'
permalink: /select-from-one-table-and-insert-into-another/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '73'
    - '4'
rank_math_seo_score:
    - '62'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_focus_keyword:
    - 'How to select from one table and insert into another,select from one table into another,select from one table and update into another'
rank_math_description:
    - 'In this article, we''ll discuss on how to select from one table and insert into another table using Insert into statement and create table based on another table'
rank_math_primary_category:
    - '6'
socialsnap_share_count_timestamp:
    - '2023-09-06 13:47:11'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we’ll discuss on how to select from one table and insert into another table using *Insert into* statement and create table based on another table in oracle.

## <span class="ez-toc-section" id="2_using_insert_into_statement_copy_data_to_existing_table"></span>2. Using Insert into Statement (Copy data to existing table)<span class="ez-toc-section-end"></span>

To insert data from another table using insert into statement, *Select statement* should be used directly after the column names of the normal insert query **instead of using the *Values* keyword**. The columns specified in the insert statement and select statement should be same and also in the same order.

we can select from one table and insert into another table by using the following sql query

<div class="wp-block-codemirror-blocks-code-block code-block">```
INSERT INTO targettable
    (COLUMN_NAMES) //seperated by comma
    SELECT COLUMN_NAMES FROM sourcetable 
```

</div>## <span class="ez-toc-section" id="3_create_table_based_on_records_from_another_table"></span>3. Create table based on records from another table<span class="ez-toc-section-end"></span>

To create a new table based on the data available from another table, the following create table statement can be used. This will create table and also copy the data.

<div class="wp-block-codemirror-blocks-code-block code-block">```
create table new_table as 
select * from old_table
```

</div>To create a new table with only specific columns and its data, the following create table statement can be used.

<div class="wp-block-codemirror-blocks-code-block code-block">```
create table new_table as 
select column1, column2 from old_table
```

</div>To just create a empty table based on another table without copying the data, use a where clause which can never be true.

<div class="wp-block-codemirror-blocks-code-block code-block">```
create table new_table as 
select * from old_table
where 1 = 2
```

</div>**Note:** Create table as select **only** creates the table similar to the source table. It will not copy the any triggers, constraints or indexes from the source table. Those objects needs to be created manually, if required.

## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we have discussed about how to select from one table and insert into another by using the Insert into statement and create table statements.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1588426743929">### How to select from one table and insert into another?

<div class="rank-math-answer ">Insert into targettable  
(COLUMN\_NAMES) //seperated by comma  
SELECT COLUMN\_NAMES FROM sourcetable

</div></div><div class="rank-math-list-item" id="faq-question-1588426811744">### How to create table based on another table from Oracle?

<div class="rank-math-answer ">create table new\_table as  
select \* from old\_table

</div></div></div></div>