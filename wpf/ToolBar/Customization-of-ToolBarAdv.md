---
layout: post
title: Customization | ToolBarAdv | Wpf | Syncfusion
description: This section explain about how to customize the appearance and set different themes for Syncfusion WPF ToolBarAdv. 
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

## Theme

ToolBarAdv supports various built-in themes. Refer to the below links to apply themes for the ToolBarAdv,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)
