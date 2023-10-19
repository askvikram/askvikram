---
id: 82
title: 'Simple Ways to Solve Ora-01722 Invalid Number Error?'
date: '2020-04-18T06:06:11+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=82'
permalink: /ora-01722-invalid-number/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '66'
    - '11'
rank_math_primary_category:
    - '3'
rank_math_description:
    - 'In this article, we will discuss about the causes of ora-01722 invalid number error and different ways to solve this error.'
rank_math_focus_keyword:
    - 'ora-01722 invalid number'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_seo_score:
    - '69'
rank_math_rich_snippet:
    - article
rank_math_schema_Article:
    - 'a:7:{s:5:"@type";s:11:"BlogPosting";s:8:"headline";s:11:"%seo_title%";s:13:"datePublished";s:20:"%date(Y-m-dTH:i:sP)%";s:12:"dateModified";s:24:"%modified(Y-m-dTH:i:sP)%";s:6:"author";a:2:{s:5:"@type";s:6:"Person";s:4:"name";s:5:"9ezfd";}s:11:"description";s:123:"In this article, we will discuss about the causes of ora-01722 invalid number error and different ways to solve this error.";s:8:"metadata";a:3:{s:5:"title";s:7:"Article";s:9:"isPrimary";b:1;s:4:"type";s:8:"template";}}'
socialsnap_share_count_timestamp:
    - '2023-09-14 09:08:08'
ss_total_share_count:
    - '0'
categories:
    - ora-err
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, we’ll discuss about the root causes of ora-01722 invalid number error and possible ways to solve this error based on its usage.

## <span class="ez-toc-section" id="2_root_cause"></span>2. Root Cause<span class="ez-toc-section-end"></span>

The error occurs when we try to convert a string or any other datatype value to a number but the conversion attempt is failed.

This error can also happen when we try to insert a *non-numeric* value to a column which is defined as *number* datatype.

## <span class="ez-toc-section" id="3_solution"></span>3. Solution<span class="ez-toc-section-end"></span>

Lets see how to solve the error based on the usage of the function.

### 3.1. ora-01722 in to\_number()

**to\_number()** function is used to convert a string literal with the numeric value to a number. Ensure the string literal passed to this function contains only numbers and not any other non numeric characters.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT To_number('123456') 
FROM   dual; 
```

</div>### 3.2. ora-01722 in to\_char()

**to\_char()** function is used to convert a number or a date to a string datatype.

 Invalid number error will be thrown if we pass date as a normal string as below.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT To_char('03-JAN-2013', 'D') 
FROM   dual; 
```

</div>Hence the string needs to be cast as date before using it in the To\_Char function. Example as below.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT To_char(To_date('03-JAN-2013'), 'D') 
FROM   dual; 
```

</div>### 3.3. ora-01722 in Aggregate Functions

Invalid number error occurs during the usage of the aggregate functions such as Sum() when the non-numeric columns are passed to these types of aggregate functions.

In the following query, we are trying to Sum the name of the customers which is not possible. Hence the invalid number error will be thrown.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT SUM(name) 
FROM   customers; 
```

</div>### 3.4. ora-01722 in Insert/Update

Invalid number error occurs when we try to insert or update a non numeric value to the numeric value column.

In the below e.g., we are trying to update mobile number with invalid character ‘-‘. Hence the invalid number error will be thrown.

<div class="wp-block-codemirror-blocks-code-block code-block">```
UPDATE customers
SET mobilenumber = '+91-123456789'
WHERE customer_id = 2;
```

</div>## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To conclude, we’ve discussed in detail about various ways of solving ora-01722 invalid number error.