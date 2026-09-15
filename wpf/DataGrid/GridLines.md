---
layout: post
title: Grid Lines Customization in WPF Data Grid | Syncfusion®
description: Grid Lines Customization in Data Grid customizes grid and header lines to improve data presentation, organization, and readability.
platform: wpf
control: Data Grid
documentation: ug
---

# Grid Lines Customization in WPF Data Grid

[WPF Data Grid](https://www.syncfusion.com/wpf-controls/datagrid) allows you to customize the grid lines visibility to vertical, horizontal, both or none. To achieve this, use the following properties.

[SfDataGrid.GridLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_GridLinesVisibility): To set the border lines for the cells other than header and stacked header cells.
[SfDataGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility): To set the border lines only for header and stacked header cells.

The following are the list of options available to customize grid lines visibility,

* Both
* Vertical
* Horizontal
* None

## Record rows

### Both

The [GridLinesVisibility.Both](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Both) displays the Data Grid with both horizontal and vertical grid lines. By default GridLinesVisibility value set as Both.

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

![GridLinesVisibility](GridLines_images/GridLines_image1.png)

### Horizontal

The [GridLinesVisibility.Horizontal](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Horizontal) displays the Data Grid with horizontal grid lines only.

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

![Horizontal GridLinesVisibility](GridLines_images/GridLines_image2.png)

### Vertical

The [GridLinesVisibility.Vertical](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_Vertical) displays the Data Grid with vertical grid lines only.

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

![Vertical GridLinesVisibility](GridLines_images/GridLines_image3.png)

### None
[GridLinesVisibility.None](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridLinesVisibility.html#Syncfusion_UI_Xaml_Grid_GridLinesVisibility_None) displays the Data Grid without grid lines.

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

![None GridLinesVisibility](GridLines_images/GridLines_image4.png)

## Header rows

You can customize the Data Grid header lines visibility by using the [SfDataGrid.HeaderLinesVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderLinesVisibility) property. You can also customize the header lines visibility to horizontal, vertical, none or both. By default HeaderLinesVisibility value set as Both.

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

![Horizontal HeaderLinesVisibility](GridLines_images/GridLines_image5.png)

## Grid lines for Master-Details view

The Data Grid allows you to customize the grid lines for Master-Details view also like parent grid by changing the grid lines properties in GridViewDefinition.DataGrid.

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

![DetailsViewDataGrid GridLinesVisibility customization](GridLines_images/GridLines_image6.png)

## Limitations

* Grid lines customization are not supported for RowHeader.