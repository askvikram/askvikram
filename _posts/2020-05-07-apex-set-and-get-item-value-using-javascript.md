---
id: 300
title: 'Oracle Apex Set and Get Item Value Using Javascript'
date: '2020-05-07T05:07:51+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://oracle.soy/?p=300'
permalink: /apex-set-and-get-item-value-using-javascript/
rank_math_internal_links_processed:
    - '1'
    - '1'
rank_math_analytic_object_id:
    - '74'
    - '2'
rank_math_primary_category:
    - '4'
rank_math_seo_score:
    - '10'
rank_math_focus_keyword:
    - 'oracle apex javascript set item value,oracle apex javascript get item value,oracle apex javascript set page item value,oracle apex javascript get page item value'
rank_math_description:
    - 'In this article, we''ll see the ways to set and get page item values in Oracle apex using Javascript.'
socialsnap_share_count_timestamp:
    - '2023-09-16 10:51:23'
ss_total_share_count:
    - '0'
ss_ss_click_share_count_twitter:
    - '2'
categories:
    - Apex
---

## <span class="ez-toc-section" id="1_introduction"></span>1. Introduction<span class="ez-toc-section-end"></span>

Today most oracle apex applications contains Javascript code, particularly useful for making forms more interactive and user friendly.

In this article, we’ll see how to set item value and get item value using Javascript in Oracle Apex.

## <span class="ez-toc-section" id="2_set_item_value_using_javascript"></span>2. Set Item Value Using Javascript<span class="ez-toc-section-end"></span>

To set the page item value in apex we need to use **$S** function of the javascript.

The $ function can be used to set the value of Text item, Display only item or also hidden item in Apex.

The following examples shows the simplest way to set value of the page item in javascript.

<div class="wp-block-codemirror-blocks-code-block code-block">```
$s("P2_TEXT_FIELD","Hello World!");
$s("P2_DISPLAY_ONLY","Hello World!");
```

</div>There are few other ways to set the item values as well, shown below:

<div class="wp-block-codemirror-blocks-code-block code-block">```
$x("P2_TEXT_FIELD").value = "Hello World!";
$("#P2_DISPLAY_ONLY").text("Hello World!");
```

</div>To set the value using the Apex JavaScript API function:

<div class="wp-block-codemirror-blocks-code-block code-block">```
apex.item( "P2_TEXT_FIELD" ).setValue ("Hello World!");
```

</div>## <span class="ez-toc-section" id="3_get_item_value_using_javascript"></span>3. Get Item Value using Javascript<span class="ez-toc-section-end"></span>

To get the page item value in apex, we need to use **$** or **$x** function of the javascript.

The $ function can be used to get the value from Text item, Display only item or also hidden item in Apex.

The following example shows the simplest ways to get the value of the page item in Javascript.

<div class="wp-block-codemirror-blocks-code-block code-block">```
x = $("#P2_DISPLAY_ONLY").text(); //To get the text information of the item, simple $ function is used. 
$x("P2_TEXT_FIELD").value; // To get the value of the text field, $X is used.
```

</div>To get the page item values, we can also simply use the *$v(“&lt;item\_name&gt;”)*.

<div class="wp-block-codemirror-blocks-code-block code-block">```
x = $v("P2_TEXT_FIELD");
y = $v("P2_DISPLAY_ONLY");
```

</div>To get the value using the Apex JavaScript API function:

<div class="wp-block-codemirror-blocks-code-block code-block">```
apex.item( "P2_TEXT_FIELD" ).getValue();
```

</div>To access the multiple items in an array, **$v2()** comes handy. For example multiple selections from check boxes, the selected values can be accessed by using:

<div class="wp-block-codemirror-blocks-code-block code-block">```
myArr = $v2("P2_AREAS_OF_INTEREST");
for (idx=0; idx<myArr.length; idx++) {
  //do something with myArr[idx];
}
```

</div>## <span class="ez-toc-section" id="4_conclusion"></span>4. Conclusion<span class="ez-toc-section-end"></span>

To summarize, we’ve discussed the different way available in Oracle Apex to set page item value and get page item value.

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1588809042497">### How to get multiple items in Array using Javascript in Oracle Apex? 

<div class="rank-math-answer ">To access the multiple items in an array using javascript in oracle apex, **$v2()** function can be used.

</div></div></div></div>