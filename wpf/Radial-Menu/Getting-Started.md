---
layout: post
title: Getting Started with WPF Radial Menu Control | Syncfusion®
description: Learn about getting started with the Syncfusion® WPF Radial Menu (SfRadialMenu) control, its elements, and more.
platform: WPF
control: SfRadialMenu 
documentation: ug
---

# Getting Started with WPF Radial Menu (SfRadialMenu)

**Namespace:** Syncfusion.Windows.Controls.Navigation

**Assembly:** Syncfusion.SfRadialMenu.WPF (contained in Syncfusion.SfRadialMenu.WPF.dll)

The following code samples demonstrate how to create the RadialMenu in both code-behind and XAML.

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

The Radial Menu supports various built-in themes. Refer to the links below to apply themes for the Radial Menu:

- [Apply a theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
- [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting Theme in WPF Radial Menu](appearance-and-styling_images/wpf-radial-menu-setting-theme.png)
