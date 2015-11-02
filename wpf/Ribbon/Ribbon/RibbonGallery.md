---
layout: post
title: RibbonGallery
description: ribbongallery
platform: wpf
control: Ribbon
documentation: ug
---
## RibbonGallery

### Visual Mode

RibbonGallery has two visual modes. Visual Mode of RibbonGallery is set by VisualMode property of RibbonGallery.

* In the DropDown mode, the RibbonGallery control is displayed like a DropDown control
* In the InRibbon mode, it is displayed as a normal gallery control in the ribbon.

The following code example illustrates How to set VisualMode for RibbonGallery control in Ribbon instance.

InRibbon mode

{% highlight xml %}

[XAML]


<syncfusion:RibbonGallery Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png"/>



{% endhighlight %}

![](RibbonGallery_images/RibbonGallery_img1.jpeg)


DropDown Mode

{% highlight xml %}

[XAML]

<syncfusion:RibbonGallery VisualMode="DropDown" Label="RibbonGallery" LargeIcon="Word.png" >



{% endhighlight %}

![](RibbonGallery_images/RibbonGallery_img2.jpeg)


### Ribbon Gallery item

The following code example illustrates how to add RibbonGalleryItem to RibbonGallery control in Ribbon instance.

You can add items in RibbonGallery by using RibbonGalleryItem element inside the RibbonGallery.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">          

<syncfusion:RibbonTab Caption="HOME" IsChecked="False"/>                

<syncfusion:RibbonTab IsChecked="True" Caption="DESIGN">

<syncfusion:RibbonBar Width="250" Header="RibbonBar">

<syncfusion:RibbonGallery Name="_RibbonGallery" Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png" >

<syncfusion:RibbonGalleryItem>

<Image Source="OrangeLarge.png"/>

</syncfusion:RibbonGalleryItem>

<syncfusion:RibbonGalleryItem  >

<Image Source="BlueLarge.png"/>

</syncfusion:RibbonGalleryItem>

</syncfusion:RibbonGallery>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

You can add items in RibbonGallery dynamically by creating instance of RibbonGalleryItem and add it to RibbonGallery Items.

{% highlight c# %}

[C#]

Image _Image1 = new Image() { Source =new BitmapImage(new Uri(@"OrangeLarge.png", UriKind.RelativeOrAbsolute)) };

Image _Image2 = new Image() { Source = new BitmapImage(new Uri(@"BlueLarge.png", UriKind.RelativeOrAbsolute)) };

RibbonGalleryItem _RibbonGalleryItem = new RibbonGalleryItem(){Content=_Image1};

RibbonGalleryItem _RibbonGalleryItem1 = new RibbonGalleryItem() { Content = _Image2 };

_RibbonGallery.Items.Add(_RibbonGalleryItem);

_RibbonGallery.Items.Add(_RibbonGalleryItem1);



{% endhighlight %}

![](RibbonGallery_images/RibbonGallery_img3.jpeg)


### Ribbon Gallery group

Ribbon Gallery Group is a collection of Ribbon Gallery Items. Ribbon Gallery Groups are used to group the items in the Ribbon Gallery control based on some classifications.

**Gallery** **filter**

It is must, add GalleryGroupFilters to RibbonGallery control, a particular RibbonGalleryGroup gets displayed. FilterIndexes property is used to specify the indexes of the filters.

The following code example illustrates How to use GalleryGroup and GalleryFilters property of RibbonGallery control in Ribbon instance.

{% highlight xml %}

[XAML]

<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">                      

<syncfusion:RibbonTab Caption="HOME" IsChecked="False"/>               

<syncfusion:RibbonTab IsChecked="False" Caption="DESIGN">

<syncfusion:RibbonBar Width="250" Header="RibbonBar">

<syncfusion:RibbonGallery Name="_RibbonGallery" Width="230" VisualMode="DropDown" Label="RibbonGallery" LargeIcon="Word.png" >                        

<syncfusion:RibbonGallery.GalleryFilters>

<syncfusion:RibbonGalleryFilter Label="All"/>

<syncfusion:RibbonGalleryFilter Label="Group 1"/>

<syncfusion:RibbonGalleryFilter Label="Group 2"/>

</syncfusion:RibbonGallery.GalleryFilters>

<syncfusion:RibbonGallery.GalleryGroups>

<syncfusion:RibbonGalleryGroup Name="_RibbonGalleryGroup" Label="Group 1">

<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem1" Margin="5">

<Image Source="OrangeLarge.png"/>

</syncfusion:RibbonGalleryItem>

<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem2" >

<Image Source="BlueLarge.png"/>

</syncfusion:RibbonGalleryItem>                      

</syncfusion:RibbonGalleryGroup>

<syncfusion:RibbonGalleryGroup  Name="_RibbonGalleryGroup1"  Label="Group 2">

<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem3"  Margin="5">

<Image Source="GreenLarge.png"/>

</syncfusion:RibbonGalleryItem>

<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem4"  >

<Image Source="PinkLarge.png" />

</syncfusion:RibbonGalleryItem>

</syncfusion:RibbonGalleryGroup>

</syncfusion:RibbonGallery.GalleryGroups>                    </syncfusion:RibbonGallery>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}

![](RibbonGallery_images/RibbonGallery_img4.jpeg)


### Adding custom menu items

In the expanded Gallery items (in both the Visual Mode), can add custom menu items to the bottom of the Ribbon Gallery control, using the MenuItem property of RibbonGallery.

The following code example illustrates How to add custom menu items to RibbonGallery control in Ribbon instance.

{% highlight xml %}

[XAML]



<syncfusion:Ribbon Name="_Ribbon1" HorizontalAlignment="Stretch" VerticalAlignment="Top">           

<syncfusion:RibbonTab Caption="HOME" IsChecked="True"/>

<syncfusion:RibbonTab IsChecked="False" Caption="DESIGN">

<syncfusion:RibbonBar Width="250" Header="RibbonBar">

<syncfusion:RibbonGallery Name="_RibbonGallery" Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png" >

<syncfusion:RibbonGalleryItem  Margin="5">

<Image Source="OrangeLarge.png"/>

</syncfusion:RibbonGalleryItem>

<syncfusion:RibbonGalleryItem  Margin="5">

<Image Source="PinkLarge.png"/>

</syncfusion:RibbonGalleryItem>

<syncfusion:RibbonGallery.MenuItems>

<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-1"/>

<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-2"/>

<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-3"/>

</syncfusion:RibbonGallery.MenuItems>              

</syncfusion:RibbonGallery>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>



{% endhighlight %}

Custom Menu items of RibbonGallery dynamically added by creating instance of RibbonButton and add it to MenuItems property of RibbonGallery. You can use SplitButton or MenuButton or SimpleMenuButton instead of RibbonButton.

{% highlight c# %}

[C#]



RibbonButton _RibbonButton1 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-1" };

RibbonButton _RibbonButton2 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-2" };

RibbonButton _RibbonButton3 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-3" };

_RibbonGallery.MenuItems.Add(_RibbonButton1);

_RibbonGallery.MenuItems.Add(_RibbonButton2);

_RibbonGallery.MenuItems.Add(_RibbonButton3);



{% endhighlight %}

![](RibbonGallery_images/RibbonGallery_img5.jpeg)

