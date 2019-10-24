---
layout: post
title: Scroll Bar Support | SplitButton | wpf | Syncfusion
description: scroll bar support
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Scroll Bar Support

The DropDownMenuGroup is shipped with the built-in scrollbar support. It can be made visible by using the ScrollBarVisibility property.

Setting ScrollBarVisibility property to Visible:

{% tabs %}
{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup IsResizable=”True” ScrollBarVisibility=”True”>
<shared:DropDownMenuItem Header="Menu Item 1"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}
{% endtabs %}

![](Scroll-Bar-Support_images/Scroll-Bar-Support_img1.png)

