---
layout: post
title: OlapReport-Serialization
description: olapreport serialization
platform: wpf
control: OLAP Client 
documentation: ug
---
# OlapReport Serialization

This feature enables the user to save additional settings along the OLAP information in an OlapReport and load them whenever required. 

The following are the appearance settings that a user can save and load during the runtime in an OlapChart and OlapGrid.

## OlapChart

* Appearance
* Legend position
* Series color types
* Skin for chart

## OlapGrid

* Freeze headers
* Show Tooltip
* Header and Value cell settings
* Appearance

## Use Case Scenarios

The user can maintain the Chart and/or the Grid appearance settings with its OLAP data through an OlapReport.

The following image shows a serialized Chart and Grid appearance settings in an XML format: 

![C:/Users/diana/Desktop/AdditionalInfoSerialization.png](OlapReport-Serialization_images/OlapReport-Serialization_img1.png)



## Properties

_Properties Table_

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
 ChartSettings</td><td>
Gets or  sets the chart appearance settings</td><td>
CLR </td><td>
ChartApperanceSettings </td><td>
-</td></tr>
<tr>
<td>
GridSettings</td><td>
Gets or sets the Grid appearance settings</td><td>
CLR</td><td>
GridAppearanceSettings</td><td>
-</td></tr>
</table>


## Sample Link

The user can find samples in the following locations:

## For OlapChart

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapChart.WPF\Samples\Serialization\Serialization Demo

## For OlapGrid

SystemDrive:\Users\<user_name>\AppData\Local\Syncfusion\EssentialStudio\<version_number>\BI\WPF\OlapGrid.WPF\Samples\Serialization\Serialization Demo

