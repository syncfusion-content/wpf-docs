---
layout: post
title: Getting-Started
description: getting started 
platform: wpf
control: Radial Menu 
documentation: ug
---

# Getting Started 

Namespace : Syncfusion.Windows.Controls.Navigation 

Assembly : Syncfusion.SfRadialMenu.WPF (in Syncfusion.SfRadialMenu.WPF.dll) 

The following code sample shows how to create the RadialMenu from code-behind and XAML. 



[XAML]



&lt;Page xmlns:navigation="clr-namespace:Syncfusion.Windows.Controls.Navigation;assembly=Syncfusion.SfRadialMenu.Wpf"&gt; 

     &lt;Grid&gt;

&lt;navigation:SfRadialMenu&gt; 

&lt;navigation:SfRadialMenuItem Header="Bold"/&gt;

&lt;navigation:RadialMenuItem Header="Cut"/&gt; 

&lt;navigation:SfRadialMenuItem Header="Copy"/&gt; 

&lt;navigation:SfRadialMenuItem Header="Paste"/&gt; 

&lt;/navigation:SfRadialMenu&gt; 

     &lt;/Grid&gt; 

&lt;/Page&gt; 





[C#]



SfRadialMenu radialMenu = new SfRadialMenu(); 

SfRadialMenuItem bold = new SfRadialMenuItem() { Header = "Bold" };               SfRadialMenuItem cut = new SfRadialMenuItem() { Header = "Cut" }; 

SfRadialMenuItem copy = new SfRadialMenuItem() { Header = "Copy" }; 

SfRadialMenuItem paste = new SfRadialMenuItem() { Header = "Paste" }; radialMenu.Items.Add(bold);

radialMenu.Items.Add(cut);

radialMenu.Items.Add(copy);

radialMenu.Items.Add(paste); 





