---
layout: post
title: RibbonListBox and its items for Syncfusion's Ribbon control for WPF
description: RibbonListBox and its items for Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonListBox

`RibbonListBox` control is used to display a list of items in a Ribbon. It accepts any type of content as RibbonListBox items but `ListBoxItem` by default.


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_ribbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonListBox  Width="140" >

<ListBoxItem Content="Office2003Theme"/>

<ListBoxItem Content="Office2007Theme"/>

<ListBoxItem Content="Office2010Theme"/>

</syncfusion:RibbonListBox>                

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Create instance of RibbonListBox and add it to RibbonBar through code behind.

{% tabs %}

{% highlight C# %}

RibbonListBox _ribbonListBox = new RibbonListBox();

ListBoxItem item1 = new ListBoxItem(){Content = "Office2003Theme"};

ListBoxItem item2 = new ListBoxItem(){Content = "Office2007Theme"};

ListBoxItem item3= new ListBoxItem(){Content = "Office2010Theme"};

_ribbonListBox.Items.Add(item1);

_ribbonListBox.Items.Add(item2);

_ribbonListBox.Items.Add(item3);

_ribbonBar2.Items.Add(_ribbonListBox);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonListBox As New RibbonListBox()

Dim item1 As New ListBoxItem() With {.Content = "Office2003Theme"}

Dim item2 As New ListBoxItem() With {.Content = "Office2007Theme"}

Dim item3 As New ListBoxItem() With {.Content = "Office2010Theme"}

_ribbonListBox.Items.Add(item1)

_ribbonListBox.Items.Add(item2)

_ribbonListBox.Items.Add(item3)

_ribbonBar2.Items.Add(_ribbonListBox)

{% endhighlight %}

{% endtabs %}

![](RibbonListBox_images/RibbonListBox_img1.jpeg)


