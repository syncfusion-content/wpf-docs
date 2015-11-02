---
layout: post
title: RibbonListBox
description: RibbonListBox
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonListBox

RibbonListBox control is used to display a list of items in a Ribbon instance. You can add any type of content as RibbonListBox items.

The following code example illustrates How to use RibbonListBox control in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  IsChecked="False">

<syncfusion:RibbonBar Name="_RibbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_RibbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonListBox  Width="140" >

<ComboBoxItem Content="Office2003Theme"/>

<ComboBoxItem Content="Office2007Theme"/>

<ComboBoxItem Content="Office2010Theme"/>

</syncfusion:RibbonListBox>                

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>



{% endhighlight %}

Create instance of RibbonListBox and add it to RibbonBar Items.

{% highlight c# %}

[C#]

RibbonListBox _RibbonListBox = new RibbonListBox();

ComboBoxItem Item = new ComboBoxItem(){Content = "Office2003Theme"};

ComboBoxItem Item1 = new ComboBoxItem(){Content = "Office2007Theme"};

ComboBoxItem Item2= new ComboBoxItem(){Content = "Office2010Theme"};

_RibbonBar2.Items.Add(Item);

_RibbonBar2.Items.Add(Item1);

_RibbonBar2.Items.Add(Item2);

_RibbonBar2.Items.Add(_RibbonListBox);



{% endhighlight %}

![](RibbonListBox_images/RibbonListBox_img1.jpeg)


