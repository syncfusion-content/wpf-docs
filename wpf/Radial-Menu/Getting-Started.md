---
layout: post
title: Getting Started with WPF Radial Menu control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Radial Menu (SfRadialMenu) control, its elements and more.
platform: wpf
control: SfRadialMenu 
documentation: ug
---

# Getting Started with WPF Radial Menu (SfRadialMenu)

Namespace : Syncfusion.Windows.Controls.Navigation 

Assembly : Syncfusion.SfRadialMenu.WPF (in Syncfusion.SfRadialMenu.WPF.dll) 

The following code sample shows how to create the RadialMenu from code-behind and XAML. 

{%tabs%}
{%highlight xaml%}




<Page xmlns:navigation="clr-namespace:Syncfusion.Windows.Controls.Navigation;assembly=Syncfusion.SfRadialMenu.Wpf"> 

     <Grid>

<navigation:SfRadialMenu> 

<navigation:SfRadialMenuItem Header="Bold"/>

<navigation:SfRadialMenuItem Header="Cut"/> 

<navigation:SfRadialMenuItem Header="Copy"/> 

<navigation:SfRadialMenuItem Header="Paste"/> 

</navigation:SfRadialMenu> 

     </Grid> 

</Page> 


{%endhighlight%}


{%highlight c#%}




SfRadialMenu radialMenu = new SfRadialMenu(); 

SfRadialMenuItem bold = new SfRadialMenuItem() { Header = "Bold" };               SfRadialMenuItem cut = new SfRadialMenuItem() { Header = "Cut" }; 

SfRadialMenuItem copy = new SfRadialMenuItem() { Header = "Copy" }; 

SfRadialMenuItem paste = new SfRadialMenuItem() { Header = "Paste" }; radialMenu.Items.Add(bold);

radialMenu.Items.Add(cut);

radialMenu.Items.Add(copy);

radialMenu.Items.Add(paste); 


{%endhighlight%}
{%endtabs%}

## Theme

Radial Menu supports various built-in themes. Refer to the below links to apply themes for the Radial Menu,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting theme in WPF Radial Menu](Appearance-and-Styling_images/Theme.png)
