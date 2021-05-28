---
layout: post
title: Touch-Events in WPF Wizard Control control | Syncfusion
description: Learn here all about Touch-Events support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
 documentation: ug
---

# Touch-Events in WPF RichTextBoxAdv (Classic)

The RichTextBoxAdv control provides support for touch manipulation like panning, zooming, and selecting the content of the document.

Panning: With the touch manipulation event, we can interpret the multi-touch input to simulate directly manipulating the viewer and allow users to use their finger to scroll over the contents of the RichTextBoxAdv control.

Zooming: With the touch manipulation event, we can interpret multi-touch input to simulate directly manipulating the viewer and allow users to use their fingers to zoom in and out the contents of the RichTextBoxAdv control.

Selection: With the touch manipulation event, we can interpret the multi-touch input to simulate directly manipulating the contents rendered on the viewer and allow users to use their fingers to perform select content similar to using a mouse.

N> By default, the IsManipulationEnabled property of the RichTextBoxAdv control is set to false and touch manipulations are disabled. In order to enable touch manipulation in the RichTextBoxAdv control, set the IsManipulationEnabled property to true.



### Properties



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
IsManipulationEnabled</td><td>
Gets or sets a value that indicates whether manipulation events are enabled in the RichTextBoxAdv. </td><td>
Dependency Property</td><td>
Boolean</td></tr>
</table>


