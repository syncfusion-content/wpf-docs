---
layout: post
title: ToolTip in WPF GridControl | Syncfusion
description: Learn about ToolTip support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: WPF
control: GridControl
documentation: ug
---

# ToolTip in WPF GridControl

Tooltip can be added to individual cells, rows and columns to show more information about the particular cell on mouse hover. ToolTip services can be enabled by setting [GridTooltipService.SetShowTooltips](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTooltipService.html#Syncfusion_Windows_Controls_Grid_GridTooltipService_SetShowTooltips_System_Windows_DependencyObject_System_Boolean_) attached property to `true`. ToolTip for particular cell or row or column can be enabled by setting the [ShowToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ShowTooltip) property of [GridStyleInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html).

## ToolTip for specific cell

ToolTip can be displayed for any cell by setting [ShowToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ShowTooltip) and ToolTip text can be customized by setting [ToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ToolTip) property.

{% tabs %}

{% highlight XAML %}

//To enable tooltip for GridControl
<syncfusion:GridControl Name="grid" syncfusion:GridTooltipService.ShowTooltips="True" />

{% endhighlight %}

{% highlight C# %}

//To enable tooltip for GridControl.
GridTooltipService.SetShowTooltips(gridcontrol, true);

//Set tooltip for particular cell.
gridcontrol.Model[1, 1].ToolTip = " Grid (" + gridcontrol.Model[1, 1].CellValue +") ";
gridcontrol.Model[1, 1].ShowTooltip = true;

{% endhighlight %}

{% endtabs %}

![ToolTip for specific cell in WPF GridControl](Tooltip_images/show-tooltip-cell.png)

## ToolTip for row and column

ToolTip can be displayed for any row or column by setting the [ShowToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ShowTooltip) and ToolTip text can be customized by setting the [ToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ToolTip).

{% tabs %}

{% highlight C# %}

//Adding tooltip to the specific row
gridcontrol.Model.RowStyles[1].ToolTip = "First row";
gridcontrol.Model.RowStyles[1].ShowTooltip = true;

//Adding tooltip to the specific column
gridcontrol.Model.ColStyles[1].ToolTip = "First column";
gridcontrol.Model.ColStyles[1].ShowTooltip = true;

{% endhighlight %}

{% endtabs %}

![Tooltip for specific row in WPF GridControl](Tooltip_images/show-tooltip-rows.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-ToolTip/tree/master/ToolTip_simple)

## Set ToolTip in QueryCellInfo event

You can set the ToolTip to a specific cell or row or column by using the [QueryCellInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridControlBase.html) event.

{% tabs %}

{% highlight C# %}

private void Gridcontrol_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{            
    e.Style.ShowTooltip = true;
    //Show tooltip for specific index
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 1)
        e.Style.ToolTip = " Grid (" + gridcontrol.Model[1, 1].CellValue +") ";
    // Show tooltip for row.
    if (e.Cell.ColumnIndex > 0 && e.Cell.RowIndex == 5)
        e.Style.ToolTip = " Row " + "(" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";
    // Show tooltip for column.
    if (e.Cell.RowIndex > 0 && e.Cell.ColumnIndex == 4)
        e.Style.ToolTip = " Column " + "(" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";
}

{% endhighlight %}

{% endtabs %}

![ToolTip for row or column using QueryCellInfo in WPF GridControl](Tooltip_images/show-tooltip-querycell.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-ToolTip/tree/master/ToolTip_using_querycellinfo)

## Show or hide the ToolTip

You can show or hide the ToolTip in a specific cell or row or column by setting the [ShowToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ShowTooltip) property to `false`.

{% tabs %}

{% highlight C# %}

gridcontrol.Model[1, 1].ShowTooltip = false;

{% endhighlight %}

{% endtabs %}

## Setting ToolTip delay

The [SetToolTipDelay](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTooltipService.html#Syncfusion_Windows_Controls_Grid_GridTooltipService_SetTooltipDelay_System_Windows_DependencyObject_System_Int32_) method allows you to increase or decrease the time that the ToolTip waits before displaying the ToolTip.

{% tabs %}

{% highlight C# %}

GridTooltipService.SetTooltipDelay(gridcontrol, 5000);

{% endhighlight %}

{% endtabs %}

## Handling ToolTip opening event

The [CellToolTipOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridControlBase.html) event will be triggered when the mouse hover on a cell has valid the ToolTip text.

{% tabs %}

{% highlight C# %}

gridcontrol.Model[1, 1].ShowTooltip = true;
gridcontrol.Model[1, 1].ToolTip = " Grid (" + gridcontrol.Model[1, 1].CellValue + ") ";

//CellToolTipOpening event
gridcontrol.CellToolTipOpening += Gridcontrol_CellToolTipOpening;

private void Gridcontrol_CellToolTipOpening(object sender, GridCellToolTipOpeningEventArgs e)
{
    var grids = sender as GridControl;
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 1)
        grids.Model[e.Cell.RowIndex, e.Cell.ColumnIndex].ToolTip = "Hello";
}

{% endhighlight %}

{% endtabs %}

![Change the ToolTip text at run time in WPF GridControl](Tooltip_images/show-tooltip-openingevent.png)

## Hide ToolTip for disabled cell

You can disable the cell by setting `Enabled` property to `false`. If you want to hide the tooltip for this disabled cell, you need to set the [ShowToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_ShowTooltip) property to `false`.

{% tabs %}

{% highlight C# %}

gridcontrol.Model[1, 1].Enabled = false;
gridcontrol.Model[1, 1].ToolTip = " Grid (" + gridcontrol.Model[1, 1].CellValue + ") ";
gridcontrol.Model[1, 1].ShowTooltip = false;

//Using QueryCellInfo
private void Gridcontrol_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 1)
    {
        e.Style.Enabled = false;
        e.Style.ToolTip = " Grid (" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";        
        e.Style.ShowTooltip = false;
    }
}

{% endhighlight %}

{% endtabs %}

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-ToolTip/tree/master/Tooltip_event)

## Identify whether cell has ToolTip

The [HasToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_HasToolTip) property is used to identify whether a cell has ToolTip or not in a cell or row or column in GridControl. You can also highlight the row or column or cell applied to the ToolTip.

{% tabs %}

{% highlight C# %}

gridcontrol.QueryCellInfo += Gridcontrol_QueryCellInfo;

private void Gridcontrol_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{
    if (e.Cell.ColumnIndex > 0 && e.Cell.RowIndex == 5)
        e.Style.ToolTip = " Row " + "(" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";
    if(e.Style.HasToolTip)
    {
        e.Style.Background = Brushes.Green;
        e.Style.Foreground = Brushes.White;
    }
}

{% endhighlight %}

{% endtabs %}

![Highlight the row applied to ToolTip in WPF GridControl](ToolTip_images/show-tooltip-highlight.png)

## Customize the ToolTip

The tooltip appearance can be customized by defining DataTemplate. The DataTemplate can be assigned to the [GridStyleInfo.ToolTipTemplateKey](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_TooltipTemplateKey) or [GridStyleInfo.ToolTipTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html#Syncfusion_Windows_Controls_Grid_GridStyleInfo_TooltipTemplate) property. If you are using tooltipTemplate1 then you need to assign template to its corresponding template key property namely `GridStyleInfo.ToolTipTemplate` or `GridStyleInfo.ToolTipTemplateKey`.

[GridStyleInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridStyleInfo.html) which holds cell information is the `DataContext` for data template of ToolTip.

**Using ToolTipTemplateKey**

{% tabs %}

{% highlight XAML %}

<Window.Resources>
    <DataTemplate x:Key="tooltipTemplate1">
        <Border Name="Border"
                Background="Green"
                BorderBrush="Black"
                BorderThickness="1" Width="60" Height="20"
                CornerRadius="0">
            <TextBlock Background="Transparent" Text="{Binding Path=ToolTip}" Padding="2" />
        </Border>
    </DataTemplate>
</Window.Resources>

{% endhighlight %}

{% highlight C# %}

//Set the template key to a particular index
gridcontrol.Model[1, 1].TooltipTemplateKey = "tooltipTemplate1";

//Using QueryCellInfo event
private void Gridcontrol_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 1)
    {
        e.Style.ToolTip = " Grid (" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";
        e.Style.TooltipTemplateKey = "tooltipTemplate1";
    }
}

{% endhighlight %}

{% endtabs %}

**Using ToolTipTemplate**

{% tabs %}

{% highlight XAML %}

<Window.Resources>
    <DataTemplate x:Key="tooltipTemplate1">
        <Border Name="Border"
                Background="Green"
                BorderBrush="Black"
                BorderThickness="1" Width="60" Height="20"
                CornerRadius="0">
            <TextBlock Background="Transparent" Text="{Binding Path=ToolTip}" Padding="2" />
        </Border>
    </DataTemplate>
</Window.Resources>

{% endhighlight %}

{% highlight C# %}

//Set the template key to a particular index
gridcontrol.Model[1, 1].TooltipTemplate = (DataTemplate)this.Resources["tooltipTemplate1"];

//Using QueryCellInfo event
private void Gridcontrol_QueryCellInfo(object sender, GridQueryCellInfoEventArgs e)
{    
    if (e.Cell.RowIndex == 1 && e.Cell.ColumnIndex == 1)
    {
        e.Style.ToolTip = " Grid (" + e.Cell.RowIndex + "," + e.Cell.ColumnIndex + ") ";    
        e.Style.TooltipTemplate = (DataTemplate)this.Resources["tooltipTemplate1"];
    }
}

{% endhighlight %}

{% endtabs %}

![Customize the ToolTip for WPF GridControl](Tooltip_images/show-tooltip-customization.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-GridControl-ToolTip/tree/master/ToolTip_customization)

## Remove the ToolTip

The `ResetValue` method is used to remove the ToolTip for any cell or row or column in GridControl and to reset the ToolTip value to the default values.

{% tabs %}

{% highlight C# %}

gridcontrol.Model[1, 1].ResetValue(GridStyleInfoStore.ToolTipProperty);

{% endhighlight %}

{% endtabs %}
