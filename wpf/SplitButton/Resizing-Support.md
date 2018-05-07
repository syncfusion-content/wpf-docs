---
layout: post
title: Resizing Support | SplitButton | wpf | Syncfusion
description: resizing support
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Resizing Support

The DropDownMenuGroup supports resizing, if the property IsResizable is set to true.

Setting IsResizable property to true:

{% tabs %}
{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" 
x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup IsResizable=”True”>
<shared:DropDownMenuItem Header="Menu Item 1"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}
{% endtabs %}

![](Resizing-Support_images/Resizing-Support_img1.png)



