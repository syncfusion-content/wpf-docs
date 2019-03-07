---
layout: post
title: Conditional Formatting
description: Conditional formatting
platform: wpf
control: Pivot grid
documentation: ug
---

# Conditional Formatting

Conditional formatting is a process of applying customized styles to any object based on specified conditions.

## Conditional formatting using data conditions

It can be defined by using the `PivotGridControl.ConditionalFormats`, which is an observable collection of *PivotGridDataConditionalFormat* type. The criteria for filtering the cells are specified by using the `PivotGridDataConditionalFormat.Conditions` property, which is a collection of *PivotGridDataCondition* objects. The style for each *ConditionalFormat* can be specified by using the `PivotGridDataConditionalFormat.CellStyle` property, which should be the *PivotGridCellStyle* type. It can be defined in XAML or code-behind.

For **XAML**, refer to the following code snippet.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">

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

            <syncfusion:PivotGridControl.ConditionalFormats>
                <!-- Adding Conditions. -->
                <syncfusion:PivotGridDataConditionalFormat Name="C1">
                    <!-- Specifying the Cell Style. -->
                    <syncfusion:PivotGridDataConditionalFormat.CellStyle>
                        <syncfusion:PivotGridCellStyle Background="Red" FontFamily="Calibri" FontSize="12" />
                    </syncfusion:PivotGridDataConditionalFormat.CellStyle>
                    <!-- Specifying Conditions. -->
                    <syncfusion:PivotGridDataConditionalFormat.Conditions>
                        <syncfusion:PivotGridDataCondition ConditionType="GreaterThan" Value="50000000" SummaryElement="Amount" PredicateType="And" />
                    </syncfusion:PivotGridDataConditionalFormat.Conditions>
                </syncfusion:PivotGridDataConditionalFormat>

                <syncfusion:PivotGridDataConditionalFormat Name="C2">
                    <!-- Specifying the Cell Style. -->
                    <syncfusion:PivotGridDataConditionalFormat.CellStyle>
                        <syncfusion:PivotGridCellStyle Background="Yellow" FontFamily="Calibri" FontSize="12" />
                    </syncfusion:PivotGridDataConditionalFormat.CellStyle>
                    <!-- Specifying Conditions. -->
                    <syncfusion:PivotGridDataConditionalFormat.Conditions>
                        <syncfusion:PivotGridDataCondition ConditionType="LessThan" Value="50" SummaryElement="Quantity" PredicateType="And" />
                    </syncfusion:PivotGridDataConditionalFormat.Conditions>
                </syncfusion:PivotGridDataConditionalFormat>
            </syncfusion:PivotGridControl.ConditionalFormats>

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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        PivotGridDataConditionalFormat m_PivotGridDataConditionalFormat = new PivotGridDataConditionalFormat();
        //Adding Conditions
        m_PivotGridDataConditionalFormat.Conditions.Add(new PivotGridDataCondition() {
            ConditionType = PivotGridDataConditionType.GreaterThan,
                SummaryElement = "Amount",
                Value = "50000000",
                PredicateType = PredicateType.And
        });
        // Specifying the Cell Style.
        m_PivotGridDataConditionalFormat.CellStyle = new PivotGridCellStyle() {
            Background = Brushes.Red, FontFamily = new FontFamily("Calibri"), FontSize = 12
        };
        PivotGridDataConditionalFormat n_PivotGridDataConditionalFormat = new PivotGridDataConditionalFormat();
        //Adding Conditions
        n_PivotGridDataConditionalFormat.Conditions.Add(new PivotGridDataCondition() {
            ConditionType = PivotGridDataConditionType.GreaterThan,
                SummaryElement = "Quantity",
                Value = "50",
                PredicateType = PredicateType.And
        });
        // Specifying the Cell Style.
        n_PivotGridDataConditionalFormat.CellStyle = new PivotGridCellStyle() {
            Background = Brushes.Yellow, FontFamily = new FontFamily("Calibri"), FontSize = 12
        };
        //Adding Conditional Formats to PivotGrid
        pivotGrid.ConditionalFormats.Add(m_PivotGridDataConditionalFormat);
        pivotGrid.ConditionalFormats.Add(n_PivotGridDataConditionalFormat);
    }
}

{% endhighlight %}

![](Conditional-format-images/PivotGrid shows conditionally formatted values.png)

## Conditional formatting using gradient color scales

It can be defined by using the `PivotGridControl.ColorScaleConditionalFormats`, which is an observable collection of *PivotGridColorScaleConditionalFormat* type. It can be done in the following ways.

* Conditional formatting using predefined color scales.
* Conditional formatting using custom colors.

### Conditional formatting using predefined color scales

It can be applied by setting the `ColorScaleName` property, with the color scale value selected from *ColorScale* enumerator. It can be defined in XAML or code-behind.

For **XAML**, refer to the following code snippet.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">

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

            <!-- Conditional Formatting Cells -->
            <syncfusion:PivotGridControl.ColorScaleConditionalFormats>
                <syncfusion:PivotGridColorScaleConditionalFormat Name="C1" CalculationName="Amount" ApplyToAllLevels="True" ColorScaleName="BlueWhiteRed" />
            </syncfusion:PivotGridControl.ColorScaleConditionalFormats>

            </syncfusion:PivotGridControl>

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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        // Conditional formatting cells.
        PivotGridColorScaleConditionalFormat m_ColorScaleFormat = new PivotGridColorScaleConditionalFormat()
        {
            Name = "C1",
            CalculationName= "Amount",
            ColorScaleName = ColorScale.BlueWhiteRed,
            ApplyToAllLevels = true
        };
        //Adding Conditional Formats to PivotGrid
        pivotGrid.ColorScaleConditionalFormats.Add(m_ColorScaleFormat);
    }
}

{% endhighlight %}

![](Conditional-format-images/ColorScale1.png)

### Conditional formatting using custom colors

It can be applied by providing custom colors to the properties `StartColor`, `EndColor`, `MiddleColor` in application level. Also, we can apply conditional formatting based on two level of gradient color scales by defining `StartColor` and `EndColor` properties alone. It can be defined in XAML or code-behind.

For **XAML**, refer to the following code snippet.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">

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

            <!-- Conditional Formatting Cells -->
            <syncfusion:PivotGridControl.ColorScaleConditionalFormats>
                <syncfusion:PivotGridColorScaleConditionalFormat Name="C1" CalculationName="Amount" ApplyToAllLevels="True" StartColor="Green" MiddleColor="Yellow" EndColor="Red" />
            </syncfusion:PivotGridControl.ColorScaleConditionalFormats>

            </syncfusion:PivotGridControl>

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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        // Conditional formatting cells.
        PivotGridColorScaleConditionalFormat m_ColorScaleFormat = new PivotGridColorScaleConditionalFormat()
        {
            Name = "C1",
            CalculationName= "Amount",
            ApplyToAllLevels = true,
            StartColor = System.Drawing.Color.Green,
            MiddleColor = System.Drawing.Color.Yellow,
            EndColor = System.Drawing.Color.Red
        };
        //Adding Conditional Formats to PivotGrid
        pivotGrid.ColorScaleConditionalFormats.Add(m_ColorScaleFormat);
    }
}

{% endhighlight %}

![](Conditional-format-images/ColorScale2.png)

N> To apply conditional formatting based on gradient color scale values, make sure that either `ApplyToAllLevels` or `ApplyToSpecificLevel` property is set to true. Since conditional formatting is applied only when any of the property value is set to true else it displays the value cells without formatting applied.

#### Apply conditional formatting to specific level

`ApplyToSpecificLevel` specifies whether to apply conditional formatting to data cells placed at the intersection of specific row and column fields. It can be achieved by defining `RowName` and `ColumnName` properties. 

To achieve this through **XAML**, refer to the following code snippet.

{% highlight xaml %}

    <Grid>
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" ItemSource="{Binding   Source={StaticResource data}}">

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

            <!-- Conditional Formatting Cells -->
            <syncfusion:PivotGridControl.ColorScaleConditionalFormats>
                <syncfusion:PivotGridColorScaleConditionalFormat Name="C1" CalculationName="Quantity" ApplyToSpecificLevel="True" RowName="Date" ColumnName="Country"  ColorScaleName="GreenYellow" />
            </syncfusion:PivotGridControl.ColorScaleConditionalFormats>

            </syncfusion:PivotGridControl>

        </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

To achieve this through code-behind, refer to the following code snippet.

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
            CalculationName = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum
        };
        PivotComputationInfo m_PivotComputationInfo1 = new PivotComputationInfo() {
            CalculationName = "Quantity", FieldName = "Quantity", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.Count
        };
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo);
        pivotGrid.PivotCalculations.Add(m_PivotComputationInfo1);

        // Conditional formatting cells.
        PivotGridColorScaleConditionalFormat m_ColorScaleFormat = new PivotGridColorScaleConditionalFormat()
        {
            Name = "C1",
            CalculationName = "Quantity",
            ApplyToSpecificLevel = true,
            RowName = "Date",
            ColumnName = "Country",
            ColorScaleName = ColorScale.GreenYellow
        };
        //Adding Conditional Formats to PivotGrid
        pivotGrid.ColorScaleConditionalFormats.Add(m_ColorScaleFormat);
    }
}

{% endhighlight %}

![](Conditional-format-images/ColorScale3.png)