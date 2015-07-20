---
layout: post
title: Subset-Filter
description: subset filter
platform: wpf
control: OLAP Client 
documentation: ug
---

# Subset Filter

Subset filter is used to filter the number of records in the result set. Subset filter will get a numeric number as input and restrict the number of records within that count.

{{ '![](Subset-Filter_images/Subset-Filter_img1.png)' | markdownify }}
{:.image }


We can specify the subset filter for both row and column.

ShowSubsetFilters

Users can toggle the visibility of SubSetFilters by using this property. This property will accept a Boolean value (true/false) based on this value it sets the visibility of SubSetFilters.

[C#]



this.olapClient1.ShowSubsetFilters = false;





[VB]



Me.olapClient1.ShowSubsetFilters = False



