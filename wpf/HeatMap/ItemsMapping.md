---
layout: post
title: ItemsMapping in WPF HeatMap (SfHeatMap) control | Syncfusion®
description: Learn here about the ItemsMapping in the Syncfusion® Essential Studio® WPF HeatMap (SfHeatMap) control, its elements, and more.
platform: wpf
control: SfHeatMap
documentation: ug
---

# Items mapping in the WPF HeatMap (SfHeatMap) control

An external data source can be mapped with the HeatMap using the `ItemsMapping` property. It supports 2 kinds of data source.

* In `TableMapping`, rows represent objects in a collection, and columns represent numerical properties of that object.
* In `CellMapping`, each cell represents an object in a collection; this collection is grouped based on a specific property to form rows and columns.

Let us see the difference between the two types of mapping. The following table represents two different data structures to represent the same HeatMap.

<table>
	<tr>
		<th>CellMapping</th>
		<th>TableMapping</th>
	</tr>
	<tr>
		<td>
			{% highlight C# %}
public class ProductInfo
{
	public string ProductName { get; set; }
	public int Year { get; set; }
	public double Value { get; set; }
}
			{% endhighlight %}
		</td>
		<td>
			{% highlight C# %}
public class ProductInfo
{
	public string ProductName { get; set; }
	public double Y2010 { get; set; }
	public double Y2011 { get; set; }
	public double Y2012 { get; set; }
	public double Y2013 { get; set; }
	public double Y2014 { get; set; }
	public double Y2015 { get; set; }
}
			{% endhighlight %}
		</td>
	</tr>
	<tr>
		<td>
			Here, a single `ProductInfo` object represents a value for a particular product in a particular year.
		</td>
		<td>
			Here, a single `ProductInfo` object represents values for a particular product from year 2010 to 2015.	
		</td>
	</tr>
	<tr>
		<td>
			{% highlight xaml %}
<syncfusion:CellMapping x:Key="CellMapping">
	<syncfusion:CellMapping.Column>
		<syncfusion:ColumnMapping 
			PropertyName="ProductName" 
			DisplayName="Product Name"/>
	</syncfusion:CellMapping.Column>
	<syncfusion:CellMapping.Row>
		<syncfusion:ColumnMapping
			PropertyName="Year"
			DisplayName="Year"/>
	</syncfusion:CellMapping.Row>
	<syncfusion:CellMapping.Value>
		<syncfusion:ColumnMapping 
			PropertyName="Value"/>
	</syncfusion:CellMapping.Value>
</syncfusion:CellMapping>	
			{% endhighlight %}
		</td>
		<td>
			{% highlight xaml %}
<syncfusion:TableMapping x:Key="TableMapping">
	<syncfusion:TableMapping.HeaderMapping>
		<syncfusion:ColumnMapping 
			PropertyName="ProductName" 
			DisplayName="Product Name"/>
	</syncfusion:TableMapping.HeaderMapping>
	<syncfusion:TableMapping.ColumnMapping>
		<syncfusion:ColumnMapping 
			PropertyName="Y2010" 
			DisplayName="2010"/>
		<syncfusion:ColumnMapping 
			PropertyName="Y2011" 
			DisplayName="2011"/>
		<syncfusion:ColumnMapping 
			PropertyName="Y2012"
			DisplayName="2012"/>
		<syncfusion:ColumnMapping 
			PropertyName="Y2013" 
			DisplayName="2013"/>
		<syncfusion:ColumnMapping 
			PropertyName="Y2014" 
			DisplayName="2014"/>
		<syncfusion:ColumnMapping 
			PropertyName="Y2015" 
			DisplayName="2015"/>
	</syncfusion:TableMapping.ColumnMapping>
</syncfusion:TableMapping>
			{% endhighlight %}
		</td>
	</tr>
	<tr>
		<td>
			{% include image.html url="Images/ItemsMapping.png"%}
		</td>
		<td>
			{% include image.html url="Images/ItemsMapping.png"%}
		</td>
	</tr>
</table>





 	 

