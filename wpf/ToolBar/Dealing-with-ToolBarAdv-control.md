---
layout: post
title: Dealing with ToolBarAdv control in WPF ToolBar control | Syncfusion
description: Learn here all about Dealing with ToolBarAdv control support in Syncfusion WPF ToolBar (ToolBarAdv) control and more.
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Dealing with ToolBarAdv control in WPF ToolBar (ToolBarAdv)

The following sections describe how to position, customize, and populate the items in a `ToolBarAdv`.

## Specifying the position of ToolBarAdv in a ToolBarTrayAdv

The position of the ToolBarAdv in the ToolBarTrayAdv can be specified using the `Band` and `BandIndex` properties. `Band` indicates the band in the ToolBarTrayAdv where the ToolBarAdv has to be placed. `BandIndex` indicates the order in which the ToolBarAdv is placed within the band.

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarTrayAdv >

<syncfusion:ToolBarAdv ToolBarName="Standard">

<Button syncfusion:ToolBarAdv.Icon="Images\NewDocumentHS.png">

<Image Source="Images\NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\openHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

<syncfusion:ToolBarAdv Band="1" ToolBarName="Extras">

<Button>

<Image Source="Images\InsertPictureHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\InsertHyperlinkHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\TableHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>



{% endhighlight %}

{% highlight C# %}
ToolBarTrayAdv tray = new ToolBarTrayAdv();

ToolBarAdv toolBar = new ToolBarAdv();

Button button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/NewDocumentHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/openHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

tray.ToolBars.Add(toolBar);

toolBar = new ToolBarAdv();

toolBar.Band = 1;

button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/InsertPictureHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/InsertHyperlinkHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/TableHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

tray.ToolBars.Add(toolBar);

Grid1.Children.Add(tray);



{% endhighlight %}

{% endtabs %}

![Specifying the position of ToolBarAdv in a ToolBarTrayAdv](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img1.jpeg)

## ToolBarAdv with overflow items

When a ToolBarAdv control contains more items than can be displayed within its size, the additional items are listed in the overflow popup. On clicking the overflow button, the items are listed.

ToolBarAdv allows you to set the overflow mode for each item.

* `OverflowMode.Always` – the specified item will always be listed in the overflow popup.
* `OverflowMode.Never` – the specified item will never be moved to the overflow popup.
* `OverflowMode.AsNeeded` – the specified item will be listed in the overflow popup if required. This is the default value.

![Dealing-with-ToolBarAdv-control-img2](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img2.jpeg)


## Show or hide Gripper

The gripper can show and hide in ToolBarAdv using the `GripperVisibility` property. To collapse the gripper in the ToolBarAdv, set the GripperVisibility as Collapsed. By default its value is visibility.

Following code illustrates how to hide the gripper:

{% tabs %}

{% highlight XAML %}
<syncfusion:ToolBarAdv GripperVisibility="Collapsed"/>



{% endhighlight %}

{% highlight C# %}

ToolBarAdv toolBar = new ToolBarAdv();

toolBar.GripperVisibility = Visibility.Collapsed;





{% endhighlight %}

{% endtabs %}

![Dealing-with-ToolBarAdv-control-img3](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img3.jpeg)


## Orientation of ToolBarTrayAdv

ToolBarAdv provide two different orientation support such as Horizontal and Vertical. The desired orientation for ToolBarAdv can be changed using the `Orientation` property of ToolBarTrayAdv.

{% tabs %}

{% highlight xaml %}
<syncfusion:ToolBarTrayAdv Orientation="Vertical" >

<syncfusion:ToolBarAdv ToolBarName="Standard">

<Button syncfusion:ToolBarAdv.Icon="Images/NewDocumentHS.png">

<Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button >

<Image Source="Images/openHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

<syncfusion:ToolBarAdv Band="1" ToolBarName="Extras">

<Button >

<Image Source="Images/InsertPictureHS.png" Width="16" Height="16"/>

</Button>

<Button >

<Image Source="Images/InsertHyperlinkHS.png" Width="16" Height="16"/>

</Button>

<Button >

<Image Source="Images/TableHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>



{% endhighlight %}

{% highlight C# %}

ToolBarTrayAdv tray = new ToolBarTrayAdv();

tray.Orientation = Orientation.Vertical;

ToolBarAdv toolBar = new ToolBarAdv();

Button button = new Button();

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/InsertPictureHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/InsertHyperlinkHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

button = new Button();

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/TableHS.png", UriKind.RelativeOrAbsolute) } };

toolBar.Items.Add(button);

tray.ToolBars.Add(toolBar);

Grid1.Children.Add(tray);



{% endhighlight %}

{% endtabs %}

![Dealing-with-ToolBarAdv-control-img4](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img4.jpeg)


## Add or Remove buttons

ToolBarAdv provides the option to show or hide an item at runtime using the **Add or Remove** button. To enable it, set the `EnableAddRemoveButton` property of ToolBarAdv to `True`. The default value is `false`. Users can unselect the checkboxes of items to hide them from the toolbar.

### Adding an item to the Add or Remove button

Following code illustrates how to add an item in Add or Remove Buttons:

{% tabs %}

{% highlight xaml %}
<syncfusion:ToolBarTrayAdv>

<syncfusion:ToolBarAdv EnableAddRemoveButton="True" >

<Button syncfusion:ToolBarAdv.Label="New Document"
        syncfusion:ToolBarAdv.Icon="Images/NewDocumentHS.png">

<Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Open Document"
        syncfusion:ToolBarAdv.Icon="Images/openHS.png">

<Image Source="Images/openHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>



{% endhighlight %}

{% highlight C# %}
ToolBarTrayAdv tray = new ToolBarTrayAdv();

ToolBarAdv toolBar = new ToolBarAdv();

toolBar.EnableAddRemoveButton = true;

Button button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/NewDocumentHS.png", UriKind.RelativeOrAbsolute) } };

ToolBarAdv.SetLabel(button, "New Document");

ToolBarAdv.SetIcon(button, new BitmapImage() { UriSource = new Uri("Images/NewDocumentHS.png", UriKind.RelativeOrAbsolute) });

toolBar.Items.Add(button);

button = new Button();

button.Width = 16;

button.Height = 16;

button.Content = new Image() { Source = new BitmapImage() { UriSource = new Uri("Images/openHS.png", UriKind.RelativeOrAbsolute) } };

ToolBarAdv.SetLabel(button, "Open Document");

ToolBarAdv.SetIcon(button, new BitmapImage() { UriSource = new Uri("Images/openHS.png", UriKind.RelativeOrAbsolute) });

toolBar.Items.Add(button);

tray.ToolBars.Add(toolBar);

Grid1.Children.Add(tray);



{% endhighlight %}

{% endtabs %}

![Dealing-with-ToolBarAdv-control-img5](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img5.jpeg)


## Hiding the ToolBarItem

To hide a particular ToolBarItem, set the `IsAvailable` attached property of the ToolBarAdv to `False`. The default value is `True`.

{% tabs %}

{% highlight xaml %}

<syncfusion:ToolBarTrayAdv >

<syncfusion:ToolBarAdv x:Name="Tooladv" ToolBarName="Standard"    >

<Button syncfusion:ToolBarAdv.Icon="Images\NewDocumentHS.png" >

<Image Source="Images\NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\openHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\InsertPictureHS.png" Width="16"
       Height="16"syncfusion:ToolBarAdv.IsAvailable="False"/>

</Button>

<Button>

<Image Source="Images\InsertHyperlinkHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\TableHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>



{% endhighlight %}

{% endtabs %}

![Dealing-with-ToolBarAdv-control-img6](Dealing-with-ToolBarAdv-control-images/Dealing-with-ToolBarAdv-control-img6.jpeg)


