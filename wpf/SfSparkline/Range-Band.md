---
layout: post
title: Range-Band
description: range band
platform: wpf
control: Sparkline
documentation: ug
---

# Range Band

Range band feature used to highlight the particular mentioned range along Y axis.

[XAML]

  <Syncfusion:SfLineSparkline 

                ItemsSource="{Binding UsersList}" 

                BandRangeStart="2000”

                BandRangeEnd="-1000” RangeBandBrush="Green”

                YBindingPath="NoOfUsers">

  &lt;/Syncfusion:SfLineSparkline &gt;

Following is the snapshot for range band,

{ ![C:/Users/ApoorvahR/Desktop/5.png](Range-Band_images/Range-Band_img1.png) | markdownify }
{:.image }


