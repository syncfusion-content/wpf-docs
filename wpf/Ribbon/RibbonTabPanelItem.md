---
layout: post
title: Ribbon TabPanelItem | Ribbon | WPF | Syncfusion
description: Ribbon TabPanelItem
platform: wpf
control: Ribbon
documentation: ug
---
# Ribbon TabPanelItem

`RibbonTabPannelItem` can set in Ribbon to located below the close button of RibbonWindow.

The following code example illustrates how to use RibbonTabPannelItem control in Ribbon instance.

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar1">

<syncfusion:RibbonMenuItem  Header="NEW" Width="100"></syncfusion:RibbonMenuItem>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:Ribbon.TabPanelItem>

<syncfusion:RibbonButton SizeForm="Small" Label="Help"/>

</syncfusion:Ribbon.TabPanelItem>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonButton and assign it to TabPanelItem property of Ribbon.

{% tabs %}

{% highlight C# %}

RibbonButton _ribbonButton = new RibbonButton() { Label="Help"};

_ribbon.TabPanelItem = _ribbonButton;

{% endhighlight %}

{% highlight VB %}

Dim _ribbonButton As New RibbonButton() With {.Label="Help"}

_ribbon.TabPanelItem = _ribbonButton

{% endhighlight %}
 
{% endtabs %}

![](RibbonTabPanelItem_images/RibbonTabPanelItem_img1.jpeg)


