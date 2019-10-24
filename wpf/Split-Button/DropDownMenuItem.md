---
layout: post
title: DropDownMenuItem | SplitButton | wpf | Syncfusion
description: dropdownmenuitem
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# DropDownMenuItem

## Adding icon to DropDownMenuItem

The DropDownMenuItem control is the basic MenuItem, which forms the actual item of the DropDownMenuGroup. The icon of the DropDownMenuItem can be added as follows:

{% tabs %}
{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1">
<shared:DropDownMenuItem.Icon>
<Image Source="Images/Drink2.png"/>
</shared:DropDownMenuItem.Icon>
</shared:DropDownMenuItem>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}
{% endtabs %}

![](DropDownMenuItem_images/DropDownMenuItem_img1.png)


## Checkable DropDownMenuItem

The DropDownMenuItem can be checked by setting the IsCheckable property to true. 

The feature can be enabled by using the property IsCheckable:

{% tabs %}
{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1" IsCheckable="True"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3" IsCheckable="True"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}
{% endtabs %}

![](DropDownMenuItem_images/DropDownMenuItem_img2.png)



