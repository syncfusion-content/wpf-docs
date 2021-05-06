---
layout: post
title: Getting Started with WPF GridControl | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: Grid Control
documentation: ug
---

# Getting Started with WPF GridControl

This section is designed to help you understand and quickly get started using Essential Grid in your WPF application.

Syncfusion WPF suite comes up with a package of powerful grid controls that provides cell-oriented features and acts as an efficient display engine for tabular data that can be customized down to the cell level. It also offers excellent performance characteristics, such as a virtual mode and high-frequency updates, which makes the grid suitable for real-time applications.

The Essential Studio for WPF is comprised of following three types of grid controls:

* [Grid Control](https://www.syncfusion.com/wpf-ui-controls/excel-like-grid)
* [SfDataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) and GridDataControl (classic)
* [SfTreeGrid](https://www.syncfusion.com/wpf-ui-controls/treegrid) and GridTreeControl (classic)

N> Refer [Choose between different Grid's](https://help.syncfusion.com/wpf/datagrid/overview#choose-between-different-grids) to take closer look at the characteristics of each of these controls. 

## Adding the Grid Control to a WPF Application

In this section, we will see how to add the Grid control to a WPF application and load random data. The Grid control can be added to an application through one of the following methods: through a designer or programmatically.

### Adding the Grid Control through a Designer

Please follow the steps below to add the Grid control through a designer.

1. Create new WPF application.

2. Open the Designer window.

3. Drag ScrollViewer from the Toolbox and drop it in the Designer window (Since the Grid control doesn’t have a built-in ScrollViewer, to make the grid flow based on data, the grid should be placed inside the ScrollViewer control.

   ![WPF Designer](Getting-Started_images/Getting-Started_img6.png)

4. Drag GridControl from the Toolbox and drop it inside the ScrollViewer.

   ![WPF Grid Control](Getting-Started_images/Getting-Started_img7.png)

5. Once you drag GridControl and drop it in ScrollViewer, the grid control will be added to the designer and its dependent assemblies will be added to the project.

   ![Designer after Dropping GridControl](Getting-Started_images/Getting-Started_img8.png)

### Programmatically Adding the Grid Control

Instead of adding it through a designer such a Visual Studio, you can add the Grid control programmatically.

1. Create a new WPF application.

2. Add the following Syncfusion assemblies to the project.
   * Syncfusion.Core.dll
   * Syncfusion.Grid.Wpf.dll
   * Syncfusion.GridCommon.Wpf.dll
   * Syncfusion.Shared.Wpf.dll

    ![WPF Grid Control Assembly References](Getting-Started_images/Getting-Started_img9.png)

3. Name the root Grid as layoutRoot in the application’s XAML page.
  
{% tabs %}
{% highlight xaml %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
   <Grid Name="layoutRoot" />  
</Window>
{% endhighlight %}
{% endtabs %}
      

4. Create ScrollViewer and GridControl in code. 

5. To add the grid to the view, add GridControl as content of ScrollViewer and then add the ScrollViewer as a child of layoutRoot (Grid).

{% tabs %}
{%highlight c#%}
//ScrollViewer defined here
ScrollViewer ScrollViewer = new ScrollViewer();
//GridControl defined here
GridControl gridControl = new GridControl();
//GridControl set as the content of the ScrollViewer
ScrollViewer.Content = gridControl;     
//To bring the Grid control to the view, ScrollViewer should be set as a child of LayoutRoot      
this.layoutRoot.Children.Add(ScrollViewer);           
{%endhighlight%}
{% endtabs %}

## Populating the Grid control with Data

The Grid control is a cell-based control, so to populate it, RowCount and ColumnCount are mandatory. Once ColumnCount and RowCount are specified, data can be populated by using one of the following methods. 

1.You can populate data by looping through the cells in the Grid control. The following code explains this scenario.

{% tabs %}
{%highlight c#%}
//Specifying row and column count
gridControl.Model.RowCount = 100;
gridControl.Model.ColumnCount = 20;

//Looping through the cells and assigning the values based on row and column index
for (int i = 0; i < 100; i++)
{
    for (int j = 0; j < 20; j++)
    {
        gridControl.Model[i, j].CellValue = string.Format("{0}/{1}", i, j);
    }
}
{%endhighlight%}
{% endtabs %}


2.You can populate data by handling the QueryCellInfo event of gridControl. This will load the data in and on-demand basis, ensuring optimized performance.

{% tabs %}
{%highlight c#%}
//Specifying row and column count
gridControl.Model.RowCount = 100;
gridControl.Model.ColumnCount = 20;
this.gridControl.QueryCellInfo += new Syncfusion.Windows.Controls.Grid.GridQueryCellInfoEventHandler(gridControl_QueryCellInfo);

//Assigning values by handling the QueryCellInfo event
void gridControl_QueryCellInfo(object sender, Syncfusion.Windows.Controls.Grid.GridQueryCellInfoEventArgs e)
{
    e.Style.CellValue=string.Format("{0}/{1}", e.Cell.RowIndex, e.Cell.ColumnIndex);
    
}   
{%endhighlight%}
{% endtabs %}

3.Now, run the application. The grid will appear as follows. 

![WPF Grid Control](Getting-Started_images/Getting-Started_img10.png)

   

