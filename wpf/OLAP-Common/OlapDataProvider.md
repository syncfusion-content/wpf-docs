---
layout: post
title: OlapDataProvider in WPF OLAP Common control | Syncfusion
description: Learn about OlapDataProvider support in Syncfusion WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
 documentation: ug
---

# OlapDataProvider in WPF OLAP Common

The database connectivity related works are all taken care of by this part of the base. Here, the  Microsoft.AnalysisService.AdomdClient data provider is used. Establishing the connection, checking the state of the connection, and closing the connection are basic operations provided by the general data provider, but some more information is required to provide the input for controls.

This part of the base will get the connection information and establish a connection with the specified data source and retrieve the information from the database and store it in its classes. This part of the base has the required logic to retrieve the information from the database and store it in the object of class in data namespace.

 All the information about the connected cube will intersect and store in the object of classes in the data namespace, which are equivalent to the classes in the AdomdClient. This information is required to provide the input for OLAP controls.

Important class in DataProvider namespace:

* AdomdDataProvider

## AdomdDataProvider

The important properties and methods in AdomdDataProvider class are tabulated below:

###  Properties

* **CatalogName**: Gets the connected database name.
* **ConnectionString**: Sets or gets the connection string.
* **CurrentCellSet**: Gets the currently executed CellSet.
* **GetCubes**: Gets the information about the cubes in the connected data source.


### Methods



<table>
<tr>
<th>
Method Name</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th><th>
Reference Link</th></tr>
<tr>
<td>
ExecuteCellSet</td><td>
Four arguments should be given to invoke this method. The arguments are MDX query as string, drill-down state of result set as bool, query append info as bool, and finally get the OlapReport. This method will generate the CellSet for the given query or OlapReport.</td><td>
MDX Query as string, drill-down state as bool, property append status as bool and current OlapReport of OlapDataManager.</td><td>
CellSet</td><td>
-</td></tr>
<tr>
<td>
GetCubeSchema</td><td>
This method will get the cube name and intersect the cube to get all the information about the cube and return an object of type CubeSchema, which will contain all the information. CubeSchema is a class in data namespace.</td><td>
Cube Name as string</td><td>
CubeSchema</td><td>
-</td></tr>
<tr>
<td>
GetChildMembers</td><td>
This method will get the member element and the expander state and return the child members of the given member as MemberCollection.</td><td>
Parent member as Member and drill down state as bool</td><td>
MemberCollection</td><td>
-</td></tr>
<tr>
<td>
GetLevelMembers</td><td>
This method will get the level element as argument and return the member elements of that level as MemberCollection.</td><td>
Level</td><td>
MemberCollection</td><td>
-</td></tr>
<tr>
<td>
GetParentMember</td><td>
This method is used to find the parent member of a member element. By passing a member element as an argument, this element will return its parent member.</td><td>
Member</td><td>
Member</td><td>
-</td></tr>
<tr>
<td>
ValidateConnectionString</td><td>
This method will validate the specified connection string in the data manager or in the data provider and return the validated status.</td><td>
-</td><td>
bool</td><td>
-</td></tr>
</table>


