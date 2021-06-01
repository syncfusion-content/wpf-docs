---
layout: post
title: Tooltip in WPF Pivot Grid control | Syncfusion
description: Learn about Tooltip support in Syncfusion Essential Studio WPF Pivot Grid control, its elements and more.
platform: wpf
control: Pivot grid
 documentation: ug
---

# Tooltip in WPF Pivot Grid

Tooltip holds the respective cell value and its row and column information. It can be enabled or disabled using the `TooltipEnabled` Boolean property. User can customize the tooltip skin at the sample level and also can set the custom text.

## Adding tooltip for entire pivot grid

The `ToolTipEnabled` property can be used to achieve this requirement and it can be mentioned in XAML or code-behind.

For XAML, refer to the following code snippet.

{% highlight xaml %}

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

For code-behind, refer to the following code snippet.

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

![PivotGrid Shows ToolTip for value cells](ToolTip-Images/PivotGrid Shows ToolTip.png)

## Adding tooltip to specific areas in pivot grid

This can be achieved by setting the appearance of tooltip with respect to each cell styles individually. Each style has its own `ToolTipEnabled` property.

After defining the pivot grid control, raise the loaded event of pivot grid control. Inside the `PivotGrid_Loaded()` event, set the `ToolTipEnabled` property of each cell styles in the pivot grid control.

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

![PivotGrid shows Tooltip for summary header](ToolTip-Images/PivotGrid shows Tooltip for summary header.png)

_PivotGrid shows tooltip for summary header_

![PivotGrid shows Tooltip for column header](ToolTip-Images/PivotGrid shows Tooltip for column header.png)

_PivotGrid shows tooltip for column header_

![PivotGrid shows Tooltip for row header](ToolTip-Images/PivotGrid shows Tooltip for row header.png)

_PivotGrid shows tooltip for row header_

![PivotGrid shows Tooltip for summary values](ToolTip-Images/PivotGrid shows Tooltip for summary value.png)

_PivotGrid shows tooltip for summary values_

## Adding custom tooltip for pivot grid

Custom data templates can be set to the pivot grid controls tooltip using the `CustomToolTipTemplateKey` property. To do so, write a data template and bind the style's Tag property, and then set the key to the pivot grid control's `CustomToolTipTemplateKey` property.

Refer to the following code snippets.

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

Similarly, you can define the custom tooltip to specific areas with respect to individual cell styles using the `CustomToolTipTemplateKey` property of row, column, summary header, and value cell styles.

![PivotGrid shows custom ToolTip](ToolTip-Images/PivotGrid shows CustomToolTip.png)
