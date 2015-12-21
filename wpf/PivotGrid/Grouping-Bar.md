---
layout: post
title: 1343-Grouping-Bar
description: 1.3.4.3 grouping bar
platform: wpf
control: PivotGridControl
documentation: ug
---

# Grouping Bar

PivotGrid Grouping Bar allows you to slice and dice the fields between column, row, value and filter. Grouping Bar allows us to add, rearrange, or remove the fields to show data in a PivotGrid exactly the way we want. It consists of the following areas

* FilterHeader Area - which holds the Filter items of PivotGrid control.
* DataHeader Area - which holds the PivotCalculation items of PivotGrid control.
* ColumnHeader Area - which holds the PivotColumn items of PivotGrid control.
* RowHeader Area - which holds the PivotRow items of PivotGrid control.

**Use Case Scenario**

Grouping bar also allows to perform sorting,filtering and summarize the data as they want at run time.

                                                           Property Table

<table>
<tr>
<th>
Property Name</th><th>
Description</th><th>
Type</th><th>
Value it Accepts</th><th>
Reference link</th></tr>
<tr>
<td>
ShowGroupingBar</td><td>
Gets or sets whether the GroupingBar needs to shown or hidden.</td><td>
bool</td><td>
True (Default),
False</td><td>
-</td></tr>
</table> 

## Defining the Grouping Bar in PivotGrid

By default, Grouping-Bar is enabled for PivotGrid control. We could show or hide the Grouping Bar by using the **ShowGroupingBar** property of PivotGrid control. It can be done both in *XAML* or *Code-Behind*.

If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" syncfusion:SkinStorage.VisualStyle="Metro" xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WpfApplication1.MainWindow" Title="MainWindow" Height="350" Width="525" xmlns:local="clr-namespace:WpfApplication1">
    <Window.Resources>
        <ResourceDictionary>
            <ObjectDataProvider x:Key="data" ObjectType="{x:Type local:ProductSales}" MethodName="GetSalesData" />
        </ResourceDictionary>
    </Window.Resources>
    <Grid Name="grid1">
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" ShowGroupingBar="True" ItemSource="{Binding   Source={StaticResource data}}">
        </syncfusion:PivotGridControl>
    </Grid>
</Window>

{% endhighlight %}

Else if, through **Code-Behind**, please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        this.Loaded += MainWindow_Loaded;
    }

    void MainWindow_Loaded(object sender, RoutedEventArgs e) {
        PivotGridControl pivotGrid = new PivotGridControl();
        grid1.Children.Add(pivotGrid);
        pivotGrid.ItemSource = ProductSales.GetSalesData();
        pivotGrid.ShowGroupingBar = true;
    }
} 

{% endhighlight %}

![](Grouping-Bar-Images/PivotGrid Shows Grouping Bar.png)

_PivotGrid with Grouping Bar_

![](Grouping-Bar-Images/PivotGrid without grouping bar.png)

_PivotGrid without Grouping Bar_

