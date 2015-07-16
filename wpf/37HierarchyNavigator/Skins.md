---
layout: post
title: Skins
description: skins
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Skins

Hierarchy Navigator supports different skins such as Windows 7, Office2010Blue, Office2010Black, Office2010Silver, Office2007Blue, Office2007Black, Office2007Silver, and Expression Blend. 

## Built-in skins

The Windows 7 theme is applied to the HierarchyNavigator control by default.

Add the following DLLs to apply the corresponding theme for Hierarchy Navigator control. SkinStorage class is used to apply a different visual style for a control, which is available in Syncfusion.Shared.WPF project.

1. Create HierarchyNavigator instance either in XAML or code behind, as shown below.

XAML



&lt;syncfusion:HierarchyNavigator x:Name="hierarchyNavigator"/&gt;



Or

C#



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();



2. Apply Visual Style as shown below in code behind by calling the static method in SkinStorage class in Syncfusion.Shared.WPF.

Window7

C#



SkinStorage.SetVisualStyle(this, "Default");



{ ![](Skins_images/Skins_img1.png) | markdownify }
{:.image }


Office2007Blue 

C#



SkinStorage.SetVisualStyle(this, "Office2007Blue");



{ ![](Skins_images/Skins_img2.png) | markdownify }
{:.image }


Office2007Black

C#



SkinStorage.SetVisualStyle(this, "Office2007Black");



{ ![](Skins_images/Skins_img3.png) | markdownify }
{:.image }


Office2007Silver

C#



SkinStorage.SetVisualStyle(this, "Office2007Silver");



{ ![](Skins_images/Skins_img4.png) | markdownify }
{:.image }


Expression Blend

C#



SkinStorage.SetVisualStyle(this, "Blend");



{ ![](Skins_images/Skins_img5.png) | markdownify }
{:.image }


Metro Theme

C#

SkinStorage.SetVisualStyle(this, “Metro");



{ ![](Skins_images/Skins_img6.png) | markdownify }
{:.image }


Transparent Theme

[C#]

SkinStorage.SetVisualStyle(this, “Transparent");



{ ![](Skins_images/Skins_img7.png) | markdownify }
{:.image }


