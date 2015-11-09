---
layout: post
title: DropDownButton and its items for Syncfusion's Ribbon control for WPF
description: DropDownButton and its items for Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonDropDownButton

DropDownButton appears like normal button that contains a drop arrow. It displays some items, while click on it. It accepts `DropDownMenuItem` as its children.

## Add DropDownMenuItem

DropDownMenuItem are the items with `Header` property that is used to set header.


{% tabs %}

{% highlight XAML %}


<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Caption="HOME" >

<syncfusion:RibbonBar Name="_ribbonBar1">

<syncfusion:DropDownButton Label="View"/>

<syncfusion:DropDownButton Label="LayOut"/>

<syncfusion:DropDownButton Name="_dropDownButton" SizeForm = "Large" Width="100" Label="File" >

<syncfusion:DropDownMenuItem Header="New"></syncfusion:DropDownMenuItem>

<syncfusion:DropDownMenuItem Header="Open"></syncfusion:DropDownMenuItem>

</syncfusion:DropDownButton>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}

{% endtabs %}

Create instance of `DropDownMenuItems` and add it to DropDownButton Items in code behind.

{% tabs %}

{% highlight C# %}


DropDownMenuItem _dropDownMenuItem1 = new DropDownMenuItem() {Header="New" };

DropDownMenuItem _dropDownMenuItem2 = new DropDownMenuItem() { Header = "Open" };

_dropDownButton.Items.Add(_dropDownMenuItem1);

_dropDownButton.Items.Add(_dropDownMenuItem2);



{% endhighlight %}

{% highlight VB %}

Dim _dropDownMenuItem1 As New DropDownMenuItem() With {.Header="New"}

Dim _dropDownMenuItem2 As New DropDownMenuItem() With {.Header = "Open"}

_dropDownButton.Items.Add(_dropDownMenuItem1)

_dropDownButton.Items.Add(_dropDownMenuItem2)


{% endhighlight %}

{% endtabs %}


![](DropDownButton_images/DropDownButton_img1.jpeg)


## Add DropDownMenuItem to DropDownMenuGroup

In DropDownButton, similar items can be grouped together and seperated from other menu items using `DropDownMenuGroup`.


{% tabs %}

{% highlight XAML %}


<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">

<syncfusion:RibbonTab Caption="HOME" IsChecked="True">

<syncfusion:RibbonBar Name="_ribbonBar">

<syncfusion:DropDownButton Label="View"/>

<syncfusion:DropDownButton Label="LayOut"/>

<syncfusion:DropDownButton Name="_dropDownButton" SizeForm = "Large" Width="100" Label="File" >

<syncfusion:DropDownMenuGroup Name="_dropDownMenuGroup1" Header="Group1">

<syncfusion:DropDownMenuItem Header="New"/>

<syncfusion:DropDownMenuItem Header="Open"/>                            

</syncfusion:DropDownMenuGroup>

<syncfusion:DropDownMenuGroup Name="_dropDownMenuGroup2" Header="Group2">

<syncfusion:DropDownMenuItem Header="Cut"/>

<syncfusion:DropDownMenuItem Header="Copy"/>                      

</syncfusion:DropDownMenuGroup>

</syncfusion:DropDownButton>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

<syncfusion:RibbonTab IsChecked="False" Caption="DESIGN"/>

</syncfusion:Ribbon>



{% endhighlight %}

{% endtabs %}

Create instance of `DropDownMenuItem` and add it to `DropDownMenuGroup` Items.

{% tabs %}

{% highlight C# %}


DropDownMenuItem _dropDownMenuItem1 = new DropDownMenuItem() { Header = "New" };

DropDownMenuItem _dropDownMenuItem2 = new DropDownMenuItem() { Header = "Open" };

DropDownMenuItem _DropDownMenuItem3 = new DropDownMenuItem() { Header = "Cut" };

DropDownMenuItem _DropDownMenuItem4 = new DropDownMenuItem() { Header = "Copy" };

_dropDownMenuGroup1.Items.Add(_dropDownMenuItem1);

_dropDownMenuGroup1.Items.Add(_dropDownMenuItem2);

_dropDownMenuGroup2.Items.Add(_dropDownMenuItem3);

_dropDownMenuGroup2.Items.Add(_dropDownMenuItem4);



{% endhighlight %}

{% highlight VB %}


Dim _dropDownMenuItem1 As New DropDownMenuItem() With {.Header = "New"}

Dim _dropDownMenuItem2 As New DropDownMenuItem() With {.Header = "Open"}

Dim _DropDownMenuItem3 As New DropDownMenuItem() With {.Header = "Cut"}

Dim _DropDownMenuItem4 As New DropDownMenuItem() With {.Header = "Copy"}

_dropDownMenuGroup1.Items.Add(_dropDownMenuItem1)

_dropDownMenuGroup1.Items.Add(_dropDownMenuItem2)

_dropDownMenuGroup2.Items.Add(_dropDownMenuItem3)

_dropDownMenuGroup2.Items.Add(_dropDownMenuItem4)


{% endhighlight %}


{% endtabs %}

![](DropDownButton_images/DropDownButton_img2.jpeg)


## Set various sizes for DropDownButton

DropDownButton have three types of size forms. You can set size forms using its `SizeForm` Property.


{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonBar Name="_ribbonBar2">

<syncfusion:DropDownButton SizeForm = "Large" Label="Large" />

<syncfusion:DropDownButton SizeForm = "Small" Label="Small" />

<syncfusion:DropDownButton SizeForm = "ExtraSmall" Label="ExtraSmall" />

</syncfusion:RibbonBar>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}


DropDownButton _dropDownButton1 = new DropDownButton() { Label = "Large", SizeForm = SizeForm.Large };

DropDownButton _dropDownButton2 = new DropDownButton() { Label = "Small", SizeForm = SizeForm.Small };

DropDownButton _dropDownButton3 = new DropDownButton() { Label = "ExtraSmall", SizeForm = SizeForm.ExtraSmall };

_ribbonBar2.Items.Add(_dropDownButton1);

_ribbonBar2.Items.Add(_dropDownButton2);

_ribbonBar2.Items.Add(_dropDownButton3);



{% endhighlight %}

{% highlight VB %}

Dim _dropDownButton1 As New DropDownButton() With {
	.Label = "Large",
	.SizeForm = SizeForm.Large
}

Dim _dropDownButton2 As New DropDownButton() With {
	.Label = "Small",
	.SizeForm = SizeForm.Small
}

Dim _dropDownButton3 As New DropDownButton() With {
	.Label = "ExtraSmall",
	.SizeForm = SizeForm.ExtraSmall
}

_ribbonBar2.Items.Add(_dropDownButton1)

_ribbonBar2.Items.Add(_dropDownButton2)

_ribbonBar2.Items.Add(_dropDownButton3)


{% endhighlight %}

{% endtabs %}

![](DropDownButton_images/DropDownButton_img3.jpeg)
