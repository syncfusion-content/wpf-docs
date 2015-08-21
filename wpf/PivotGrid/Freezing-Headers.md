---
layout: post
title: Freezing-Headers
description: freezing headers 
platform: wpf
control: PivotGrid
documentation: ug
---


# Freezing Headers

PivotGrid for WPF provides built-in support for freezing column and row headers. This is achieved by setting the FreezeHeaders property of PivotGrid to True. This feature also enables scrolling through the value cells.

{% highlight C# %}  


// To Freeze Grid Headers

this.PivotGridControl1.FreezeHeaders = true;

{% endhighlight %} 


{% highlight vbnet %} 

' To Freeze Grid Headers

Me.PivotGridControl1.FreezeHeaders = True 

{% endhighlight %} 


![](Features_images/Features_img1.png)



