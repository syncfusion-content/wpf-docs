---
layout: post
title: Syncfusion OLAP Architecture | OLAPGauge | wpf | Syncfusion
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


### Properties and Methods

* **FrameType** - Sets the frame type in order to provide effective rim style to the gauge control.
* **ColumnsCount** - Specifies the number of gauge controls to be displayed column-wise.
* **RowsCount** - Specifies the number of gauge controls to be displayed row-wise.
* **Radius** - Specifies the radius of the gauge control. The size of the gauge can be increased or decreased according to the radius value set.
* **ShowMarkersTooltip** - Provides goal information when the mouse pointer is moved over the marker.
* **ShowPointersTooltip** - Provides value information when the mouse pointer is moved over the pointer.
* **ShowGaugeHeaders** - Specifies whether or not to display the header text.
* **ShowGaugeFactors** - Specifies whether or not to display the factor or value text inside the gauge control.
* **ShowGaugeLabels** - Specifies whether or not to display text inside the gauge control.
* **OlapDataManager** - Sets the cube mode.It contains the connection property, current report, cube name , cube schema and PivotEngine for the rendering of gauge.

### Methods

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


