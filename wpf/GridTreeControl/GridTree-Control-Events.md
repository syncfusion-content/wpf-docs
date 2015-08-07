---
layout: post
title: GridTree-Control-Events
description: gridtree control events
platform: wpf
control: GridTree Control
documentation: ug
---

# GridTree Control Events

Here is the list of events exposed in GridTree control. Additionally, you have access to all the GridControl events exposed on the GridTreeControl.InternalGrid.

_GridTree Control Events_

<table>
<tr>
<td>
{{ '**GridTree control Event**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td></tr>
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
This is a cancelable event that is handled just prior to a node being expanded by the user.</td></tr>
<tr>
<td>
ExpandStateChanged</td><td>
This is a notification event that is handled once a node has been expanded by the user.</td></tr>
</table>


> _Note: Additionally, you have access to all the Grid control events exposed on the GridTreeControl.InternalGrid._



