---
layout: post
title: Rows | SfDataGrid | WPF | Syncfusion
description: rows
platform: wpf
control: SfDataGrid
documentation: ug
---

# Rows

This section explains about various row types in SfDataGrid.

[StackedHeaderRow](http://help.syncfusion.com/wpf/sfdatagrid/columns#stacked-headers)

[AddNewRow](http://help.syncfusion.com/wpf/sfdatagrid/data-manipulation#built-in-addnewrow)

[SummaryRow](http://help.syncfusion.com/wpf/sfdatagrid/summaries)

[UnboundRow](http://help.syncfusion.com/wpf/sfdatagrid/unbound-rows)

## Row Header

RowHeader is a special column used to indicate the status of row (current row, editing status, errors in row, etc.) which is placed as first cell of each row. You can show or hide the row header by setting [SfDataGrid.ShowRowHeader](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~ShowRowHeader.html) property.


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AddNewRowPosition="Top"
                       ItemsSource="{Binding Orders}"
                       ShowRowHeader="True">
{% endhighlight %}
{% highlight c# %}
dataGrid.ShowRowHeader = true;
{% endhighlight %}
{% endtabs %}

![RowHeader in SfDataGrid](Rows_images/Rows_img1.png)

You can change the width of row header by setting [SfDataGrid.RowHeaderWidth](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~RowHeaderWidth.html) property.

### Row indicators and its description

<table>
<tr>
<th>
Row Indicator
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
<img src="Rows_images/Rows_img2.png"/>
</td>
<td>
Denotes the row which has current cell or selected item.
</td>
</tr>
<tr>
<td>
<img src="Rows_images/Rows_img3.png"/>
</td>
<td>
Denotes row is being edited. 
</td>
</tr>
<tr>
<td>
<img src="Rows_images/Rows_img4.png"/>
</td>
<td>
Denotes row is AddNewRow.
</td>
</tr>
<tr>
<td>
<img src="Rows_images/Rows_img5.png"/>
</td>
<td>
Denotes the row has errors. 
</td>
</tr>
<tr>
<td>
<img src="Rows_images/Rows_img6.png"/>
</td>
<td>
Denotes that the current row which has errors.
</td>
</tr>
</table>

See also.

[Show RowIndex in RowHeader](http://help.syncfusion.com/wpf/sfdatagrid/styles-and-templates#styling-rowheader)

[Customizing RowHeader based on record](http://help.syncfusion.com/wpf/sfdatagrid/conditional-styling#row-header)

## Header Row

Header row is present in top of the SfDataGrid which has column headers in it. Column header describes the caption to identify the column content.

![Show the column header in Header row](Rows_images/Rows_img7.png)

You can change the header row height by setting [SfDataGrid.HeaderRowHeight](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~HeaderRowHeight.html) property.

### Hiding Header row

You can hide the header row by setting `SfDataGrid.HeaderRowHeight` as `0` (zero).


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       HeaderRowHeight="0"
                       ItemsSource="{Binding Orders}">
{% endhighlight %}
{% endtabs %}

You can also hide the header row of DetailsViewDataGrid by setting `HeaderRowHeight` as `0` (zero) to [ViewDefinition.DataGrid](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridViewDefinition~DataGrid.html).


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.DetailsViewDefinition>
        <syncfusion:GridViewDefinition RelationalColumn="Details">
            <syncfusion:GridViewDefinition.DataGrid>
                <syncfusion:SfDataGrid x:Name="FirstLevelNestedGrid" HeaderRowHeight="0" />
            </syncfusion:GridViewDefinition.DataGrid>
        </syncfusion:GridViewDefinition>
    </syncfusion:SfDataGrid.DetailsViewDefinition>
</ syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

![Hiding the row header in details view datagrid](Rows_images/Rows_img8.png)

## Freeze panes

SfDataGrid provides support to freeze the rows and columns at top and bottom similar to excel. You can freeze the rows and columns by setting following properties,

<table>
<tr>
<th>
Property Name
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
{{'[FrozenRowsCount](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~FrozenRowsCount.html)'| markdownify }}
</td>
<td>
Set the frozen rows count at `top` of the SfDataGrid.
</td>
</tr>
<tr>
<td>
{{'[FooterRowsCount](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~FooterRowsCount.html)'| markdownify }}
</td>
<td>
Set the footer rows count at `bottom` of the SfDataGrid.
</td>
</tr>
<tr>
<td>
{{'[FrozenColumnCount](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~FrozenColumnCount.html)'| markdownify }}
</td>
<td>
Set the frozen columns count in `left side` of the SfDataGrid. 
</td>
</tr>
<tr>
<td>
{{'[FooterColumnCount](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfGridBase~FooterColumnCount.html)'| markdownify }}
</td>
<td>
Set the frozen columns in `right side` of the SfDataGrid.
</td>
</tr>
</table>


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       FooterColumnCount="1"
                       FooterRowsCount="3"
                       FrozenColumnCount="1"
                       FrozenRowsCount="2"
                       ItemsSource="{Binding Orders}">
{% endhighlight %}
{% highlight c# %}
dataGrid.FooterColumnCount = 1;
dataGrid.FrozenColumnCount = 1;
dataGrid.FrozenRowsCount = 2;
dataGrid.FrozenRowsCount = 3;
{% endhighlight %}
{% endtabs %}

![Show the Fotter column, Footer rows, Frozen column , Frozen rows in SfDataGrid](Rows_images/Rows_img9.png)

### Differentiate frozen rows from normal rows

You can differentiate the frozen rows and footer rows from normal rows by writing style for [VirtualizingCellsControl](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html) and by customizing the `FrozenRow` and `FooterRow` visual states.


{% tabs %}
{% highlight xaml %}
<Style TargetType="{x:Type syncfusion:VirtualizingCellsControl}">
       <Setter Property="Background" Value="Transparent">
       <Setter Property="BorderBrush" Value="Gray">
       <Setter Property="BorderThickness" Value="0">
       <Setter Property="IsTabStop" Value="False">
       <Setter Property="FocusVisualStyle" Value="{x:Null}">
       <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:VirtualizingCellsControl}">
                <Grid>
                    <VisualStateManager.VisualStateGroups>
                        <VisualStateGroup x:Name="BorderStates">
                            <VisualState x:Name="NormalRow">
                            <VisualState x:Name="FrozenRow">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
                                                                        Duration="1"
                                                                        Storyboard.TargetName="PART_RowBorder"
                                                                        Storyboard.TargetProperty="BorderThickness">
                                        <!--  Border Thickness for Frozen rows  -->
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0, 0, 0, 3"/>
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                            <VisualState x:Name="FooterRow">
                                <Storyboard BeginTime="0">
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
                                                                        Duration="1"
                                                                        Storyboard.TargetName="PART_RowBorder"
                                                                        Storyboard.TargetProperty="BorderThickness">
                                        <!--  Border Thickness for Footer rows  -->
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0, 3, 0, 0" />
                                    </ThicknessAnimationUsingKeyFrames>
                                    <ThicknessAnimationUsingKeyFrames BeginTime="0"
                                                                        Duration="1"
                                                                        Storyboard.TargetName="PART_RowBorder"
                                                                        Storyboard.TargetProperty="Margin">
                                        <EasingThicknessKeyFrame KeyTime="0" Value="0, -1, 0, 0" />
                                    </ThicknessAnimationUsingKeyFrames>
                                </Storyboard>
                            </VisualState>
                        </VisualStateGroup>
                    </VisualStateManager.VisualStateGroups>
                    <Border x:Name="PART_RowBorder"
                            BorderBrush="{TemplateBinding BorderBrush}"
                            BorderThickness="{TemplateBinding BorderThickness}" />
                    <Rectangle x:Name="PART_CurrentFocusRow"
                                Margin="{TemplateBinding CurrentFocusBorderMargin}"
                                Stroke="DarkGray"
                                StrokeDashArray="2,2"
                                StrokeThickness="1"
                                Visibility="{TemplateBinding CurrentFocusRowVisibility}" />
                    <Rectangle Clip="{TemplateBinding RowBackgroundClip}" Fill="{TemplateBinding Background}" />
                    <Border Background="{TemplateBinding RowSelectionBrush}"
                            Clip="{TemplateBinding SelectionBorderClipRect}"
                            Visibility="{TemplateBinding SelectionBorderVisiblity}" />
                    <Border Background="{TemplateBinding RowHoverBackgroundBrush}"
                            BorderBrush="{TemplateBinding RowHoverBackgroundBrush}"
                            BorderThickness="{TemplateBinding RowHighlightBorderThickness}"
                            Clip="{TemplateBinding HighlightBorderClipRect}"
                            SnapsToDevicePixels="True"
                            Visibility="{TemplateBinding HighlightSelectionBorderVisiblity}" />
                    <Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}">
                        <ContentPresenter />
                    <Border>
                </Grid>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
{% endhighlight %}
{% endtabs %}

![Show the differentiation of Frozen Rows and Fotter Rows from normal rows](Rows_images/Rows_img10.png)

### Disable drag and drop between frozen and non-frozen columns

You can disable the drag and drop between frozen and non-frozen columns by handling [QueryColumnDragging](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~QueryColumnDragging_EV.html) event.
Using `Reason` property in [QueryColumnDraggingEventArgs](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs.html), you can cancel the column dropping operation. 

In the below code, if the Reason is `QueryColumnDraggingReason.Dropping` and the column is dragged from frozen region to non-frozen region or vice versa, you can cancel the dropping action by setting `e.Cancel` as `true` in the event.


{% tabs %}
{% highlight c# %}
this.dataGrid.QueryColumnDragging +=dataGrid_QueryColumnDragging;

void dataGrid_QueryColumnDragging(object sender, QueryColumnDraggingEventArgs e)
{

    if (e.Reason == QueryColumnDraggingReason.Dropping)
    {

        //used to get frozen column index from the  frozen column count
        var frozenColIndex = dataGrid.FrozenColumnCount +
                                              this.dataGrid.ResolveToStartColumnIndex();
        //cancels dragging from frozen column to non-frozen column

        if (e.From < frozenColIndex && e.To > frozenColIndex - 1)
            e.Cancel = true;

        // cancels dragging from non-frozen column to frozen column

        if (e.From > frozenColIndex && e.To < frozenColIndex ||
             (e.From == frozenColIndex && e.To < frozenColIndex))
            e.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}



### Limitations

1. When using `DetailsView` with freeze panes, exception will be raised like “DetailsView is not supported with Freeze panes support”.

2. When `AllowFrozenGroupHeaders` is true, frozen rows will not be considered.

3. SfDataGrid is supported only for freezing as number of rows in top and number of rows in bottom and it cannot be frozen with specific rows.


N>

1. Header rows, table summary rows and row header are frozen regardless of `FrozenRowsCount` and `FooterRowsCount`.

2. `FrozenRowsCount` and `FooterRowsCount` values should be less than the number of rows and column visible.
