---
layout: post
title: RibbonCheckBox | Ribbon | WPF | Syncfusion
description: RibbonCheckBox
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonCheckBox

`RibbonCheckBox` is used to select or unselect options. It provides similar set of functionalities like normal CheckBox control in Ribbon.

The following code example illustrates how to use `RibbonCheckBox` control in Ribbon instance.

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  >

<syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton Label="Cut"/>

<syncfusion:RibbonButton Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Name="_ribbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonCheckBox  Width="140" Content="SelectAll" IsChecked="True"></syncfusion:RibbonCheckBox>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonCheckBox and add it to RibbonBar Items.

{% tabs %}

{% highlight C# %}

RibbonCheckBox _ribbonCheckBox = new RibbonCheckBox(){Content = "SelectAll", IsChecked=true };

_ribbonBar2.Items.Add(_ribbonCheckBox);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonCheckBox As New RibbonCheckBox() With {
	.Content = "SelectAll",
	.IsChecked=True
}

_ribbonBar2.Items.Add(_ribbonCheckBox)

{% endhighlight %}

{% endtabs %}

![](RibbonCheckBox_images/RibbonCheckBox_img1.jpeg)


