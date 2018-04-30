---
layout: post
title: DropDownMenuItem| DropDownButtonAdv | Wpf | Syncfusion
description: dropdownmenuitem
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# DropDownMenuItem

## Adding Icon to DropDownMenuItem

The DropDownMenuItem control is a basic MenuItem, which forms the actual items of DropDownMenuGroup. 

The icon of the DropDownMenuItem can be added as follows:

{% tabs %}
{% highlight xaml %}

<shared:DropDownButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1">
<shared:DropDownMenuItem.Icon>
<Image Source="Images/Home.png"/>
</shared:DropDownMenuItem.Icon>
</shared:DropDownMenuItem>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:DropDownButtonAdv>

{% endhighlight %}
{% endtabs %}

![](DropDownMenuItem_images/DropDownMenuItem_img1.png)

## Checkable DropDownMenuItem

The DropDownMenuItem can be checked by setting the IsCheckable property to true. 

The feature can be enabled by using the property IsCheckable:

{% tabs %}
{% highlight xaml %}

<shared:DropDownButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1" IsCheckable="True"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3" IsCheckable="True"/>
</shared:DropDownMenuGroup>
</shared:DropDownButtonAdv>

{% endhighlight %}
{% endtabs %}

![](DropDownMenuItem_images/DropDownMenuItem_img2.png)
