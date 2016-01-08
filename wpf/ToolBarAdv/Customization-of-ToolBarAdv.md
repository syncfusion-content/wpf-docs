---
layout: post
title: Customization of ToolBarAdv
description: Describes about customization of ToolBarAdv
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Customization of ToolBarAdv

## Customizing Floating ToolBarAdv

The floating ToolBarAdv can be customized using the FloatingToolBarAdvStyle property of ToolBarManager.

{% tabs %}

{% highlight XAML %}
<syncfusion:ToolBarManager FloatingToolBarStyle="{StaticResource toolstyle}" >

<syncfusion:ToolBarTrayAdv  >

<syncfusion:ToolBarAdv x:Name="Tooladv" ToolBarName="Standard"      >

<Button syncfusion:ToolBarAdv.Icon="Images\NewDocumentHS.png" >

<Image Source="Images\NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\openHS.png" Width="16" Height="16" />

</Button>

<Button>

<Image Source="Images\InsertPictureHS.png" Width="16" Height="16" syncfusion:ToolBarAdv.IsAvailable="False"/>

</Button>

<Button>

<Image Source="Images\InsertHyperlinkHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\TableHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>

</syncfusion:ToolBarManager>



{% endhighlight %}

{% endtabs %}

## Customize FrameworkElement’s Style

In ToolBarAdv, style for FrameworkElement will be picked from a ResourceDictionary assigned in the ControlsResourceDictionary property of ToolBarAdv.

{% tabs %}

{% highlight C# %}

ToolBarAdv toolBar = new ToolBarAdv();

toolBar.ControlsResourceDictionary = new ResourceDictionary()

{

Source = new Uri("ControlsResouce.xaml", UriKind.RelativeOrAbsolute)

};

}



{% endhighlight %}

{% endtabs %}

## Visual Styles

SkinManager provides rich and professional look and feel UI for the ToolBarAdv control. Some of the available visual style are as follows:

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Metro
* Transparent

For example, the Blend style applied for the ToolBarAdv control shows in the following code example:

{% tabs %}

{% highlight XAML %}
<Window x:Class="WpfApplication4.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

Title="MainWindow" Height="350" Width="525" syncfusion:SkinStorage.VisualStyle="Blend">

<Grid x:Name="Grid1">

<syncfusion:ToolBarManager  >

<syncfusion:ToolBarTrayAdv >

<syncfusion:ToolBarAdv x:Name="Tooladv" ToolBarName="Standard" >

<Button syncfusion:ToolBarAdv.Icon="Images\NewDocumentHS.png" >

<Image Source="Images\NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button>

<Image Source="Images\openHS.png" Width="16" Height="16" />

</Button>

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

</syncfusion:ToolBarManager>

</Grid>

</Window>



{% endhighlight %}

{% endtabs %}

![](Customization-of-ToolBarAdv-images/Customization-of-ToolBarAdv-img1.jpeg)


