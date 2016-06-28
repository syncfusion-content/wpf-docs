---
layout: post
title: Freeze Headers| OlapGrid | Wpf | Syncfusion
description: freeze headers
platform: wpf
control: OlapGrid
documentation: ug
---

# Freeze Headers

OlapGrid provides built-in support to freeze the column and row headers. This is achieved by setting the **"FreezeHeaders"** property of OlapGrid to **"true"**.

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

![](Freeze-Headers_images/Freeze-Headers_img1.png)

A sample demo is available at the following location:

{system drive:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapGrid.WPF\Samples\Appearance\Frozen Header


