---
layout: post
title: RibbonRadioButton | Ribbon | WPF | Syncfusion
description: RibbonRadioButton
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonRadioButton

RibbonRadioButton control is used to select options among a group in Ribbon instance. 

The following code example illustrates how to use RibbonRadioButton control in Ribbon instance.

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_ribbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonRadioButton GroupName="Group1"  Width="140" Content="ReadOnly" IsChecked="True"></syncfusion:RibbonRadioButton>

<syncfusion:RibbonRadioButton GroupName="Group1"  Width="140" Content="WriteOnly" ></syncfusion:RibbonRadioButton>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonRadioButton and add it to RibbonBar Items.

{% tabs %}

{% highlight C# %}

RibbonRadioButton _ribbonRadioButton1 = new RibbonRadioButton(){Content = "ReadOnly", IsChecked = true , GroupName = "Group1"};      

RibbonRadioButton _ribbonRadioButton2 = new RibbonRadioButton(){Content = "WriteOnly", GroupName = "Group1"};

_ribbonBar2.Items.Add(_ribbonRadioButton1);

_ribbonBar2.Items.Add(_ribbonRadioButton2);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonRadioButton1 As New RibbonRadioButton() With {
	.Content = "ReadOnly",
	.IsChecked = True,
	.GroupName = "Group1"
}

Dim _ribbonRadioButton2 As New RibbonRadioButton() With {
	.Content = "WriteOnly",
	.GroupName = "Group1"
}

_ribbonBar2.Items.Add(_ribbonRadioButton1)

_ribbonBar2.Items.Add(_ribbonRadioButton2)

{% endhighlight %}

{% endtabs %}

![](RibbonRadioButton_images/RibbonRadioButton_img1.jpeg)


