---
layout: post
title:  Freeze Headers in WPF OlapGrid | Syncfusion®
description: The freeze headers support in OlapGrid allows freezing the column and row headers so they remain visible while scrolling the grid.
platform: wpf
control: OlapGrid
documentation: ug
---

# Freeze Headers in WPF OlapGrid

The OLAP grid provides built-in support to freeze the column and row headers. This can be achieved by setting the `FreezeHeaders` property of OLAP grid to **"true"**.

{% tabs %}
  
{% highlight xaml %}

<syncfusion:OlapGrid  FreezeHeaders="True"> 
</syncfusion:OlapGrid>

{% endhighlight %}

{% highlight c# %}

// To freeze OlapGrid Headers
this.OlapGrid1.FreezeHeaders = true;

{% endhighlight %}

{% highlight vbnet %}

' To freeze OlapGrid Headers
Me.OlapGrid1.FreezeHeaders = True

{% endhighlight %}

{% endtabs %}

![Enables the freeze headers in OlapGrid](Freeze-Headers_images/Freeze-Headers_img1.png)

A sample demo is available in the following location.

{system drive:}\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Appearance\Frozen Header


