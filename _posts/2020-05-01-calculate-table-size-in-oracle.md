---
id: 238
title: 'How to Calculate Table Size in Oracle?'
date: '2020-05-01T08:11:30+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'https://www.sql.qa/?p=238'
permalink: /calculate-table-size-in-oracle/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '70'
    - '5'
rank_math_seo_score:
    - '64'
rank_math_robots:
    - 'a:1:{i:0;s:5:"index";}'
rank_math_focus_keyword:
    - 'calculate table size in oracle,query to calculate table size in oracle,oracle calculate table size with lobs,oracle calculate table size in mb,oracle calculate table size in gb'
rank_math_description:
    - 'In this article, we''ve discussed how to calculate table size in Oracle using the dba_segments views(for. individual tables and All tables). '
rank_math_primary_category:
    - '6'
socialsnap_share_count_timestamp:
    - '2023-09-14 16:12:08'
ss_total_share_count:
    - '0'
categories:
    - Oracle
    - sql
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article, let’s discuss the steps to calculate the table size in Oracle in detail.

In Oracle, data is stored in blocks. Contagious number of blocks is called *Extent*. One or more extent makes up a segment which corresponds to a table, a table partition or an index. The *dba\_segments* is the dictionary where the details about the segments are stored. When using this *dba\_segments*, we get the size of the physical data itself.

## <span class="ez-toc-section" id="2_calculate_table_size"></span>2. Calculate table size<span class="ez-toc-section-end"></span>

To calculate the size of a table in **‘MB’** from the dba\_segments dictionary, the following query can be used. DBA rights is required to query the dba\_segments dictionary.

<div class="wp-block-codemirror-blocks-code-block code-block">```
select segment_name,segment_type,bytes/1024/1024 MB
 from dba_segments
 where segment_type='TABLE' and segment_name='<yourtablename>';
```

</div>If you do not have dba rights, then you can query user\_segments view.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT bytes / 1024 / 1024 MB 
FROM   user_segments 
WHERE  segment_name = 'Table_name' 
```

</div>## <span class="ez-toc-section" id="3_calculate_all_tables_size"></span>3. Calculate all tables size<span class="ez-toc-section-end"></span>

To calculate the size of all tables in **‘MB’** from the *dba\_segments* dictionary, the following query can be used.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT DS.TABLESPACE_NAME, SEGMENT_NAME, ROUND(SUM(DS.BYTES) / (1024 * 1024)) AS MB
  FROM DBA_SEGMENTS DS
  WHERE SEGMENT_NAME IN (SELECT TABLE_NAME FROM DBA_TABLES)
 GROUP BY DS.TABLESPACE_NAME,
       SEGMENT_NAME;                                                              
```

</div>## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To conclude, we’ve discussed how to calculate table size in Oracle using the dba\_segments view. There are also other ways to calculate the table size using *dba\_tables*, *all\_tables* or *user\_tables*. However these views return only estimates and not the exact data size. To calculate the exact statistics from these view, the statistics needs to be gathered first.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1588300320832">### what is difference between Dba\_segments and Dba\_tables?

<div class="rank-math-answer ">The *dba\_segments* describes the “physical” data segment, like a data file while *dba\_tables* view describes a “logical” structure of the table.

</div></div><div class="rank-math-list-item" id="faq-question-1588300344670">### What are Oracle Segments?

<div class="rank-math-answer ">A **segment** is a set of extents that contains all the data for a specific logical storage structure within a tablespace.

</div></div><div class="rank-math-list-item" id="faq-question-1588300472307">### **How to check** dba\_segments **in oracle**?

<div class="rank-math-answer ">select segment\_name,segment\_type,bytes/1024/1024 MB  
from dba\_segments

</div></div></div></div>