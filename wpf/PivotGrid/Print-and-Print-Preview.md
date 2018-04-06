---
layout: post
title: 13414-Print-and-Print-Preview
description: print and print preview
platform: wpf
control: PivotGridControl
documentation: ug
---

# Print and Print Preview

We provide printing support for PivotGrid control along with GroupingBar. You can use the method `ShowPrintPreview` to preview the PivotGrid control before printing. The properties `PrintHeader` and `PrintFooter` helps to add or remove the header and footer information while printing.

**Defining Header and Footer in XAML**

After defining the PivotGrid control, define the DataTemplate for header and footer and set the **PrintHeader** and **PrintFooter** properties of PivotGrid control.

Please refer the below code sample to know about the header template, footer template and setting its properties in PivotGrid control.

{% highlight xaml %}

    <Window.Resources>
        <ResourceDictionary>
            <ObjectDataProvider x:Key="data" ObjectType="{x:Type local:ProductSales}" MethodName="GetSalesData" />
            <!--Creating Template for Header -->
            <DataTemplate x:Key="HeaderTemplate">
                <Grid Height="30">
                    <TextBlock Text="Header" FontSize="15" FontWeight="Bold" HorizontalAlignment="Center"></TextBlock>
                </Grid>
            </DataTemplate>
            <!--Creating Template for Footer -->
            <DataTemplate x:Key="FooterTemplate">
                <Grid Height="30">
                    <TextBlock Text="Footer" FontSize="15" FontWeight="Bold" HorizontalAlignment="Center"></TextBlock>
                </Grid>
            </DataTemplate>
        </ResourceDictionary>
    </Window.Resources>
    <Grid Name="grid1">
        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" VisualStyle="Metro" syncfusion:PrintSettings.PrintHeader="True" syncfusion:PrintSettings.PrintFooter="True" ItemSource="{Binding   Source={StaticResource data}}">

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

**Invoking Print Preview Window in PivotGrid**

After defining the PivotGrid control, raise the loaded event of PivotGrid. Inside the `pivotGrid_Loaded` event, invoke the method `ShowPrintPreview` to enable the printing behavior.

{% highlight C# %}

public partial class MainWindow: Window {
    public MainWindow() {
        InitializeComponent();
        this.pivotGrid.Loaded += pivotGrid_Loaded;
    }

    void pivotGrid_Loaded(object sender, RoutedEventArgs e) {
        //Shows the Print Preview window with templates for header, footer and with user defined title.
        this.pivotGrid.ShowPrintPreview((DataTemplate) this.Resources["HeaderTemplate"], (DataTemplate) this.Resources["FooterTemplate"], "Printing PivotGrid", this);

        //Shows the Print Preview window with empty template and default title.
        this.pivotGrid.ShowPrintPreview(this);

        //Shows the Print Preview window with templates for header, footer and with default title.
        this.pivotGrid.ShowPrintPreview((DataTemplate) this.Resources["HeaderTemplate"], (DataTemplate) this.Resources["FooterTemplate"], this);
    }
}

{% endhighlight %}

![](Print-Images/Print preview.png)

## Print Preview Options

The Print Preview window provides the following options:

* Zooming
* Page Settings
* Print

**Zooming**

Click on the **Zoom** drop-down button in the Print Preview window and select the desired percentage to magnify the PivotGrid view. You can choose from various preset zoom level options such as 50%, 100%, 200% or 400%.

**Page Settings**

Click the **PageSettings** button in the Print Preview window to change the pages while printing.

**Print**

Click the **Print** button in the Print Preview window to print the PivotGrid content.

![](Print-Images/Print and Zooming options.png)