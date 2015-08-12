---
layout: post
title: Syncfusion-OLAP-Architecture
description: syncfusion olap architecture
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Syncfusion OLAP Architecture

Syncfusion's OLAP architecture allows you to build a full life cycle reporting solution for your enterprise. Here are the important pieces of the architecture

* OLAP Access Layer - Built on top of ADOMD.NET and provides a high level object model to let you easily define reports.
* OLAP Controls - Chart, Grid, Gauge for ASP.NET, WPF and Silverlight.
* OLAP Report Builder - RAD tool to let you select the dimensions you are interested in visualizing and also lets you define the appearance for the chart, grid and gauge.

Let us see how the Syncfusion OLAP components allow you to build a full life cycle reporting solution for your enterprise.

![](Syncfusion-OLAP-Architecture_images/Syncfusion-OLAP-Architecture_img1.jpeg)



## Class Diagram



![](Syncfusion-OLAP-Architecture_images/Syncfusion-OLAP-Architecture_img2.png)



## Properties and Methods

### Properties

_Property Table_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Value It Accepts</th><th>
Reference Path</th></tr>
<tr>
<td>
FrameType</td><td>
Sets the frame type in order to provide effective rim style to the gauge control.</td><td>
GaugeFrameType</td><td>
CircularWithInnerLeftGradient, CircularWithDarkOuterFrames, CircularCenterGradient, CircularWithInnerTopGradient, FullCircle and HalfCircle</td><td>
-</td></tr>
<tr>
<td>
ColumnsCount</td><td>
Specifies the number of gauge controls to be displayed column-wise.</td><td>
Integer</td><td>
Integer Value</td><td>
-</td></tr>
<tr>
<td>
RowsCount</td><td>
Specifies the number of gauge controls to be displayed row-wise.</td><td>
Integer</td><td>
Integer Value</td><td>
-</td></tr>
<tr>
<td>
Radius</td><td>
Specifies the radius of the gauge control. The size of the gauge can be increased or decreased according to the radius value set.  </td><td>
Integer</td><td>
Integer Value</td><td>
-</td></tr>
<tr>
<td>
ShowMarkersTooltip</td><td>
Provides goal information when the mouse pointer is moved over the marker.</td><td>
Boolean</td><td>
True or False</td><td>
-</td></tr>
<tr>
<td>
ShowPointersTooltip</td><td>
Provides value information when the mouse pointer is moved over the pointer.</td><td>
Boolean</td><td>
True or False</td><td>
-</td></tr>
<tr>
<td>
ShowGaugeHeaders </td><td>
Specifies whether or not to display the header text.</td><td>
Boolean</td><td>
True or False</td><td>
-</td></tr>
<tr>
<td>
ShowGaugeFactors </td><td>
Specifies whether or not to display the factor or value text inside the gauge control.</td><td>
Boolean</td><td>
True or False</td><td>
-</td></tr>
<tr>
<td>
ShowGaugeLabels</td><td>
Specifies whether or not to display text inside the gauge control.</td><td>
Boolean</td><td>
True or False</td><td>
-</td></tr>
<tr>
<td>
OlapDataManager</td><td>
Sets the cube mode.It contains the connection proprerty, current report, cube name , cube schema and pivotengine for the rendering of gauge.</td><td>
OlapDataManager</td><td>
OlapDataManager</td><td>
-</td></tr>
</table>

### Methods

_Methods Table_

<table>
<tr>
<th>
Methods</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th><th>
Reference Links</th></tr>
<tr>
<td>
GetConnectionString()</td><td>
Gets the connection string for the manipulation of data in the corresponding cube.</td><td>
-</td><td>
string</td><td>
-</td></tr>
<tr>
<td>
SetCurrentReport(OlapReport olapReport)</td><td>
Gets the current report for rendering the gauge control.</td><td>
OlapReport</td><td>
OlapReport</td><td>
OlapReport</td></tr>
<tr>
<td>
DataBind()</td><td>
The method is used to fill or bind the data present in {{ '_DataManager_' | markdownify }} into the {{ '_Gauge_' | markdownify }} control.</td><td>
-</td><td>
void</td><td>
-</td></tr>
<tr>
<td>
ShowWaitingDialog()</td><td>
Shows the waiting dialog as soon as the process begins.</td><td>
-</td><td>
void</td><td>
-</td></tr>
<tr>
<td>
CloseWaitingDialog()</td><td>
Closes the waiting dialog as soon as the process ends and even if any error occurs in between.</td><td>
-</td><td>
void</td><td>
-</td></tr>
</table>


