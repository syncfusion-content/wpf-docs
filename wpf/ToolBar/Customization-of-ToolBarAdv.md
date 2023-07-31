---
layout: post
title: Customization in WPF ToolBar control | Syncfusion
description: Learn here all about Customization support in Syncfusion WPF ToolBar (ToolBarAdv) control, its elements and more.
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Customization in WPF ToolBar (ToolBarAdv)

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

## Customizing Foreground

The [Foreground](https://learn.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?view=windowsdesktop-7.0) property of [ToolBarAdv](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ToolBarAdv.html) can be used to customize the floating ToolBar text foreground.

The following code illustrates how to set the value of the foreground property:

{% tabs %}

{% highlight XAML %}

   <shared:ToolBarManager x:Name="toolBarManager">
        <shared:ToolBarManager.TopToolBarTray>
            <shared:ToolBarTrayAdv VerticalAlignment="Top">
                <shared:ToolBarAdv ToolBarName="Standard" Foreground="Red">
                    <Button shared:ToolBarAdv.Label="New Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/NewDocumentHS.png" ToolTip="New">
                        <Image Source="Images/NewDocumentHS.png" Width="16" Height="16" />
                    </Button>
                    <Button  shared:ToolBarAdv.Label="Open Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/openHS.png" ToolTip="Open">
                        <Image Source="Images/openHS.png"  Width="16" Height="16"/>
                    </Button>
                    <Button  shared:ToolBarAdv.Label="Save Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/saveHS.png" ToolTip="Save">
                        <Image Source="Images/saveHS.png"  Width="16" Height="16"/>
                    </Button>
                    <Button  shared:ToolBarAdv.Label="Save Document" Height="22" Width="22" shared:ToolBarAdv.Icon="Images/saveAllHS.png" ToolTip="SaveAll">
                        <Image Source="Images/saveAllHS.png"  Width="16" Height="16"/>
                    </Button>
                    <shared:ToolBarItemSeparator  />
                    <Button  shared:ToolBarAdv.Label="Print Document"  Height="22" Width="22" shared:ToolBarAdv.Icon="Images/PrintHS.png" ToolTip="Print">
                        <Image Source="Images/PrintHS.png"  Width="16" Height="16"/>
                    </Button>
                </shared:ToolBarAdv>                   
            </shared:ToolBarTrayAdv>                
        </shared:ToolBarManager.TopToolBarTray>          
    </shared:ToolBarManager>

{% endhighlight %}

{% endtabs %}

![Setting floaitng toolbar text forecolor](Getting-Started-images/Floating-ToolBar-Forecolor.png)

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

  ![Setting theme to WPF ToolBarAdv](Getting-Started-images/Theme.png)

