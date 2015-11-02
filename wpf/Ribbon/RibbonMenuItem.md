---
layout: post
title: RibbonMenuItem
description: RibbonMenuItem
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonMenuItem

RibbonMenuItems are used as entities in menus like **ApplicationMenu**, Split Button Menu, context menu, and so on.

The following code example illustrates How to use **RibbonMenuItem** control in **Ribbon** instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  >

<syncfusion:RibbonBar Name="_RibbonBar1">

<syncfusion:RibbonMenuItem  Header="NEW" Width="100"></syncfusion:RibbonMenuItem>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>            

</syncfusion:Ribbon>



{% endhighlight %}

Create instance of RibbonMenuItem and add it to RibbonBar Items.

{% highlight c# %}

[C#]

RibbonMenuItem _RibbonMenuItem = new RibbonMenuItem(){Header = "NEW", Width = 100};

_RibbonBar1.Items.Add(_RibbonMenuItem);



{% endhighlight %}

![](RibbonMenuItem_images/RibbonMenuItem_img1.jpeg)


