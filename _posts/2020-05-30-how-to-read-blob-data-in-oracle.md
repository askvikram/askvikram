---
id: 325
title: 'How to Read Blob Data in Oracle?'
date: '2020-05-30T13:39:11+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://oracle.soy/?p=325'
permalink: /how-to-read-blob-data-in-oracle/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '75'
    - '1'
rank_math_seo_score:
    - '70'
rank_math_focus_keyword:
    - 'how to read blob data in oracle'
rank_math_description:
    - 'In this article, we will discuss how to read blob data in oracle. This also explains how to select the data from the BLOB using the DBMS_LOB utility.'
rank_math_primary_category:
    - '9'
socialsnap_share_count_timestamp:
    - '2023-09-15 07:07:11'
ss_total_share_count:
    - '0'
categories:
    - Oracle
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

In this article lets look at how to read blob data in Oracle. We will also look how to select blob data in Oracle. BLOB is nothing but a datatype which is used to store the large data.

For storing large data, Oracle Oracle offers the BLOB, CLOB

## <span class="ez-toc-section" id="2_read_blob_data"></span>2. Read Blob Data<span class="ez-toc-section-end"></span>

Oracle has a utility DBMS\_LOB utility which provides many utilities for all relevant BLOB Operations.

*SUBSTR* utility from DBMS\_LOB can be used to convert BLOB to Substr as per the syntax given below.

<div class="wp-block-codemirror-blocks-code-block code-block">```
SELECT DBMS_LOB.SUBSTR(BLOB_FIELD_NAME) FROM TABLE_NAME;
```

</div>## <span class="ez-toc-section" id="3_conclusion"></span>3. Conclusion<span class="ez-toc-section-end"></span>

To conclude, we’ve seen how to select the data from Oracle BLOB using SUBSTR function of the DBMS\_LOB utility .

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1590826185113">### How to Read Blob Data in Oracle?

<div class="rank-math-answer ">SELECT DBMS\_LOB.SUBSTR(BLOB\_FIELD\_NAME) FROM TABLE\_NAME;

</div></div></div></div>