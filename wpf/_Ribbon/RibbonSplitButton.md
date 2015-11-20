---
layout: post
title: SplitButton for Syncfusion's Ribbon control for WPF
description: SplitButton for Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# SplitButton

SplitButton can perform like both normal Button as well as DropDownButton. It allow to click the button directly by clicking the upper part of the button and also it display list of items while click on the arrow.


## Add DropDownMenuItem

DropDownMenuItem are the items with `Header` property that is used to set header.


{% tabs %}

{% highlight XAML %}

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

{% endtabs %}

Create instance of `DropDownMenuItem` and add it to SplitButton in code behind.

{% tabs %}

{% highlight C# %}

SplitButton _splitbutton = new SplitButton() { Label = "Chart" };

DropDownMenuItem _dropDownMenuItem1 = new DropDownMenuItem() { Header = "PieChart" };

DropDownMenuItem _dropDownMenuItem2 = new DropDownMenuItem() { Header = "ColumnChart" };

_splitbutton.Items.Add(_dropDownMenuItem1);

_splitbutton.Items.Add(_dropDownMenuItem2);

_RibbonBar2.Items.Add(_splitbutton);

{% endhighlight %}

{% highlight VB %}

Dim _splitbutton As New SplitButton() With {.Label = "Chart"}

Dim _dropDownMenuItem1 As New DropDownMenuItem() With {.Header = "PieChart"}

Dim _dropDownMenuItem2 As New DropDownMenuItem() With {.Header = "ColumnChart"}

_splitbutton.Items.Add(_dropDownMenuItem1)

_splitbutton.Items.Add(_dropDownMenuItem2)

_RibbonBar2.Items.Add(_splitbutton)

{% endhighlight %}

{% endtabs %}

![](SplitButton_images/SplitButton_img1.jpeg)


## Set various sizes for DropDownButton

SplitButton have three types of size forms. You can set size forms using its `SizeForm` Property.


{% tabs %}

{% highlight XAML %}

<syncfusion:SplitButton SizeForm="Large" Label="Large"/>

<syncfusion:SplitButton SizeForm="Small" Label="Small"/>

<syncfusion:SplitButton SizeForm="ExtraSmall" Label="ExtraSmall"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SplitButton _splitbutton1 = new SplitButton(){Label = "Large",SizeForm= SizeForm.Large};

SplitButton _splitbutton2 = new SplitButton(){Label = "Small",SizeForm= SizeForm.Small};

SplitButton _splitbutton3 = new SplitButton(){Label = "ExtraSmall",SizeForm= SizeForm.ExtraSmall};

_ribbonBar2.Items.Add(_splitbutton1);

_ribbonBar2.Items.Add(_splitbutton2);

_ribbonBar2.Items.Add(_splitbutton3);

{% endhighlight %}

{% highlight VB %}

Dim _splitbutton1 As New SplitButton() With {
	.Label = "Large",
	.SizeForm= SizeForm.Large
}

Dim _splitbutton2 As New SplitButton() With {
	.Label = "Small",
	.SizeForm= SizeForm.Small
}

Dim _splitbutton3 As New SplitButton() With {
	.Label = "ExtraSmall",
	.SizeForm= SizeForm.ExtraSmall
}

_ribbonBar2.Items.Add(_splitbutton1)

_ribbonBar2.Items.Add(_splitbutton2)

_ribbonBar2.Items.Add(_splitbutton3)

{% endhighlight %}

{% endtabs %}

![](SplitButton_images/SplitButton_img2.jpeg)

