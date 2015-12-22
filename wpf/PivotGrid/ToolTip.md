---
layout: post
title: 13413-ToolTip
description: 1.3.4.13 tooltip
platform: wpf
control: PivotGridControl
documentation: ug
---

# ToolTip

ToolTips can be set to individual cells. The ToolTip information has the cell value and its respective row and column data and it is set in the style’s Tag property.It can be enabled or disabled in a PivotGrid control using a boolean property. A ToolTip’s skin will be set depending upon the theme set for the PivotGrid. Also, users can customize the ToolTip skin at the sample level. ToolTip text can be localized for its “Value”, “Row”, and “Column” text. Users can also set custom text for ToolTips.

**Use Case Scenarios**

ToolTips can be used to show the data of any cell so that user can get the cell’s full information such as the row and column on which it depends

                                                             Properties Table
<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Value It Accepts</th><th>
Reference Link</th></tr>
<tr>
<td>
TooltipEnabled</td><td>
Enable/disable the ToolTip for the PivotGrid control.</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
TooltipEnabled</td><td>
Enable/disable the ToolTip for individual cell styles (ColumnHeaderStyle, RowHeaderStyle, ValueCellStyle, SummaryCellStyle, SummaryHeaderStyle).</td><td>
bool</td><td>
True, False(Default)</td><td>
-</td></tr>
<tr>
<td>
CustomToolTipTemplateKey</td><td>
Gets/sets the DataTemplate key for custom ToolTips for the entire PivotGrid control.</td><td>
string</td><td>
-</td><td>
-</td></tr>
<tr>
<td>
CustomToolTipTemplateKey</td><td>
Gets/sets DataTemplate key for custom ToolTip for individual cell styles (ColumnHeaderStyle, RowHeaderStyle, ValueCellStyle, SummaryCellStyle, SummaryHeaderStyle)</td><td>
string</td><td>
-</td><td>
-</td></tr>
</table>

## Defining the ToolTip properties in PivotGrid

### Adding ToolTip for the entire PivotGrid

The property **ToolTipEnabled** can be used to achieve this requirement and it can be mentioned either in *XAML* or in *Code-Behind*. 

If through **XAML**, please refer the below code snippet.

{% highlight xml %}

<Grid>
    <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" ToolTipEnabled="True" ItemSource="{Binding   Source={StaticResource data}}">

        <syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotRows>
        <syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotColumns>
        <syncfusion:PivotGridControl.PivotCalculations>
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" />
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
        </syncfusion:PivotGridControl.PivotCalculations>

    </syncfusion:PivotGridControl>
</Grid>


{% endhighlight %}

Else if through **Code-Behind**, please refer the below code snippet.

{% highlight C# %}

public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        grid1.Children.Add(pivotGrid);
        pivotGrid.ItemSource = ProductSales.GetSalesData();
        PivotItem m_PivotItem = new PivotItem() {
            FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
        };
        PivotItem m_PivotItem1 = new PivotItem() {
            FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
        };
        PivotItem n_PivotItem = new PivotItem() {
            FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
        };
        PivotItem n_PivotItem1 = new PivotItem() {
            FieldHeader = "State", FieldMappingName = "State", TotalHeader = "Total"
        };
        // Adding PivotItem to PivotRows
        pivotGrid.PivotRows.Add(m_PivotItem);
        pivotGrid.PivotRows.Add(m_PivotItem1);
        // Adding PivotItem to PivotColumns
        pivotGrid.PivotColumns.Add(n_PivotItem);
        pivotGrid.PivotColumns.Add(n_PivotItem1);
        PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        pivotGrid.ToolTipEnabled = true;
    }
}

{% endhighlight %}

![](ToolTip-Images/PivotGrid Shows ToolTip.png)

### Adding ToolTip to specific areas in PivotGrid

It can be achieved by setting the appearance of ToolTips with respect to cell styles individually. Each style has its own ToolTipEnabled property.

After defining the PivotGrid control, raise the Loaded event for PivotGrid. Inside the PivotGrid_Loaded() event, set the **ToolTipEnabled** property of each cell styles in PivotGrid control.

{% highlight C# %}
    
public partial class MainWindow: Window {
    PivotGridControl pivotGrid = new PivotGridControl();
    public MainWindow() {
        InitializeComponent();
        grid1.Children.Add(pivotGrid);
        pivotGrid.ItemSource = ProductSales.GetSalesData();
        PivotItem m_PivotItem = new PivotItem() {
            FieldHeader = "Product", FieldMappingName = "Product", TotalHeader = "Total"
        };
        PivotItem m_PivotItem1 = new PivotItem() {
            FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total"
        };
        PivotItem n_PivotItem = new PivotItem() {
            FieldHeader = "Country", FieldMappingName = "Country", TotalHeader = "Total"
        };
        PivotItem n_PivotItem1 = new PivotItem() {
            FieldHeader = "State", FieldMappingName = "State", TotalHeader = "Total"
        };
        // Adding PivotItem to PivotRows
        pivotGrid.PivotRows.Add(m_PivotItem);
        pivotGrid.PivotRows.Add(m_PivotItem1);
        // Adding PivotItem to PivotColumns
        pivotGrid.PivotColumns.Add(n_PivotItem);
        pivotGrid.PivotColumns.Add(n_PivotItem1);
        PivotComputationInfo m_PivotComputationInfo = new PivotComputationInfo() {
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        pivotGrid += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        //Enable Tooltip for RowHeaderCellStyle
        this.pivotGrid.RowHeaderCellStyle.ToolTipEnabled = true;
        //Enable Tooltip for ColumnHeaderCellStyle
        this.pivotGrid.ColumnHeaderCellStyle.ToolTipEnabled = true;
        //Enable Tooltip for ValueCellStyle
        this.pivotGrid.ValueCellStyle.ToolTipEnabled = true;
        //Enable Tooltip for SummaryHeaderStyle
        this.pivotGrid.SummaryHeaderStyle.ToolTipEnabled = true;
        //Enable Tooltip for SummaryCellStyle
        this.pivotGrid.SummaryCellStyle.ToolTipEnabled = true;
    }
}

{% endhighlight %}

![](ToolTip-Images/PivotGrid shows Tooltip for summary header.png)

_PivotGrid shows tooltip for summary header_

![](ToolTip-Images/PivotGrid shows Tooltip for column header.png)

_PivotGrid shows tooltip for column header_

![](ToolTip-Images/PivotGrid shows Tooltip for row header.png)

_PivotGrid shows tooltip for row header_

![](ToolTip-Images/PivotGrid shows Tooltip for summary value.png)

_PivotGrid shows tooltip for summary values_

### Adding Custom ToolTip for PivotGrid

It can be achieved by using the property **CustomToolTipTemplateKey**. Custom data templates can be set to the PivotGrid control’s ToolTip. To do so, we need to write a data template and bind the style’s Tag property and set the key to the PivotGrid control’s **CustomToolTipTemplateKey** property. 

Please refer the below code snippets.

{% highlight xaml %}

<Window.Resources>
    <ResourceDictionary>
        <ObjectDataProvider x:Key="data" ObjectType="{x:Type local:ProductSales}" MethodName="GetSalesData" />

        <DataTemplate x:Key="CustomTemplateTooltip">
            <Border BorderThickness="1" BorderBrush="Black" Background="LightGreen" CornerRadius="2">
                <StackPanel Margin="5" Orientation="Horizontal" VerticalAlignment="Center">
                    <TextBlock Text="{ Binding Tag }" VerticalAlignment="Center" />
                </StackPanel>
            </Border>
        </DataTemplate>

    </ResourceDictionary>
</Window.Resources>
<Grid>
    <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ToolTipEnabled="True" ItemSource="{Binding   Source={StaticResource data}}">

        <syncfusion:PivotGridControl.PivotRows>
            <syncfusion:PivotItem FieldHeader="Product" FieldMappingName="Product" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotRows>
        <syncfusion:PivotGridControl.PivotColumns>
            <syncfusion:PivotItem FieldHeader="Country" FieldMappingName="Country" TotalHeader="Total" />
            <syncfusion:PivotItem FieldHeader="State" FieldMappingName="State" TotalHeader="Total" />
        </syncfusion:PivotGridControl.PivotColumns>
        <syncfusion:PivotGridControl.PivotCalculations>
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" />
            <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" SummaryType="Count" />
        </syncfusion:PivotGridControl.PivotCalculations>
    </syncfusion:PivotGridControl>

</Grid>       

{% endhighlight %}

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        pivotGrid.CustomToolTipTemplateKey = "CustomTemplateTooltip";
    }
}
	
{% endhighlight %}

Similarly, we can define custom tooltip to specific areas with respect to cell styles individually using **CustomToolTipTemplateKey** property of Row, Column, Summary Header and Value cell styles.

![](ToolTip-Images/PivotGrid shows CustomToolTip.png)
	