---
layout: post
title: Ribbon Separator	
description: Ribbon Separator	
platform: wpf
control: Ribbon
documentation: ug
---
## Ribbon Separator	

RibbonSeperator used to separate the similar setoff Ribbon elements in Ribbon instance. It is used in RibbonBar to group out RibbonButtons according to their purpose. 

The following code example illustrates How to set RibbonSeperator in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Caption="HOME" IsChecked="False">

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

You can add RibbonSeperator dynamically create instance of RibbonSeperator and add it to Items of in which element you want to use separator.

{% highlight c# %}

[C#]

RibbonSeparator _RibbonSeparator = new RibbonSeparator();

RibbonButton _RibbonButton = new RibbonButton() { Label = "Cut" };

RibbonButton _RibbonButton1 = new RibbonButton() { Label = "Copy" };

RibbonButton _RibbonButton2 = new RibbonButton() { Label = "Paste" };

_RibbonBar.Items.Add(_RibbonSeparator);

_RibbonBar.Items.Add(_RibbonButton);

_RibbonBar.Items.Add(_RibbonButton1);

_RibbonBar.Items.Add(_RibbonButton2);

{% endhighlight %}

![](RibbonSeparator_images/RibbonSeparator_img1.jpeg)


