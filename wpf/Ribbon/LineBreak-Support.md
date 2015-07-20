---
layout: post
title: LineBreak-Support
description: linebreak support
platform: wpf
control: Ribbon
documentation: ug
---

# LineBreak Support

LineBreak Support in RibbonButton, SplitButton, DropDownButton Label using Hyphen(-) Character

A Hyphen can now be used as delimiter for displaying the RibbonButton, SplitButton and DropDownButton labels in multiple lines. 

Following code sample illustrates how to use Hyphen (-) to display the labels in multiple lines.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:RibbonButton Name="ribbonButton" Label="Ribbon-Button" &gt;&lt;/syncfusion:RibbonButton&gt;&lt;syncfusion:SplitButton Name="splitButton" Label="Split-Button" &gt;&lt;/syncfusion:SplitButton&gt;&lt;syncfusion:DropDownButton  Name="dropdownButton" Label="DropDown-Button" &gt;&lt;/syncfusion:DropDownButton&gt;</td></tr>
<tr>
<td>
[C#]ribbonButton.Label = "Ribbon-Button";splitButton.Label = "Split-Button";dropdownButton.Label = "DropDown-Button";</td></tr>
</table>


{ ![](LineBreak-Support_images/LineBreak-Support_img1.jpeg) | markdownify }
{:.image }




