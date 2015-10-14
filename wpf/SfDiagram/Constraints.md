---
layout: post
title: Constraints | SfDiagram | wpf | Syncfusion
description: constraints
platform: wpf
control: SfDiagram
documentation: ug
---

# Constraints

The GraphConstraints property is used to enable or disable all the behaviors or certain behaviors of the SfDiagram control. This property is applicable to the entire SfDiagram control.

<table>
<tr>
<th>
Constraint</th><th>
Description</th></tr>
<tr>
<td>
None</td><td>
Disables all behaviors of the control</td></tr>
<tr>
<td>
Zoomable</td><td>
Enables zooming behavior</td></tr>
<tr>
<td>
PannableX</td><td>
Enables panning in the horizontal direction.</td></tr>
<tr>
<td>
PannableY</td><td>
Enables panning in the vertical direction.</td></tr>
<tr>
<td>
Pannable</td><td>
Enables panning behavior</td></tr>
<tr>
<td>
PanRailsX</td><td>
Enables panning actions on the x-axis in SfDiagram (horizontal panning).</td></tr>
<tr>
<td>
PanRailsY</td><td>
Enables panning actions on the y-axis in SfDiagram (vertical panning).</td></tr>
<tr>
<td>
Undoable</td><td>
Enables Redo or Undo behavior.</td></tr>
<tr>
<td>
Virtualize</td><td>
Enables Virtualizing behavior.</td></tr>
<tr>
<td>
Relationship</td><td>
Enables properties based on Node and Connector relationships on dragging at run time.</td></tr>
<tr>
<td>
Events</td><td>
Enables all events of the control.</td></tr>
<tr>
<td>
Bridging</td><td>
Enables line bridging.</td></tr>
<tr>
<td>
Routing</td><td>
Enables line routing.</td></tr>
<tr>
<td>
AutoScroll</td><td>
Enables AutoScroll behavior</td></tr>
<tr>
<td>
PanRails</td><td>
Enables panning actions on the x-axis (horizontal panning) and y-axis (vertical panning) in SfDiagram.</td></tr>
<tr>
<td>
Default</td><td>
Enables all behaviors of the control.</td></tr>
</table>

The default value for GraphConstraints property is _Default_.

The following code example illustrates how to add the Undo constraint to existing constraints in SfDiagram:

{% highlight c# %}

sfdiagram.Constraints = sfdiagram.Constraints | GraphConstraints.Undoable;

{% endhighlight %}


N> GraphConstraints property is manipulated by using bitwise operations. For more information about bitwise operations, see Bitwise Operations.

