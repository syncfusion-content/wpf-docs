---
layout: post
title: Grid Lines | DataGrid | WPF | Syncfusion
description: Learn about customization of grid lines for GridCells and HeaderCells in Syncfusion WPF DataGrid (SfDataGrid) control and more details.
platform: wpf
control: DataGrid
documentation: ug
---

# Grid Lines customization in WPF DataGrid (SfDataGrid)

SfDataGrid allows you to customize the grid lines visibility to vertical, horizontal, both or none. To achieve this, use the following properties.

[SfDataGrid.GridLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridLinesVisibility): To set the border lines for the cells other than header and stacked header cells.
[SfDataGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility): To set the border lines only for header and stacked header cells.

The following are the list of options available to customize grid lines visibility,

* Both
* Vertical
* Horizontal
* None

## Record rows

### Both

The [GridLinesVisibility.Both](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Both) displays the DataGrid with both horizontal and vertical grid lines. By default GridLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 

<syncfusion:SfDataGrid  x:Name="sfDataGrid"
                        AutoGenerateColumns="True"
                        GridLinesVisibility="Both"
                        ItemsSource="{Binding Orders}"/>

{% endhighlight %}
{% highlight c# %}
this.sfDataGrid.GridLinesVisibility = GridLinesVisibility.Both;
{% endhighlight %}
{% endtabs %}

![GridLinesVisibility in WPF DataGrid](GridLines_images/GridLines_image1.png)

### Horizontal

The [GridLinesVisibility.Horizontal](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Horizontal) displays the DataGrid with horizontal grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 

<syncfusion:SfDataGrid  x:Name="sfDataGrid"
                        AutoGenerateColumns="True"
                        GridLinesVisibility="Horizontal" 
                        ItemsSource="{Binding Orders}"/>

{% endhighlight %}
{% highlight c# %}
 this.sfDataGrid.GridLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal GridLinesVisibility in WPF DataGrid](GridLines_images/GridLines_image2.png)

### Vertical

The [GridLinesVisibility.Vertical](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Vertical) displays the DataGrid with vertical grid lines only.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfDataGrid  x:Name="sfDataGrid"
                        AutoGenerateColumns="True"
                        GridLinesVisibility="Vertical" 
                        ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
 this.sfDataGrid.GridLinesVisibility = GridLinesVisibility.Vertical;
{% endhighlight %}
{% endtabs %}

![Vertical GridLinesVisibility in WPF DataGrid](GridLines_images/GridLines_image3.png)

### None
[GridLinesVisibility.None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_None) displays the DataGrid without grid lines.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

 <dataGrid:SfDataGrid   x:Name="sfDataGrid"
                        AutoGenerateColumns="True" 
                        GridLinesVisibility="None"                     
                        ItemsSource="{Binding OrdersDetails}">
 </dataGrid:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
 this.sfDataGrid.GridLinesVisibility = GridLinesVisibility.None;
{% endhighlight %}
{% endtabs %}

![None GridLinesVisibility in WPF DataGrid](GridLines_images/GridLines_image4.png)

## Header rows

You can customize the DataGrid header lines visibility by using the [SfDataGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility) property. You can also customize the header lines visibility to horizontal, vertical, none or both. By default HeaderLinesVisibility value set as Both.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfDataGrid  x:Name="sfDataGrid"
                        AutoGenerateColumns="True"
                        HeaderLinesVisibility="Horizontal" 
                        ItemsSource="{Binding Orders}"/>

{% endhighlight %}
{% highlight c# %}
this.sfDataGrid.HeaderLinesVisibility = GridLinesVisibility.Horizontal;
{% endhighlight %}
{% endtabs %}

![Horizontal HeaderLinesVisibility in WPF DataGrid](GridLines_images/GridLines_image5.png)

## Grid lines for Master-Details view

SfDataGrid allows you to customize the grid lines for Master-Details view also like parent DataGrid by changing the grid lines properties in GridViewDefinition.DataGrid.

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

<syncfusion:SfDataGrid x:Name="sfDataGrid"
                       AutoGenerateColumns="True"                            
                       AutoGenerateRelations="False"
                       HideEmptyGridViewDefinition="True"
                       GridLinesVisibility="Horizontal"
                       HeaderLinesVisibility="Horizontal"
                       ItemsSource="{Binding Employees}">
        <!--  FirstLevelNestedGrid is created here  -->
        <syncfusion:GridViewDefinition RelationalColumn="Sales">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid  x:Name="FirstLevelNestedGrid"
                                        AutoGenerateColumns="True" 
                                        GridLinesVisibility="Horizontal"
                                        HeaderLinesVisibility="Horizontal">
                </syncfusion:SfDataGrid>
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</syncfusion:SfDataGrid>

{% endhighlight %}
{% highlight c# %}
this.sfDataGrid.GridLinesVisibility = GridLinesVisibility.Horizontal;
this.sfDataGrid.HeaderLinesVisibility = GridLinesVisibility.Horizontal;
this.FirstLevelNestedGrid.GridLinesVisibility = GridLinesVisibility.Horizontal;
this.FirstLevelNestedGrid.HeaderLinesVisibility = GridLinesVisibility.Horizontal;

{% endhighlight %}
{% endtabs %}

![DetailsViewDataGrid GridLinesVisibility customization in WPF DataGrid](GridLines_images/GridLines_image6.png)

## Limitations

* Grid lines customization are not supported for RowHeader.