---
layout: post
title: Layout-Related-Features
description: layout related features
platform: wpf
control: DocumentContainer
documentation: ug
---

# Layout Related Features

This section illustrates the following Layout-related feature of Document Container control.

## Setting Visual Styles for Document Container

Document Container comes with the support of visual styles, which gives a great look and feel for the Document Container and enhances the overall appearance of the end user's applications. The visual style for the Document Container is set by using the VisualStyle property.



_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the DocumentContainer. The options provided are as follows.BlendOffice2003Office2007BlueOffice2007BlackOffice2007SilverShinyBlueShinyRedSyncOrangeVS2010MetroTransparent</td></tr>
</table>


Use the following code to set the skin for the Document Container.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding document container --&gt;&lt;syncfusion:DocumentContainer Name="DocContainer" syncfusion:SkinStorage.VisualStyle="Office2007Blue" Mode="MDI"&gt;  …....  …....&lt;/syncfusion:DocumentContainer&gt;</td></tr>
<tr>
<td>
[C#] // Setting the visual style as Office2007Blue SkinStorage.SetVisualStyle(DocContainer, "Office2007Blue");  </td></tr>
</table>


{ ![](Layout-Related-Features_images/Layout-Related-Features_img1.jpeg) | markdownify }
{:.image }


_Document Container with "Office2007Blue" Theme_



{ ![](Layout-Related-Features_images/Layout-Related-Features_img2.jpeg) | markdownify }
{:.image }


_Document Container with "Blend" Theme_



{ ![](Layout-Related-Features_images/Layout-Related-Features_img3.jpeg) | markdownify }
{:.image }


_Document Container with "Office2003" Theme_



{ ![](Layout-Related-Features_images/Layout-Related-Features_img4.png) | markdownify }
{:.image }


_Document Container with "Metro" Theme_



{ ![](Layout-Related-Features_images/Layout-Related-Features_img5.png) | markdownify }
{:.image }


_Document Container with "Transparent" Theme_

