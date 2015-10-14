---
layout: post
title: Top Summary Layout| PivotGrid | Wpf | Syncfusion
description: Top Summary Layout
platform: wpf
control: PivotGrid
documentation: ug
---

# Top Summary Layout

This feature provides support to display the summary data of each PivotItem at the top and at the beginning of value cells. 


###Property Table

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Data Type</th><th>
Default Value</th></tr>
<tr>
<td>
GridLayout </td><td>
Gets or sets the layout of summary data in Pivot Grid. </td><td>
enum</td><td>
Normal</td></tr>
</table> 

### Adding Top Summary Layout for PivotGrid in an Application

To show the summary at the top of the Pivot Grid value cells, you can set the built-in enum type “GridLayout” in PivotGrid. By default, this property is set to “Normal”, which displays the summary data of rows or columns at the end of the value cells. Setting the GridLayout property to “TopSummary”, displays the summary data at the Top or at the beginning of value cells.

The following code shows how to set the GridLayout property. You can also set the value using XAML, C# or VB language.

{% tabs %}
{% highlight xml %} 



<pivotGrid:PivotGridControl Grid.Row="0" GridLayout="TopSummary" VisualStyle="Default" HorizontalAlignment="Left" Margin="0,0,0,0" Name="pivotGrid"                                     ItemSource="{Binding DataTableSFA}" >

{% endhighlight %} 

{% highlight C# %}  



this.pivotGrid.GridLayout = GridLayout.TopSummary;

{% endhighlight %} 


{% highlight vbnet %} 



Me.pivotGrid.GridLayout = GridLayout.TopSummary

{% endhighlight %}
{% endtabs %} 

The following image illustrates a Pivot Grid which is set show the summary data at the top.  

![](Features_images/Features_img58.png)


Summary data at the top
{:.caption}

### Sample Link

#### Windows 8/7/Vista

{Installation Drive}:\Users\<user name>\AppData\Local\Syncfusion\EssentialStudio\<version number>\BI\WPF\PivotAnalysis.WPF\ProductShowCase\PivotCustomization Demo


