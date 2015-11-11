---
layout: post
title: RibbonTextBox for Syncfusion's Ribbon control for WPF
description: RibbonTextBox for Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonTextBox

`RibbonTextBox` control provide similar set of functionalities like normal TextBox control in Ribbon Instance. 


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar2" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_ribbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonTextBox  Width="140" Text="RibbonTextBox"></syncfusion:RibbonTextBox>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonTextBox and add it to RibbonBar through code behind.

{% tabs %}

{% highlight C# %}

RibbonTextBox _ribbonTextBox = new RibbonTextBox(){Text = "RibbonTextBox"};

_ribbonBar2.Items.Add(_ribbonTextBox);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonTextBox As New RibbonTextBox() With {.Text = "RibbonTextBox"}

_ribbonBar2.Items.Add(_ribbonTextBox)

{% endhighlight %}
 
{% endtabs %}

![](RibbonTextBox_images/RibbonTextBox_img1.jpeg)


