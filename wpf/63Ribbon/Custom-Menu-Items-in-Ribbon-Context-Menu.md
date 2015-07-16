---
layout: post
title: Custom-Menu-Items-in-Ribbon-Context-Menu
description: custom menu items in ribbon context menu
platform: wpf
control: Ribbon
documentation: ug
---

# Custom Menu Items in Ribbon Context Menu

Ribbon Context Menu now supports display of custom items. You can add custom items in Ribbon Context Menu. Following code sample illustrates how you can add custom items in Ribbon ContextMenu.



[XAML]



&lt;syncfusion:Ribbon Name="ribbon" syncfusion:RibbonContextMenu.IsCustomContextMenuItemsOnTop="True" &gt;

 	&lt;syncfusion:RibbonContextMenu.CustomContextMenuItems &gt;                

       		&lt;syncfusion:RibbonMenuItem Header="Edit" IsCheckable="True" / &gt;                  

       		&lt;syncfusion:RibbonMenuItem Header="Delete" IsCheckable="True"  /&gt;                               

       		&lt;syncfusion:RibbonMenuItem Header="Rename" IsCheckable="True"  /&gt;                                

 	&lt;/syncfusion:RibbonContextMenu.CustomContextMenuItems&gt;

&lt;/syncfusion:Ribbon&gt;



{ ![](Custom-Menu-Items-in-Ribbon-Context-Menu_images/Custom-Menu-Items-in-Ribbon-Context-Menu_img1.jpeg) | markdownify }
{:.image }




