---
layout: post
title: Ribbon TabPanelItem
description: Ribbon TabPanelItem
platform: wpf
control: Ribbon
documentation: ug
---
# Ribbon TabPanelItem

You can set RibbonTabPannelItem in Ribbon instance like in Microsoft Office. It located on below the close button of RibbonWindow.

The following code example illustrates How to use RibbonTabPannelItem control in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_RibbonBar1">

<syncfusion:RibbonMenuItem  Header="NEW" Width="100"></syncfusion:RibbonMenuItem>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:Ribbon.TabPanelItem>

<syncfusion:RibbonButton SizeForm="Small" Label="Help"/>

</syncfusion:Ribbon.TabPanelItem>

</syncfusion:Ribbon>

{% endhighlight %}

Create instance of RibbonButton and assign it to TabPanelItem property of Ribbon.

{% highlight c# %}

[C#]

RibbonButton _RibbonButton = new RibbonButton() { Label="Help"};

_Ribbon1.TabPanelItem = _RibbonButton;

{% endhighlight %}

![](RibbonTabPanelItem_images/RibbonTabPanelItem_img1.jpeg)


