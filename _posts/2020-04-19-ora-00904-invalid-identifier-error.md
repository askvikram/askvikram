---
id: 100
title: 'Simple Ways to Solve Ora-00904 Invalid Identifier Error'
date: '2020-04-19T13:12:02+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=100'
permalink: /ora-00904-invalid-identifier-error/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '67'
    - '10'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_seo_score:
    - '72'
rank_math_description:
    - 'In this article, we will discuss about the simple ways to solve )RA-00904 invalid identifier error. '
rank_math_focus_keyword:
    - 'Ora-00904 Invalid Identifier,ora-00904 invalid identifier date,ora-00904 invalid identifier create table'
socialsnap_share_count_timestamp:
    - '2023-09-13 10:29:51'
ss_total_share_count:
    - '0'
categories:
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we’ll discuss about the root cause and solution for the error ORA-00904 Invalid Identifier error.

## <span class="ez-toc-section" id="2_ora-00904_invalid_identifier_%e2%80%93_cause"></span>2. Ora-00904 Invalid Identifier – Cause<span class="ez-toc-section-end"></span>

The error commonly appears when we use the identifies such as column names which are not existing.

## <span class="ez-toc-section" id="3_solution"></span>3. Solution<span class="ez-toc-section-end"></span>

### 3.1. ORA-00904 in CREATE TABLE Statements

The error occurs when we use any invalid names/letters or using an [Oracle reserved keywords](https://docs.oracle.com/cd/B10501_01/appdev.920/a42525/apb.htm) in column names while creating table.

In the below create table statement, Comment is Oracle reserved keyword and this will cause Invalid identifier error when executed.

<div class="wp-block-codemirror-blocks-code-block code-block">```
CREATE TABLE test 
  ( 
     id      NUMBER, 
     name    VARCHAR2(200), 
     COMMENT VARCHAR2(4000) 
  ); 
```

</div>### 3.2. ORA-00904 in ALTER TABLE Statements

The error occurs when we try to modify a non-existent column or add a column with the reserved word as a column name. Also, this can occur if we use the keyword column while adding column as explained below:

<div class="wp-block-codemirror-blocks-code-block code-block">```
ALTER TABLE test 
  ADD COLUMN date_of_birth DATE; 
```

</div>*“Column”* word is not necessary as mentioned above. A column can be simply added as below.

<div class="wp-block-codemirror-blocks-code-block code-block">```
ALTER TABLE test 
  ADD date_of_birth DATE; 
```

</div>### 3.3. ORA-00904 in SELECT or INSERT or update Statements

The error occurs during select or insert or update when we refer to an invalid or non-existent column during the DML operations.

In the below update statement, dept\_id column is invalid in the test table but we try to update it. This will cause Invalid Identifier error.

<div class="wp-block-codemirror-blocks-code-block code-block">```
UPDATE test 
SET    dept_id=1 
WHERE  id=101;
```

</div>The column names used in the DML operation query **should be a valid column** to avoid this error.

### 3.4. ORA-00904 in PL/SQL Stored Procedures

When it comes to PL/SQL, Invalid identifier error occurs when we try to use any invalid column in the SQL query or when we refer to a variable which is not declared in the PL/SQL program.

## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

In this article, we have seen the reasons and the solution for Ora-00904 Invalid Identifier error.