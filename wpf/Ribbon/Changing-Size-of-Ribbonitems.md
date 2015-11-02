---
layout: post
title: Changing Size of Ribbon items
description: Changing Size of Ribbon items
platform: wpf
control: Ribbon
documentation: ug
---
# Changing Size of Ribbon items

`SizeForm` is used to set the size of the Ribbon items that are added inside the **Ribbon** control.

Possible values of `SizeForm` are Large, Small and ExtraSmall.

## List of controls which support SizeForm

* RibbonButton
* DropDownButton
* SplitButton

The code to set sizeform for the above controls is illustrated below

{% highlight xml %}

[XAML]

<syncfusion:Ribbon  VerticalAlignment="Top" >

<syncfusion:RibbonTab  Caption="Home" IsChecked="True">

<syncfusion:RibbonBar Header="RibbonButton">

<syncfusion:RibbonButton   SizeForm="Large" Label="Reply"/>

<syncfusion:RibbonButton  SizeForm="Small" />

<syncfusion:ButtonPanel>

<syncfusion:RibbonButton  SizeForm="ExtraSmall" Label="ReplyAll"/>

</syncfusion:ButtonPanel>   

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="SplitButton">

<syncfusion:SplitButton   SizeForm="Large" Label="NewItem"/>

<syncfusion:SplitButton   SizeForm="Small" Label="CleanUp"/>

<syncfusion:ButtonPanel>

<syncfusion:SplitButton  SizeForm="ExtraSmall" />   

</syncfusion:ButtonPanel>   

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="DropDownButton">

<syncfusion:DropDownButton SizeForm="Large" Label="Delete"/>

<syncfusion:DropDownButton SizeForm="Small" Label="Junk"/>

<syncfusion:ButtonPanel>

<syncfusion:DropDownButton  SizeForm="ExtraSmall" />

</syncfusion:ButtonPanel>  

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="Send/Receive" IsChecked="False"/>

</syncfusion:Ribbon>



{% endhighlight %}

![](ChangingSizeofRibbonitems_images/ChangingSizeofRibbonitems_img1.jpeg)


