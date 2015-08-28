---
layout: post
title: UseWhereClauseForSlicing
description: usewhereclauseforslicing
platform: wpf
control: OLAP Common 
documentation: ug
---

# UseWhereClauseForSlicing

The UseWhereClauseForSlicing property facilitates the user to decide whether the MDX query parser engine should consider ‘Where’ or ‘Select’ clause for slicing data.

## Use Case Scenarios

While slicing dimensions with a specific range of measures using ‘Select’ clause in MDX query, an exception is thrown. This can be resolved by using the ‘Where’ clause for slicing.

Example: Slicing the Date dimension from months of 2002 to months of 2003 will throw an exception when ‘Select’ clause is used. 

## Properties

_Table6: Property Table_

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
UseWhereClauseForSlicing</td><td>
Enables the user to decide whether the MDX Query Parser Engine should consider the ‘Where’ or ‘Select’ clause for slicing operation</td><td>
Server side </td><td>
Boolean</td><td>
----</td></tr>
</table>




Adding UseWhereClauseForSlicing property to an Application:

Refer to 5.22

