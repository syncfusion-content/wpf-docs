---
layout: post
title: GridTree Control Events in WPF Wizard Control control | Syncfusion
description: Learn here all about GridTree Control Events support in Syncfusion WPF GridTreeControl (Classic) control and more.
platform: wpf
control: GridTree
documentation: ug
---

# GridTree Control Events in WPF GridTreeControl (Classic)

Here is the list of events exposed in GridTree control. Additionally, you have access to all the GridControl events exposed on the GridTreeControl.InternalGrid.



<table>
<tr>
<th>
GridTree control Event</th><th>
Description</th></tr>
<tr>
<td>
ModelLoaded</td><td>
Handled once the InternalGrid is created and after the template is applied to the GridTree control. This is the correct place to set the properties and subscribe to events on the InternalGrid.</td></tr>
<tr>
<td>
RequestTreeItems</td><td>
Required event that is used to provide the underlying data to the GridTree control on demand. This event is discussed earlier in this document.</td></tr>
<tr>
<td>
RequestNodeImage</td><td>
By handling this event, you can provide an image to be used in the expand cell. This event is discussed earlier in this document.</td></tr>
<tr>
<td>
ExpandStateChanging</td><td>
By handling this event , you can cancel the node being expanded by the user.</td></tr>
<tr>
<td>
ExpandStateChanged</td><td>
This is a notification event that is handled once a node has been expanded by the user.</td></tr>
</table>


N> Additionally, you have access to all the Grid control events exposed on the GridTreeControl.InternalGrid.



