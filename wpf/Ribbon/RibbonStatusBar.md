---
layout: post
title: RibbonStatusBar
description: RibbonStatusBar
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonStatusBar

RibbonStatusBar control is added to a RibbonWindow to display the current status of the application or document like in Microsoft Office.

The following code example illustrates How to use RibbonStatusBar control in RibbonWindow.

{% highlight xml %}

[XAML]

<syncfusion:RibbonWindow.StatusBar>

<syncfusion:RibbonStatusBar>

<WrapPanel>

<TextBlock Text="Ready" Margin="10,0,0,0" Foreground="AntiqueWhite"/>

<TextBlock Text="Page No 1" Margin="20,0,0,0" Foreground="AntiqueWhite"/>

</WrapPanel>

</syncfusion:RibbonStatusBar>

</syncfusion:RibbonWindow.StatusBar>

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch"  VerticalAlignment="Top">

<!--Add RibbonTab and add its Items here-->

</syncfusion:Ribbon>

{% endhighlight %}

Create instance of StatusBar and assign it to RibbonStatusBar property of RibbonWindow.

{% highlight c# %}

[C#]

RibbonStatusBar _RibbonStatusBar = new RibbonStatusBar();

WrapPanel _WrapPanel = new WrapPanel();

Label _TextBlock = new Label() { Content = "Ready", Foreground = Brushes.WhiteSmoke };

Label _TextBlock1 = new Label() { Content = "Page No 1", Foreground = Brushes.WhiteSmoke };

_WrapPanel.Children.Add(_TextBlock);

_WrapPanel.Children.Add(_TextBlock1);

_RibbonStatusBar.Items.Add(_WrapPanel);

_RibbonWindow.StatusBar = _RibbonStatusBar;

{% endhighlight %}

![](RibbonStatusBar_images/RibbonStatusBar_img1.jpeg)


