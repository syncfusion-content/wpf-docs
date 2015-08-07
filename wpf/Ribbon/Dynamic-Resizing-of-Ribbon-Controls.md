---
layout: post
title: Dynamic-Resizing-of-Ribbon-Controls
description: dynamic resizing of ribbon controls
platform: wpf
control: Ribbon
documentation: ug
---

# Dynamic Resizing of Ribbon Controls

Ribbon Control provides Office 2007 UI. While resizing the ribbon window, which contains the Ribbon Controls, the ribbon controls automatically resize to fit into the Ribbon layout panel. Note: Further resizing the ribbon window will collapse the ribbon bars containing the ribbon controls.

Following property is used to activate the dynamic resizing feature of ribbon controls.

IsAutoSizeFormEnabled – Gets or sets a value indicating whether the ribbon controls should dynamically resize to its auto size form or not. This is a dependency property.

## Enabling Dynamic Resizing of Rabin control

Set IsAutoSizeFormEnabled to true to enable Dynamic Resizing of Rabin control.

The following code illustrates this.



<table>
<tr>
<td>
[XAML]   <syncfusion:Ribbon Name="MyRibbon" IsAutoSizeFormEnabled="True"></syncfusion:Ribbon></td></tr>
<tr>
<td>
[C#]  Ribbon MyRibbon = new Ribbon();MyRibbon.IsAutoSizeFormEnabled = true;</td></tr>
</table>


Ribbon items automatically changed its size form when window resized.



![](Dynamic-Resizing-of-Ribbon-Controls_images/Dynamic-Resizing-of-Ribbon-Controls_img1.jpeg)




Small size form buttons automatically changed to extra small buttons when resized.



![](Dynamic-Resizing-of-Ribbon-Controls_images/Dynamic-Resizing-of-Ribbon-Controls_img2.jpeg)




Large size form buttons changed to small size form buttons when resized.



![](Dynamic-Resizing-of-Ribbon-Controls_images/Dynamic-Resizing-of-Ribbon-Controls_img3.jpeg)


 _Note: Size form changed on further resizing of window._



