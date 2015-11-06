---
layout: post
title: SplitButton | Ribbon | WPF | Syncfusion
description: SplitButton
platform: wpf
control: Ribbon
documentation: ug
---
# SplitButton

SplitButton will act as both normal Button as well as DropDownButton. It allow to click the button directly by clicking the upper part of the button and also it display list of items while press the below part of the button.

## Adding Item to the control

DropDownMeuItem can be added as items to SplitButton.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Name="_ribbonTab1" Caption="HOME"  IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar1" Header="RibbonBar1">

<syncfusion:RibbonButton   Label="Cut"/>

<syncfusion:RibbonButton   Label="Copy"/>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Name="_ribbonBar2" Header="RibbonBar2">

<syncfusion:SplitButton Label="Chart">

<syncfusion:DropDownMenuItem Header="PieChart"/>

<syncfusion:DropDownMenuItem Header="ColumnChart"/>

</syncfusion:SplitButton>

<syncfusion:SplitButton Label="Table"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="EDIT"  IsChecked="False"/>

<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>

</syncfusion:Ribbon>

{% endhighlight %}

You can add Items to SplitButton by create instance of `DropDownMenuItem` and add it to SplitButton.

{% highlight c# %}

[C#]

SplitButton _splitbutton = new SplitButton() { Label = "Chart" };

DropDownMenuItem _dropDownMenuItem1 = new DropDownMenuItem() { Header = "PieChart" };

DropDownMenuItem _dropDownMenuItem2 = new DropDownMenuItem() { Header = "ColumnChart" };

_splitbutton.Items.Add(_dropDownMenuItem1);

_splitbutton.Items.Add(_dropDownMenuItem2);

_RibbonBar2.Items.Add(_splitbutton);

{% endhighlight %}

![](SplitButton_images/SplitButton_img1.jpeg)


## Three types of SizeForm

SplitButton have three types of size forms. You can set size forms using `SizeForm` Property.

The following code example illustrates different size forms of SplitButton in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:SplitButton SizeForm="Large" Label="Large"/>

<syncfusion:SplitButton SizeForm="Small" Label="Small"/>

<syncfusion:SplitButton SizeForm="ExtraSmall" Label="ExtraSmall"/>

{% endhighlight %}

{% highlight c# %}

[C#]

SplitButton _splitbutton1 = new SplitButton(){Label = "Large",SizeForm= SizeForm.Large};

SplitButton _splitbutton2 = new SplitButton(){Label = "Small",SizeForm= SizeForm.Small};

SplitButton _splitbutton3 = new SplitButton(){Label = "ExtraSmall",SizeForm= SizeForm.ExtraSmall};

_ribbonBar2.Items.Add(_splitbutton1);

_ribbonBar2.Items.Add(_splitbutton2);

_ribbonBar2.Items.Add(_splitbutton3);

{% endhighlight %}

![](SplitButton_images/SplitButton_img2.jpeg)

