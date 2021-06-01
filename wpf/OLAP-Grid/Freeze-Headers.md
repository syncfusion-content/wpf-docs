---
layout: post
title: Freeze Headers in WPF Olap Grid control | Syncfusion
description: Learn about Freeze Headers support in Syncfusion WPF Olap Grid control, its elements and more details.
platform: wpf
control: OlapGrid
 documentation: ug
---

# Freeze Headers in WPF Olap Grid

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


