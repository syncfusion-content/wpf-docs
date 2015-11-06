---
layout: post
title: DropDownButton | Ribbon | WPF | Syncfusion
description: DropDownButton
platform: wpf
control: Ribbon
documentation: ug
---
# DropDownButton

DropDownButton is a button control which contains a drop arrow. On clicking the DropDownButton, the menu items related to the button gets displayed in PopUp. These menu item can be added using `DropDownMenuItem`

## Creating DropDownMenuItem

DropDownMenuItem are the items with `Header` property. It can added to `SplitButton` and `DropDownButton`.

The following code example illustrates how to create DropDownMenuItem and add it to DropDownButton in Ribbon instance.

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

Create instance of `DropDownMenuItems` and add it to `DropDownButton` Items.

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


## Adding DropDownMenuItem to DropDownMenuGroup

In DropDownButton similar items can be grouped together and seperated from other menu items using `DropDownMenuGroup`.

The following code example illustrates how to add drop down MenuItems to `DropDownMenuGroup`

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


## Control can be created in three types of size

DropDownButton have three types of size forms. You can set size forms using `SizeForm` Property.

The following code example illustrates different size forms of DropDownButton in Ribbon instance.

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
