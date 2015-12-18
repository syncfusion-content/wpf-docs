---
layout: post
title: RibbonMenuItem in Syncfusion Ribbon control
description: RibbonMenuItem in Syncfusion Ribbon control
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonMenuItem

`RibbonMenuItem` used as entity in menus like ApplicationMenu, DropDownButton, SplitButton, context menu, and so on.


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  >

<syncfusion:RibbonBar Name="_ribbonBar1">

<syncfusion:RibbonMenuItem  Header="NEW" Width="100"></syncfusion:RibbonMenuItem>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonMenuItem and add it to RibbonBar through code behind.

{% tabs %}

{% highlight C# %}

RibbonMenuItem _ribbonMenuItem = new RibbonMenuItem(){Header = "NEW", Width = 100};

_ribbonBar1.Items.Add(_ribbonMenuItem);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonMenuItem As New RibbonMenuItem() With {
	.Header = "NEW",
	.Width = 100
}

_ribbonBar1.Items.Add(_ribbonMenuItem)

{% endhighlight %}

{% endtabs %}

![](RibbonMenuItem_images/RibbonMenuItem_img1.jpg)


