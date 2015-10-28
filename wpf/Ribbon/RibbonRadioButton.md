---
layout: post
title: RibbonRadioButton
description: RibbonRadioButton
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonRadioButton

**RibbonRadioButton** control is used to select options among a group in **Ribbon** instance. 

The following code example illustrates How to use **RibbonRadioButton** control in **Ribbon** instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_RibbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_RibbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar  Name="_RibbonBar2" Width="150" Header="RibbonBar2">

<syncfusion:RibbonRadioButton GroupName="Group1"  Width="140" Content="ReadOnly" IsChecked="True"></syncfusion:RibbonRadioButton>

<syncfusion:RibbonRadioButton GroupName="Group1"  Width="140" Content="WriteOnly" ></syncfusion:RibbonRadioButton>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

</syncfusion:Ribbon>



{% endhighlight %}

Create instance of RibbonRadioButton and add it to RibbonBar Items.

{% highlight c# %}

[C#]

RibbonRadioButton _RibbonRadioButton = new RibbonRadioButton(){Content = "ReadOnly", IsChecked = true , GroupName = "Group1"};      

RibbonRadioButton _RibbonRadioButton1 = new RibbonRadioButton(){Content = "WriteOnly", GroupName = "Group1"};

_RibbonBar2.Items.Add(_RibbonRadioButton);

_RibbonBar2.Items.Add(_RibbonRadioButton1);



{% endhighlight %}

![](RibbonRadioButton_images/RibbonRadioButton_img1.jpeg)


