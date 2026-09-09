---
layout: post
title: Freeze Headers in WPF OLAP Grid | Syncfusion®
description: The freeze headers support in OLAP Grid allows freezing the column and row headers so they remain visible while scrolling the grid.
platform: wpf
control: OLAP Grid
documentation: ug
---

# Freeze Headers in WPF OLAP Grid

The OLAP Grid provides built-in support to freeze the column and row headers. This can be achieved by setting the `FreezeHeaders` property of the control to **"true"**.

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

![Freeze headers enabled](Freeze-Headers_images/Freeze-Headers_img1.png)

A sample demo is available in the following location.

{system drive:}\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapGrid.WPF\Samples\Appearance\Frozen Header


