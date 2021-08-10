---
layout: post
title: Grid Lines | TreeGrid | WPF | Syncfusion
description: Learn about customization of grid lines for GridCells and HeaderCells in Syncfusion WPF TreeGrid (SfTreeGrid) control and more details.
platform: wpf
control: TreeGrid
documentation: ug
---

# Grid Lines customization in WPF TreeGrid (SfTreeGrid)

SfTreeGrid allows you to customize the grid lines visibility to vertical, horizontal, both or none. To achieve this, use the following properties.

[SfTreeGrid.GridLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridLinesVisibility): To set the border lines for the cells other than header and stacked header cells.
[SfTreeGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility): To set the border lines only for header and stacked header cells.

The following are the list of options available to customize grid lines visibility,

* Both
* Vertical
* Horizontal
* None

## Record rows

### Both

The [GridLinesVisibility.Both](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Both) displays the TreeGrid with both horizontal and vertical grid lines. By default GridLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfTreeGrid x:Name="sfTreeGrid"
                       AutoExpandMode="RootNodesExpanded"
                       ChildPropertyName="ReportsTo"                       
                       ParentPropertyName="ID"
                       ItemsSource="{Binding Employees}"
                       GridLinesVisibility="Both"
                       SelfRelationRootValue="-1"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Both;
{% endhighlight %}
{% endtabs %}

![GridLinesVisibility in WPF TreeGrid](GridLines_images/GridLines_image1.png)

### Horizontal

The [GridLinesVisibility.Horizontal](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Horizontal) displays the TreeGrid with horizontal grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfTreeGrid x:Name="sfTreeGrid"
                       AutoExpandMode="RootNodesExpanded"
                       ChildPropertyName="ReportsTo"
                       ParentPropertyName="ID"
                       ItemsSource="{Binding Employees}"
                       GridLinesVisibility="Horizontal"
                       SelfRelationRootValue="-1"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal GridLinesVisibility in WPF TreeGrid](GridLines_images/GridLines_image2.png)

### Vertical

The [GridLinesVisibility.Vertical](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Vertical) displays the TreeGrid with vertical grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfTreeGrid x:Name="sfTreeGrid"
                       AutoExpandMode="RootNodesExpanded"
                       ChildPropertyName="ReportsTo"
                       ItemsSource="{Binding Employees}"
                       GridLinesVisibility="Vertical"
                       ParentPropertyName="ID"
                       SelfRelationRootValue="-1"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.Vertical;
{% endhighlight %}
{% endtabs %}

![Vertical GridLinesVisibility in WPF TreeGrid](GridLines_images/GridLines_image3.png)

### None
[GridLinesVisibility.None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_None) displays the TreeGrid without grid lines.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfTreeGrid x:Name="sfTreeGrid"
                       AutoExpandMode="RootNodesExpanded"
                       ChildPropertyName="ReportsTo"
                       ItemsSource="{Binding Employees}"
                       GridLinesVisibility="None"
                       ParentPropertyName="ID"
                       SelfRelationRootValue="-1"/>

{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.GridLinesVisibility = GridLinesVisibility.None;
{% endhighlight %}
{% endtabs %}

![None GridLinesVisibility in WPF TreeGrid](GridLines_images/GridLines_image4.png)

## Header rows

You can customize the TreeGrid header lines visibility by using the [SfTreeGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility) property. You can also customize the header lines visibility to horizontal, vertical, none or both. By default HeaderLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfTreeGrid x:Name="sfTreeGrid"
                       AutoExpandMode="RootNodesExpanded"
                       ChildPropertyName="ReportsTo"
                       ParentPropertyName="ID"
                       ItemsSource="{Binding Employees}"
                       HeaderLinesVisibility="Horizontal"
                       SelfRelationRootValue="-1"/>
{% endhighlight %}
{% highlight c# %}
this.sfTreeGrid.HeaderLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal HeaderLinesVisibility in WPF TreeGrid](GridLines_images/GridLines_image5.png)

## Limitations

* Grid lines customization are not supported for RowHeader.


N> You can refer to our [WPF TreeGrid](https://www.syncfusion.com/wpf-controls/treegrid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeGrid example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the treegrid.