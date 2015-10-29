---
layout: post
title: RibbonTextBox
description: RibbonTextBox
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonTextBox

RibbonTextBox control provide similar setoff functionalities like normal TextBox control in Ribbon Instance. 

The following code example illustrates How to use RibbonTextBox control in Ribbon instance.

You can use RibbonTextBox in Ribbon by add it inside the RibbonBar element.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_RibbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_RibbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonTextBox  Width="140" Text="RibbonTextBox"></syncfusion:RibbonTextBox>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

Create instance of RibbonTextBox and add it to RibbonBar Items.

{% highlight c# %}

[C#]

RibbonTextBox _RibbonTextBox = new RibbonTextBox(){Text = "RibbonTextBox"};

_RibbonBar2.Items.Add(_RibbonTextBox);

{% endhighlight %}

![](RibbonTextBox_images/RibbonTextBox_img1.jpeg)


