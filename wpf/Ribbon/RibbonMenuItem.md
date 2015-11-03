---
layout: post
title: RibbonMenuItem | Ribbon | WPF | Syncfusion
description: RibbonMenuItem
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonMenuItem

RibbonMenuItems are used as entities in menus like ApplicationMenu, DropDownButton, SplitButton, context menu, and so on.

The following code example illustrates how to use RibbonMenuItem control in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  >

<syncfusion:RibbonBar Name="_ribbonBar1">

<syncfusion:RibbonMenuItem  Header="NEW" Width="100"></syncfusion:RibbonMenuItem>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>            

</syncfusion:Ribbon>



{% endhighlight %}

Create instance of RibbonMenuItem and add it to RibbonBar Items.

{% highlight c# %}

[C#]

RibbonMenuItem _ribbonMenuItem = new RibbonMenuItem(){Header = "NEW", Width = 100};

_ribbonBar1.Items.Add(_ribbonMenuItem);



{% endhighlight %}

![](RibbonMenuItem_images/RibbonMenuItem_img1.jpeg)


