# Overview Control

Overview control is used to display a preview (overall view) of the entire content of a Diagram. This helps you to look overall picture of large Diagram and also to navigate (pan or zoom) to a particular position of the page

When you work on a very large Diagram, You may not know the part where you are actually working or navigation from one part to another might be a difficult. To navigation, you can zoom out entire Diagram and find where you are. This solution is not suitable when you need some frequent navigation.

Overview control solved this problem by displaying a preview (overall view) of the entire Diagram. A rectangle indicated viewport of the Diagram. Navigation becomes easy by dragging this rectangle.

Note : 

Supported platform: WPF, WinRT 8.1, Universal

Use Case Scenarios

You can view the entire content of a Diagram in a preview window. This helps you to navigate to a particular position of the page.

<table>
<tr>
<td>
**Property******<br/><br/></td><td>
**Description******<br/><br/></td><td>
**Type******<br/><br/></td><td>
**Data** **Type******<br/><br/></td></tr>
<tr>
<td>
Constraint<br/><br/></td><td>
Gets or Sets the OverviewConstraints type.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
enum<br/><br/>OverviewConstraints.None<br/><br/>OverviewConstraints.Pan<br/><br/>OverviewConstraints.TapFocus<br/><br/>OverviewConstraints.DrawFocus<br/><br/>OverviewConstraints.Zoom<br/><br/></td></tr>
<tr>
<td>
FocusBrush<br/><br/></td><td>
Specifies the color of the viewport area in the preview.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td></tr>
<tr>
<td>
UnFocusBrush<br/><br/></td><td>
Specifies the background of the extended area in the preview.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Brush<br/><br/></td></tr>
</table>
Adding Overview control to an Application

The following code example explains how to add Overview to an Application

![](OverviewControl_images/OverviewControl_img1.jpeg)


Refer to the Overview Sample from the following link.

Sample Link:

Navigation->WPF->Diagram->Overview

