---
layout: post
title: RibbonStatusBar
description: RibbonStatusBar
platform: wpf
control: Ribbon
documentation: ug
---
# Ribbon StatusBar

RibbonStatusBar control is added to RibbonWindow to display the current status of the application or document similar in Microsoft Office.

The following code example illustrates how to use RibbonStatusBar control in RibbonWindow.

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

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch"  VerticalAlignment="Top">

<!--Add RibbonTab and add its Items here-->

</syncfusion:Ribbon>

{% endhighlight %}

Create instance of StatusBar and assign it to RibbonStatusBar property of RibbonWindow.

{% highlight c# %}

[C#]

RibbonStatusBar _ribbonStatusBar = new RibbonStatusBar();

WrapPanel _wrapPanel = new WrapPanel();

Label _textBlock1 = new Label() { Content = "Ready", Foreground = Brushes.WhiteSmoke };

Label _textBlock2 = new Label() { Content = "Page No 1", Foreground = Brushes.WhiteSmoke };

_wrapPanel.Children.Add(_textBlock1);

_wrapPanel.Children.Add(_textBlock2);

_ribbonStatusBar.Items.Add(_wrapPanel);

_ribbonWindow.StatusBar = _ribbonStatusBar;

{% endhighlight %}

![](RibbonStatusBar_images/RibbonStatusBar_img1.jpeg)


