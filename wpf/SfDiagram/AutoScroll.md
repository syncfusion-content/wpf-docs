# AutoScroll

Autoscroll feature automatically scrolls the Diagram whenever the Node or Connector is moved beyond the boundary of the diagram. So that, it is always visible during dragging, resizing, and multiple selection operations. Autoscroll is automatically triggered when any one of the following is done towards the edges of the Diagram.

* Node dragging, resizing
* Connection editing
* Rubber band selection
* Label dragging

Autoscroll border

The Autoscroll border is used to specify the maximum distance between the object and Diagram edge to trigger Autoscroll. The default value is set as 15 for all sides (left, right, top, and bottom) and it can be changed by using the AutoScrollBorder property of page settings. The following code example illustrates how to set Autoscroll border.

<table>
<tr>
<td>
diagram.PageSettings.AutoScrollBorder = new Thickness(150, 15, 15, 15);<br/><br/><br/><br/></td></tr>
</table>


Scroll limit

The scroll limit allows you to define the scrollable region of the Diagram. It includes the following options

* Allows to scroll in all directions without any restriction
* Allows to scroll within the Diagram content.
* Allows to scroll within the specified scrollable area.

ScrollLimit property of scroll settings helps to limit the scrolling.

The following code example illustrates how to specify the scroll limit.

<table>
<tr>
<td>
diagram.PageSettings.ScrollLimit = ScrollLimit.Infinity;<br/><br/><br/><br/></td></tr>
</table>
Scrollable Area

You can restrict scrolling beyond any particular rectangle area by using the ScrollableArea property of scroll settings. To restrict scrolling beyond any custom region, you have to set the ScrollLimit as “limited”. The following code example illustrated how to customize scrollable area.

<table>
<tr>
<td>
diagram.PageSettings.ScrollLimit = ScrollLimit.Limited;<br/><br/>diagram.PageSettings.ScrollableArea = new Rect(0, 0, 500, 500);<br/><br/><br/><br/></td></tr>
</table>
