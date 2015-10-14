---
layout: post
title: OlapDataProvider| OLAPCommon  | Wpf | Syncfusion
description: olapdataprovider
platform: wpf
control: OLAPCommon 
documentation: ug
---

# OlapDataProvider

The database connectivity related works are all taken care of by this part of the base. Here we are using Microsoft.AnalysisService.AdomdClient data provider. Establishing the connection, checking the state of the connection and closing the connection are basic operations provided by the general data provider, but we need some information beyond this in order to provide the input for our controls.  

This part of the base will get the connection information and establish a connection with the specified data source and retrieve the information from the data base and store it in its classes. This part of the base will have the required logic to retrieve the information from the data base and store it in the object of class in Data namespace. 

 All the information about the connected cube will intersect and be stored in object of classes in Data namespace, which are equivalent to the classes in the AdomdClient. This information is required to provide the input for OLAP controls.

Important class in DataProvider namespace:

* AdomdDataProvider

## AdomdDataProvider

The important properties and methods in AdomdDataProvider class are tabulated below:

###  Properties

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference Link</th></tr>
<tr>
<td>
CatalogName</td><td>
To get the connected database name</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
ConnectionString</td><td>
To set or get the connection string</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
CurrentCellSet</td><td>
To get the currently executed CellSet</td><td>
CellSet</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
GetCubes</td><td>
To get the information about the cubes in the connected data source</td><td>
CubeInfoCollection</td><td>
-</td><td>
-</td></tr>
</table>



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
Four arguments should be given to invoke this method. The arguments are MDX query as string, drill down state of result set as bool, query append info as bool and finally get the OlapReport. This method will generate the CellSet for the given query or OlapReport.</td><td>
Mdx Query as string, drill down state as bool, Property append status as bool and Current OlapReort of OlapDataManager</td><td>
CellSet</td><td>
-</td></tr>
<tr>
<td>
GetCubeSchema</td><td>
This method will get the cube name and intersect the cube to get all the information about the cube and return an object of type CubeSchema, which will contain all the information. CubeSchema is a class in Data namespace.</td><td>
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


