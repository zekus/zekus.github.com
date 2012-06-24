---
comments: true
date: '2010-03-31 10:00:21'
layout: post
slug: google-website-optimiser-and-the-bugged-techie-guide
status: publish
title: Google Website Optimiser and the bugged Techie Guide
wordpress_id: '341'
categories:
- Altro
- Javascript
tags:
- content-variation
- content_variation
- GWO
- techie guide
- Web Optimiser
---

I spent hours yesterday to implement the GWO that, instead, should take literally minutes!  
You want to know why? The bugged [Techie Guide](http://www.google.com/en//websiteoptimizer/techieguide.pdf)!!!  
  
On page 19, the script is completely wrong and drove me mad: variation-content should be **variation_content** and document.write(“</nosc” + “ript>”) should be **document.write(“<nosc” + “ript>”)**;  
  
So, here is he complete correct script:  
```
<script>  
var v = utmx(‘variation_content’, ‘Section1’);  
if (v) {  
document.write(  
v.replace(“%%product_name%%”, “<? print $product_name ?>”).  
replace(“%%product_price%%”, “<? print $product_price ?>”).  
replace(“%%product_id%%”, “<? print $product_id ?>”));  
document.write(“<nosc” + “ript>”);  
}  
</script>  
<ul>  
<li>Product name: <? print $product_name ?>  
<li>Product price: <? print $product_price ?>  
<li><a href=’buy.php?prod-id=<? print $product_id ?>’>  
Buy Now</a>  
</ul>  
</noscript>  
```
  
Adapt it to your code and be happy!
