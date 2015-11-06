---
layout: post
title: Ribbon Separator | Ribbon | WPF | Syncfusion
description: Ribbon Separator	
platform: wpf
control: Ribbon
documentation: ug
---
# Ribbon Separator	

`RibbonSeperator` used to separate the similar set of Ribbon elements in Ribbon instance. It is used in RibbonBar to group out RibbonButtons according to their purpose. 

The following code example illustrates how to set RibbonSeperator in Ribbon instance.

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Caption="HOME" IsChecked="True">

<syncfusion:RibbonBar>

<syncfusion:RibbonButton Label="New"/>

<syncfusion:RibbonButton Label="Open"/>

<syncfusion:RibbonButton Label="Save"/>

<syncfusion:RibbonSeparator/>

<syncfusion:RibbonButton Label="Cut"/>

<syncfusion:RibbonButton Label="Copy"/>

<syncfusion:RibbonButton Label="Paste"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab IsChecked="False" Caption="DESIGN"></syncfusion:RibbonTab>

</syncfusion:Ribbon>     

{% endhighlight %}

{% endtabs %}

RibbonSeperator instance can be added as item to the group of other items

{% tabs %}

{% highlight C# %}

RibbonSeparator _ribbonSeparator = new RibbonSeparator();

RibbonButton _ribbonButton1 = new RibbonButton() { Label = "New" };

RibbonButton _ribbonButton2 = new RibbonButton() { Label = "Open" };

RibbonButton _ribbonButton3 = new RibbonButton() { Label = "Save" };

RibbonButton _ribbonButton4 = new RibbonButton() { Label = "Cut" };

RibbonButton _ribbonButton5 = new RibbonButton() { Label = "Copy" };

RibbonButton _ribbonButton6 = new RibbonButton() { Label = "Paste" };

_ribbonBar.Items.Add(_ribbonButton1);

_ribbonBar.Items.Add(_ribbonButton2);

_ribbonBar.Items.Add(_ribbonButton3);

_ribbonBar.Items.Add(_ribbonSeparator);

_ribbonBar.Items.Add(_ribbonButton4);

_ribbonBar.Items.Add(_ribbonButton5);

_ribbonBar.Items.Add(_ribbonButton6);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonSeparator As New RibbonSeparator()

Dim _ribbonButton1 As New RibbonButton() With {.Label = "New"}

Dim _ribbonButton2 As New RibbonButton() With {.Label = "Open"}

Dim _ribbonButton3 As New RibbonButton() With {.Label = "Save"}

Dim _ribbonButton4 As New RibbonButton() With {.Label = "Cut"}

Dim _ribbonButton5 As New RibbonButton() With {.Label = "Copy"}

Dim _ribbonButton6 As New RibbonButton() With {.Label = "Paste"}

_ribbonBar.Items.Add(_ribbonButton1)

_ribbonBar.Items.Add(_ribbonButton2)

_ribbonBar.Items.Add(_ribbonButton3)

_ribbonBar.Items.Add(_ribbonSeparator)

_ribbonBar.Items.Add(_ribbonButton4)

_ribbonBar.Items.Add(_ribbonButton5)

_ribbonBar.Items.Add(_ribbonButton6)

{% endhighlight %}

{% endtabs %}

![](RibbonSeparator_images/RibbonSeparator_img1.jpeg)


