---
layout: post
title: Expand Nested Properties in WPF PropertyGrid control | Syncfusion
description: Learn about expanding nested properties of selected object in Syncfusion WPF property grid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Expand Nested Properties in PropertyGrid

The PropertyGrid control has support to expand instance properties of a class which has ExpandableObjectConverter as its TypeConverter.

###  Use case scenarios

Using the PropertyExpandMode property, users can choose whether the nested properties of the selected object can be expanded or not. By setting the PropertyExpandMode as NestedMode, the nested properties of the selected object can be expanded, and by setting the PropertyExpandMode as FlatMode, the selected object is shown in flat mode.

### Tables for properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
PropertyExpandMode</td><td>
Gets or sets the PropertyExpandMode</td><td>
Dependency</td><td>
Enum</td></tr>
</table>


####  Sample link

1. Select Start>Programs>Syncfusion>Essential Studio xx.x.x.xx>Dashboard.
2. Select Run Locally Installed Samples in WPF button.
3. Expand the PropertyGrid tree view item in the sample browser.
4. Choose the Getting Started samples listed under it to launch. 


## Adding expand nested properties in property grid to an application 

In the following code sample the PropertyVisibilityMode is set as NestedMode in both XAML and C#.

{% tabs %}

{% highlight xaml %}

<syncfusion:PropertyGrid Name="propertyGrid" PropertyExpandMode="NestedMode">            
</syncfusion:PropertyGrid>

{% endhighlight %}

{% highlight c# %}

propertyGrid.PropertyExpandMode = Syncfusion.Windows.PropertyGrid.PropertyGrid.PropertyExpandModes.NestedMode; 

{% endhighlight %} 

{% endtabs %}
