---
layout: post
title: Rows in WPF DataGrid control | Syncfusion
description: Learn here all about Rows support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Rows in WPF DataGrid (SfDataGrid)

This section explains about various row types in SfDataGrid.

[StackedHeaderRow](http://help.syncfusion.com/wpf/sfdatagrid/columns#stacked-headers)

[AddNewRow](http://help.syncfusion.com/wpf/sfdatagrid/data-manipulation#built-in-addnewrow)

[SummaryRow](http://help.syncfusion.com/wpf/sfdatagrid/summaries)

[UnboundRow](http://help.syncfusion.com/wpf/sfdatagrid/unbound-rows)

## Row Header

RowHeader is a special column used to indicate the status of row (current row, editing status, errors in row, etc.) which is placed as first cell of each row. You can show or hide the row header by setting [SfDataGrid.ShowRowHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_ShowRowHeader) property.

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

![WPF DataGrid with RowHeader](Rows_images/wpf-datagrid-row-header.png)

See also.

[Show RowIndex in RowHeader](http://help.syncfusion.com/wpf/sfdatagrid/styles-and-templates#styling-rowheader)

[Customizing RowHeader based on record](http://help.syncfusion.com/wpf/sfdatagrid/conditional-styling#row-header)

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

### Row header width

You can change the width of the row header by setting [SfDataGrid.RowHeaderWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_RowHeaderWidth) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       ShowRowHeader="True"
                       RowHeaderWidth="50"
                       ItemsSource="{Binding Orders}"  />
{% endhighlight %}

{% highlight c# %}
dataGrid.RowHeaderWidth = 50;
{% endhighlight %}
{% endtabs %}

### Display the row index in row header

You can display the corresponding row index in each row header, by customizing the `ControlTemplate` of `GridRowHeaderCell`. You have to bind the `RowIndex` property to `TextBlock.Text` like the below code example.

{% tabs %}
{% highlight xaml %}

<Style TargetType="syncfusion:GridRowHeaderCell">
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="syncfusion:GridRowHeaderCell">
                <Border x:Name="PART_RowHeaderCellBorder"
                        Background="{TemplateBinding Background}"
                        BorderBrush="{TemplateBinding BorderBrush}"
                        BorderThickness="{TemplateBinding BorderThickness}">
                    <Grid>
                        <TextBlock HorizontalAlignment="Center"
                                   VerticalAlignment="Center"
                                   Text="{Binding RowIndex,RelativeSource={RelativeSource TemplatedParent}}"
                                   TextAlignment="Center" />
                    </Grid>
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>

{% endhighlight %}
{% endtabs %}

![WPF DataGrid displays Row Header Cells with Row Index](Interactive-Features_images/wpf-datagrid-row-index.png)


You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/WPF-13678149272112665828.zip).

### Change the current row indicator

You can change the CurrentRowIndicator in the row header by customizing the control template of `GridRowHeaderCell`.

{% tabs %}
{% highlight xaml %}

<Style TargetType="syncfusion:GridRowHeaderCell">
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="syncfusion:GridRowHeaderCell">
                <Border x:Name="PART_RowHeaderCellBorder"
                        Background="{TemplateBinding Background}"
                        BorderBrush="{TemplateBinding BorderBrush}"
                        BorderThickness="{TemplateBinding BorderThickness}">
                    <VisualStateManager.VisualStateGroups>
                        <VisualStateGroup x:Name="IndicationStates">
                            <VisualState x:Name="Normal">
                            </VisualState>
                            <VisualState x:Name="CurrentRow">
                                <Storyboard>
                                    <ObjectAnimationUsingKeyFrames Storyboard.TargetName="PART_RowHeaderIndicator" Storyboard.TargetProperty="Data">
                                        <DiscreteObjectKeyFrame KeyTime="0">
                                            <DiscreteObjectKeyFrame.Value>
                                                <Geometry>F1M-218.342,2910.79L-234.066,2926.52 -233.954,2926.63 -225.428,2926.63 -210.87,2912.07 -206.495,2907.7 -225.313,2888.88 -234.066,2888.88 -218.342,2904.6 -259.829,2904.6 -259.829,2910.79 -218.342,2910.79z</Geometry>
                                            </DiscreteObjectKeyFrame.Value>
                                        </DiscreteObjectKeyFrame>
                                    </ObjectAnimationUsingKeyFrames>                                            
                                </Storyboard>
                            </VisualState>
                        </VisualStateGroup>
                    </VisualStateManager.VisualStateGroups>
                    <Path x:Name="PART_RowHeaderIndicator"
                          Width="8.146"
                          Height="8.146"
                          HorizontalAlignment="Center"
                          VerticalAlignment="Center"
                          Fill="#FF303030"
                          Stretch="Fill">
                    </Path>
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>

{% endhighlight %}
{% endtabs %}

![Customizing Current Row Indicator in WPF DataGrid](Interactive-Features_images/wpf-datagrid-row-indicator.png)

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ChangingCurrentRowIndicator257326168.zip).

### Change the background of row header 

You can change the background color of the row header by customizing the style of the `GridRowHeaderCell`. You can change the background color with the converter based on the underlying collection.

{% tabs %}
{% highlight xaml %}

<Application.Resources>       
    <local:CustomConverter x:Key="converter"/>
    <!--Customizing the RowHeader style--> 
    <Style  TargetType= "syncfusion:GridRowHeaderCell">
        <!--By using converter the Background color is changed based on the business logic-->
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter }}"/>
    </Style>
</Application.Resources>

{% endhighlight %}

{% highlight c# %}

public class CustomConverter:IValueConverter
{
 
    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {

        //Type casting the value as Data class(Business logic)
        var data = value as Data;

        //The Red color is applied to RowHeader if the status value is true otherwise the white color is applied 

        if (data.Status == true)
            return Brushes.Red;

        else
            return Brushes.Green;
    }
    
    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}

{% endhighlight %}
{% endtabs %}

![Changing Row Header Background of WPF DataGrid](Interactive-Features_images/wpf-datagrid-row-header-background.png)

You can get the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/BackgroundColorForRowHeader_WPF18250214901515913833.zip).

## Header Row

Header row is present in top of the DataGrid which has column headers in it. Column header describes the caption to identify the column content.

![WPF DataGrid displays Column Header in Header Row](Rows_images/wpf-datagrid-column-header.png)

You can change the header row height by setting [SfDataGrid.HeaderRowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_HeaderRowHeight) property.

### Hiding Header row

You can hide the header row by setting `SfDataGrid.HeaderRowHeight` as `0` (zero).


{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       HeaderRowHeight="0"
                       ItemsSource="{Binding Orders}">
{% endhighlight %}
{% endtabs %}

You can also hide the header row of DetailsViewDataGrid by setting `HeaderRowHeight` as `0` (zero) to [ViewDefinition.DataGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridViewDefinition.html#Syncfusion_UI_Xaml_Grid_GridViewDefinition_DataGrid).


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

![Hide Header Row in WPF Details View Datagrid](Rows_images/wpf-datagrid-hide-header-row.png)

## Freeze panes

DataGrid provides support to freeze the rows and columns at top and bottom similar to excel. You can freeze the rows and columns by setting following properties,

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
{{'[FrozenRowsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FrozenRowsCount)'| markdownify }}
</td>
<td>
Set the frozen rows count at <kbd>top</kbd> of the SfDataGrid.
</td>
</tr>
<tr>
<td>
{{'[FooterRowsCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_FooterRowsCount)'| markdownify }}
</td>
<td>
Set the footer rows count at </kbd>bottom</kbd> of the SfDataGrid.
</td>
</tr>
<tr>
<td>
{{'[FrozenColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FrozenColumnCount)'| markdownify }}
</td>
<td>
Set the frozen columns count in <kbd>left side</kbd> of the SfDataGrid. 
</td>
</tr>
<tr>
<td>
{{'[FooterColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_FooterColumnCount)'| markdownify }}
</td>
<td>
Set the frozen columns in <kbd>right side</kbd> of the SfDataGrid.
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

![WPF DataGrid displays Frozen Rows and columns](Rows_images/wpf-datagrid-freeze-rows-and-columns.png)

### Differentiate frozen rows from normal rows

You can differentiate the frozen rows and footer rows from normal rows by writing style for [VirtualizingCellsControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html) and by customizing the `FrozenRow` and `FooterRow` visual states.


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

![WPF DataGrid displays Differentiating Frozen Rows and Footer Rows from Normal Rows](Rows_images/wpf-datagrid-differentiate-frozen-rows-and-columns.png)

### Disable drag and drop between frozen and non-frozen columns

You can disable the drag and drop between frozen and non-frozen columns by handling [QueryColumnDragging](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.
Using `Reason` property in [QueryColumnDraggingEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.QueryColumnDraggingEventArgs.html), you can cancel the column dropping operation. 

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

1. When using `DetailsView` with freeze panes, exception will be raised like **DetailsView is not supported with Freeze panes support**.

2. When `AllowFrozenGroupHeaders` is true, frozen rows will not be considered.

3. SfDataGrid has support to freeze the number of rows from top or bottom. There is no support to freeze a specific row.

N> 1. Header rows, table summary rows and row header are frozen regardless of `FrozenRowsCount` and `FooterRowsCount`.
   2. `FrozenRowsCount` and `FooterRowsCount` values should be less than the number of rows and column visible.
