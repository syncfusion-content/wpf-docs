---
layout: post
title: Printing in WPF DataGrid control | Syncfusion
description: Learn here all about Printing support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Printing in WPF DataGrid (SfDataGrid)

SfDataGrid provides support to print the data displayed in the DataGrid using [SfDataGrid.Print](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_Print) method. It also provides support to display print preview window by calling   [SfDataGrid.ShowPrintPreview](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowPrintPreview) method.

{% tabs %}
{% highlight c# %}
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

## Print Preview

SfDataGrid provides option to display print preview to review and customize the document in desired format before printing. Print preview window can be opened by calling [SfDataGrid.ShowPrintPreview](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_ShowPrintPreview) method.

{% tabs %}
{% highlight c# %}
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![Print preview window for WPF DataGrid before printing](Printing_images/Printing_img1.png)

## Print Settings

SfDataGrid provides various options to customize print preview settings using [SfDataGrid.PrintSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_PrintSettings) property of type [PrintSettings](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html).

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowRepeatHeaders = false;            
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Print

Print preview window has Print and Quick Print Buttons which needs to be clicked to print the SfDataGrid.

![Print and Quick Print buttons in print preview window of WPF DataGrid](Printing_images/Printing_img2.png)

1. Clicking the Print button opens the System print dialog where user can select the printer and set the number of copies to be printed.

    ![Shows the system print dialog for printing WPF DataGrid](Printing_images/Printing_img3.png)

2. Clicking the Quick Print button, directly print the pages using default printer without opening the print dialog.

### Scaling

SfDataGrid provides support to scale rows or columns or both while printing to fit on one page. Scaling options can be changed by setting [PrintSettings.PrintScaleOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintScaleOption) property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintScaleOption = PrintScaleOptions.FitAllColumnsonOnePage;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

Scaling options can be changed in print preview at runtime by selecting from scaling options drop-down in print preview. 

![Print scaling options in print preview window of WPF DataGrid](Printing_images/Printing_img4.png)

### Column Header on each page

Column headers can be printed on each page by enabling [PrintSettings.AllowRepeatHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowRepeatHeaders) property while printing.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowRepeatHeaders = true;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Changing Flow Direction while printing

You can change the text direction in print page by using [PrintSettings.PrintFlowDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintFlowDirection) property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintFlowDirection = FlowDirection.RightToLeft;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

### Print with StackedHeaders

SfDataGrid provides support to print the StackedHeaders by setting the [PrintSettings.CanPrintStackedHeaders](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_CanPrintStackedHeaders) as `true`.

{% tabs %}
{% highlight c# %}
this.sfDataGrid.PrintSettings.CanPrintStackedHeaders = true;
{% endhighlight %}
{% endtabs %}

![Shows stacked headers printing in WPF DataGrid](Printing_images/Printing_img23.png)

## Page Settings

SfDataGrid provides various options to customize page settings using [SfDataGrid.PrintSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_PrintSettings) property of type [PrintSettings](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html).

### Orientation

SfDataGrid provides support to switch between Portrait (more rows but fewer columns) and Landscape (more columns but fewer rows) orientation while printing. Orientation can be changed by setting [PrintSettings.PrintPageOrientation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageOrientation) Property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageOrientation = PrintOrientation.Landscape;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

Print orientation can be changed in print preview at runtime by selecting from orientation drop-down in print preview.

![Page orientation options in print preview window for WPF DataGrid](Printing_images/Printing_img5.png)

### Page size

SfDataGrid provides support to change the page size. Page size can be changed by setting [PrintSettings.PrintPageWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageWidth) and [PrintSettings.PrintPageHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageHeight) properties.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageHeight = 800;            
dataGrid.PrintSettings.PrintPageWidth = 800;
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

Page size can be changed in print preview also by selecting from page-size drop-down which displays pre-defined page sizes. You can also manually enter custom page width and height in the editors below page-size drop-down and press OK to apply the custom width and height for the page.

![Page size options in print preview window for WPF DataGrid](Printing_images/Printing_img6.png)

### Page margin

SfDataGrid provides support to change the page margins to adjust content in printed page. Page margin can be changed by setting [PrintSettings.PrintPageMargin](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageMargin) property.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageMargin = new Thickness(5);
dataGrid.Print();
{% endhighlight %}
{% endtabs %}

Page margin can be changed in print preview also by selecting from pre-defined page margin from margin drop-down. You can manually enter custom margins in the editors below margin drop-down and press OK to apply the custom margin.

![Page margin options in print preview window for WPF DataGrid](Printing_images/Printing_img7.png)

## Setting Header and Footer

SfDataGrid provides a way to display additional content at the top (Header) or bottom (Footer) of the page while printing. This can be achieved by setting [PrintPageHeaderHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageHeaderHeight) , [PrintPageHeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageHeaderTemplate) , [PrintPageFooterHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageFooterHeight)  [PrintPageFooterTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageFooterTemplate) properties in [PrintSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_PrintSettings).

Steps to add page header while printing,

1. Create DataTemplate in `Application.Resources`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <DataTemplate x:Key="PageHeaderTempalte">
        <Grid Background="Gray">
            <TextBlock Text="Syncfusion" 
                       FontSize="18" 
                       FontWeight="Bold" 
                       Foreground="White" 
                       HorizontalAlignment="Center"/>
        </Grid>
    </DataTemplate>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

2.Set the above defined DataTemplate to [PrintSettings.PrintPageHeaderTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageHeaderTemplate) and assign value for [PrintSettings.PrintPageHeaderHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageHeaderHeight) property also.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageHeaderHeight = 30;
dataGrid.PrintSettings.PrintPageHeaderTemplate = Application.Current.Resources["PageHeaderTempalte"] as DataTemplate;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

3.Now run the application and you can see page header in all the pages. In the same way, you can set [PrintSettings.PrintPageFooterTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageFooterTemplate) also.

![Customized HeaderTemplate and HeaderHeight in print preview window for WPF DataGrid](Printing_images/Printing_img8.png)


N> [PrintManagerBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html) is the `DataContext` for [PrintPageControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPageControl.html), where the header and footer templates are loaded.

### Printing Current Date time and Page number

You can print current Date and Time at each page by setting the  [PrintPageFooterHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageFooterHeight)  [PrintPageFooterTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_PrintPageFooterTemplate) properties in [PrintSettings](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_PrintSettings).
 
You can get the page number from [PrintPageControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPageControl.html).

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <DataTemplate x:Key="PageFooterTempalte">
        <Grid>
            <TextBlock HorizontalAlignment="Center" 
                       FontSize="20" 
                       Text="{Binding Source={x:Static system:DateTime.Now}}"/>
            <TextBlock Margin="0,0,10,0"
                       HorizontalAlignment="Right"
                       VerticalAlignment="Center" FontSize="20">
                <TextBlock.Text>
                    <Binding Path="PageIndex"
                             RelativeSource="{RelativeSource Mode=FindAncestor,
                                                              AncestorType={x:Type syncfusion:PrintPageControl}}"
                             StringFormat="Page : {0}" />
                </TextBlock.Text>
            </TextBlock>
        </Grid>
    </DataTemplate>
</Application.Resources>
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.PrintPageFooterHeight = 30;
dataGrid.PrintSettings.PrintPageFooterTemplate = Application.Current.Resources["PageFooterTempalte"] as DataTemplate;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![Customized FooterTemplate and FooterHeight in print preview window for WPF DataGrid](Printing_images/Printing_img9.png)

## Different modes of printing for better performance

### Printing using drawing for better performance

When you require better performance and don’t want appearance settings (Background and Foreground) to be exported while printing then you can use this printing option by setting [PrintSettings.AllowPrintByDrawing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintByDrawing) property to `true`.
 
 
N> This is default print mode. For appearance customization of rows and cells while printing, refer [printing customization](#printing-customization) section.

 
### Printing using UIElement Rendering

When you want to print the SfDataGrid with same appearance settings as in the display (Background and Foreground) or with custom appearance by writing styles, then you can enable this print option by setting [PrintSettings.AllowPrintByDrawing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintByDrawing) property to `false`.

You can print SfDataGrid as it displayed in View by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintStyles) to `true`.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowPrintByDrawing = false;
dataGrid.PrintSettings.AllowPrintStyles = true;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

[GridHeaderCellControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridHeaderCellControl.html) style customized and the same style will be exported while printing by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintStyles) to `true`.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
     <Style TargetType="syncfusion:GridHeaderCellControl">
         <Setter Property="Background" Value="LightPink"/>            
     </Style>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

![Shows same style as in view for WPF DataGrid using AllowPrintStyles API while printing](Printing_images/Printing_img10.png)

#### Applying custom style

Custom styles can be applied while printing by setting [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintStyles) to `false` and writing style for below controls based on your requirement.

<table>
<tr>
<th>
Appearance to be customized
</th>
<th>
TargetType of Style
</th>
</tr>
<tr>
<td>
Header Cell
</td>
<td>
{{'[PrintHeaderCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintHeaderCell.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Normal Cells
</td>
<td>
{{'[PrintGridCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintGridCell.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Caption summary cells
</td>
<td>
{{'[PrintCaptionSummaryCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintCaptionSummaryCell.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Group summary cells
</td>
<td>
{{'[PrintGroupSummaryCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintGroupSummaryCell.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Table summary cells
</td>
<td>
{{'[PrintTableSummaryCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintTableSummaryCell.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
Unbound row cells
</td>
<td>
{{'[PrintUnboundRowCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintUnboundRowCell.html)'| markdownify }}
</td>
</tr>
</table>


To provide custom appearance for Header cells while printing, [PrintHeaderCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintHeaderCell.html) style is customized.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:PrintHeaderCell">
         <Setter Property="Background" Value="LightSkyBlue"/>            
    </Style>
</Application.Resources>
{% endhighlight %}
{% endtabs %}

To print SfDataGrid with custom styles, set [PrintSettings.AllowPrintByDrawing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintByDrawing) and [PrintSettings.AllowPrintStyles](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintSettings.html#Syncfusion_UI_Xaml_Grid_PrintSettings_AllowPrintStyles) properties to `false`.

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings = new PrintSettings();
dataGrid.PrintSettings.AllowPrintByDrawing = false;
dataGrid.PrintSettings.AllowPrintStyles = false;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![WPF DataGrid displaying custom style for using AllowPrintStyles API while printing](Printing_images/Printing_img11.png)

## Printing Customization
 
Printing operations can be customized by overriding [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html) and its available methods.
 
### Setting different Row Height
 
SfDataGrid allows you to set different Row height for specific rows while printing. You can achieve this by overriding the [GetRowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetRowHeight_System_Object_System_Int32_Syncfusion_UI_Xaml_Grid_RowType_) method in [PrintManagerBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html) class.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override double GetRowHeight(object record, int rowIndex, RowType type)
    {

        if (rowIndex != -1 && !(record is Group))

            if (rowIndex % 2 != 0)

                return 50.0;

        return base.GetRowHeight(record, rowIndex, type);
    }        
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![Customization of row height while printing in WPF DataGrid](Printing_images/Printing_img12.png)

### Hiding rows while printing
     
You can hide specific row by using [GetRowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetRowHeight_System_Object_System_Int32_Syncfusion_UI_Xaml_Grid_RowType_) method in [PrintManagerBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html) class and setting height as 0.

Here, unbound row is excluded while printing. Likewise, you can hide any row based on record and row index.

{% tabs %}
{% highlight c# %}
public class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override double GetRowHeight(object record, int rowIndex, RowType type)
    {

        if (record is GridUnBoundRow)
            return 0;

        return base.GetRowHeight(record, rowIndex, type);
    }        
}
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

### Setup columns to be printed

SfDataGrid allows you to exclude the columns while printing the grid. You can change the column list by overriding the [GetColumnNames](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetColumnNames) method in [PrintManagerBase](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html) class.

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{
 
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override List<string> GetColumnNames()
    {
        List<string> columnList = this.dataGrid.Columns.Select(x => x.MappingName).ToList();
        columnList.Remove("CustomerName");
        return columnList;
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

Here, `CustomerName` column is displayed in grid. But it is excluded while printing.

![Shows removal column while printing in WPF DataGrid](Printing_images/Printing_img13.png)

### Customize the header text while printing

SfDataGrid allows you to change column header text while printing the grid. You can change the Column header text by overriding the [GetColumnHeaderText](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetColumnHeaderText_System_String_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{
  
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override string GetColumnHeaderText(string mappingName)
    {
  
        if (mappingName == "OrderID")
            return "Order ID";
            
        return base.GetColumnHeaderText(mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

Here, OrderID column Header text is changed as `Order ID` while printing.

![customize the column header text while printing in WPF DataGrid](Printing_images/Printing_img14.png)

### Styling Rows when AllowPrintByDrawing enabled

You can apply row styles based on custom condition by overriding [OnRenderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_OnRenderCell_System_Windows_Media_DrawingContext_Syncfusion_UI_Xaml_Grid_RowInfo_Syncfusion_UI_Xaml_Grid_CellInfo_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html) class.

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{
 
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override void OnRenderCell(DrawingContext drawingContext, RowInfo  rowInfo, CellInfo cellInfo)
    {
 
        if (!(rowInfo.Record is RecordEntry))
        {
            base.OnRenderCell(drawingContext, rowInfo, cellInfo);
            return;
        }
        var rect = new Rect((cellInfo.CellRect).X, (cellInfo.CellRect).Y + 0.5,  (cellInfo.CellRect).Width, (cellInfo.CellRect).Height);
        
        if (((rowInfo.Record as RecordEntry).Data as OrderInfo).Country == "Germany")
            drawingContext.DrawGeometry(new SolidColorBrush(Colors.Bisque), new Pen(), new RectangleGeometry(rect));
            
        else if (((rowInfo.Record as RecordEntry).Data as OrderInfo).Country == "Mexico")
            drawingContext.DrawGeometry(new SolidColorBrush(Colors.LightSkyBlue), new Pen(), new RectangleGeometry(rect));
            
        base.OnRenderCell(drawingContext, rowInfo, cellInfo);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![Row styling with AllowPrintByDrawing enabled while printing in WPF DataGrid](Printing_images/Printing_img15.png)

### Styling Rows when AllowPrintByDrawing disabled

You can apply row styles based on custom logic by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintGridCell_System_Object_System_String_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{
 
    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string mappingName)
    {
 
        if (!(record is OrderInfo))
            return base.GetPrintGridCell(record, mappingName);

        if ((record as OrderInfo).Country == "Germany")
            return new PrintGridCell() { Background = new SolidColorBrush(Colors.Bisque) };
            
        else if ((record as OrderInfo).Country == "Mexico")
            return new PrintGridCell() { Background = new SolidColorBrush(Colors.LightSkyBlue) };
            
        return base.GetPrintGridCell(record, mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.AllowPrintByDrawing = false;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}


![Row styling with AllowPrintByDrawing disabled while printing in WPF DataGrid](Printing_images/Printing_img16.png)

<table>
<tr>
<th>
Appearance to be customized
</th>
<th>
Method
</th>
</tr>
<tr>
<td>
Header Cell
</td>
<td>
{{'[GetPrintHeaderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintHeaderCell_System_String_)'| markdownify }}
</td>
</tr>
<tr>
<td>
Normal Cells
</td>
<td>
{{'[GetPrintGridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintGridCell_System_Object_System_String_)'| markdownify }}
</td>
</tr>
<tr>
<td>
Caption summary cells
</td>
<td>
{{'[GetPrintCaptionSummaryCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintCaptionSummaryCell_System_Object_System_String_)'| markdownify }}
</td>
</tr>
<tr>
<td>
Group summary cells
</td>
<td>
{{'[GetPrintGroupSummaryCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintGroupSummaryCell_System_Object_System_String_)'| markdownify }}
</td>
</tr>
<tr>
<td>
Table summary cells
</td>
<td>
{{'[GetPrintTableSummaryCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintTableSummaryCell_System_Object_System_String_)'| markdownify }}
</td>
</tr>
<tr>
<td>
Unbound row cells
</td>
<td>
{{'[GetPrintUnboundRowCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintUnboundRowCell_System_Object_System_String_)'| markdownify }}
</td>
</tr>
</table>


### Setup alternate row style when AllowPrintByDrawing enabled

SfDataGrid allows you to apply alternative row style by overriding [OnRenderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_OnRenderCell_System_Windows_Media_DrawingContext_Syncfusion_UI_Xaml_Grid_RowInfo_Syncfusion_UI_Xaml_Grid_CellInfo_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override void OnRenderCell(DrawingContext drawingContext, RowInfo  rowInfo, CellInfo cellInfo)
    {
        var index = dataGrid.View.Records.IndexOfRecord(rowInfo.Record);
        var rect = new Rect((cellInfo.CellRect).X, (cellInfo.CellRect).Y + 0.5, (cellInfo.CellRect).Width, (cellInfo.CellRect).Height);
        
        if (index % 2 == 0)
            drawingContext.DrawGeometry(new SolidColorBrush(Colors.Bisque), new Pen(), new RectangleGeometry(rect));
            
        base.OnRenderCell(drawingContext, rowInfo, cellInfo);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}


![Alternate row styling with AllowPrintByDrawing enabled while printing in WPF DataGrid](Printing_images/Printing_img17.png)

### Setup alternate row style when AllowPrintByDrawing disabled

SfDataGrid allows you to apply alternative row style by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintGridCell_System_Object_System_String_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string  mappingName)
    {
        var index = dataGrid.View.Records.IndexOfRecord(record);
        
        if (index % 2 == 0)
            return new PrintGridCell() { Background = new SolidColorBrush(Colors.Bisque) };
            
        return base.GetPrintGridCell(record, mappingName);
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.AllowPrintByDrawing = false;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}


![Alternate row styling with AllowPrintByDrawing disabled while printing in WPF DataGrid](Printing_images/Printing_img18.png)

### Styling Columns when AllowPrintByDrawing enabled

You can apply column styles based on some conditions by overriding [OnRenderCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_OnRenderCell_System_Windows_Media_DrawingContext_Syncfusion_UI_Xaml_Grid_RowInfo_Syncfusion_UI_Xaml_Grid_CellInfo_), [GetFormattedText](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetFormattedText_Syncfusion_UI_Xaml_Grid_RowInfo_Syncfusion_UI_Xaml_Grid_CellInfo_System_String_) methods in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override void OnRenderCell(DrawingContext drawingContext, RowInfo  rowInfo, CellInfo cellInfo)
    {

        if (cellInfo.ColumnName == "OrderID" && rowInfo.Record != null)
        {
            var rect = new Rect((cellInfo.CellRect).X, (cellInfo.CellRect).Y + 0.5, (cellInfo.CellRect).Width, (cellInfo.CellRect).Height);
            drawingContext.DrawGeometry(new SolidColorBrush(Colors.LightGreen), new Pen(), new RectangleGeometry(rect));
        }
        
        base.OnRenderCell(drawingContext, rowInfo, cellInfo);
    }

    protected override FormattedText GetFormattedText(RowInfo rowInfo, CellInfo cellInfo, string cellValue)
    {
        var formattedText = base.GetFormattedText(rowInfo, cellInfo, cellValue);
        
        if (cellInfo.ColumnName == "OrderID" && rowInfo.Record != null)
            formattedText.SetFontStyle(FontStyles.Italic);
            
        return formattedText;
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}

![Column styling with AllowPrintByDrawing enabled while printing in WPF DataGrid](Printing_images/Printing_img19.png)

Here, OrderID column Font Style and Background are changed.

### Styling Columns when AllowPrintByDrawing disabled

You can apply column styles based on custom logic by overriding [GetPrintGridCell](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html#Syncfusion_UI_Xaml_Grid_GridPrintManager_GetPrintGridCell_System_Object_System_String_) method in [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html).

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    public override ContentControl GetPrintGridCell(object record, string mappingName)
    {

        if (mappingName == "OrderID")
            return new PrintGridCell() { Background = new  SolidColorBrush(Colors.LightGreen), FontStyle = FontStyles.Italic };
            
        return base.GetPrintGridCell(record, mappingName);          
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.PrintSettings.AllowPrintByDrawing = false;
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}


![Column styling with AllowPrintByDrawing disabled while printing in WPF DataGrid](Printing_images/Printing_img20.png)


N> [GetColumnWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetColumnWidth_System_String_) , [GetColumnTextWrapping](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetColumnTextWrapping_System_String_), [GetColumnTextAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetColumnTextAlignment_System_String_) and [GetColumnPadding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetColumnPadding_System_String_) methods are also used for column customization while printing.


### Printing Selected rows

Selected rows can be printed by overriding [GetSourceListForPrinting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html#Syncfusion_UI_Xaml_Grid_PrintManagerBase_GetSourceListForPrinting) method in [PrintManagerClass](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintManagerBase.html) class.

{% tabs %}
{% highlight c# %}
private class CustomPrintManager : GridPrintManager
{

    public CustomPrintManager(SfDataGrid grid)
        : base(grid)
    {
    }

    protected override IList GetSourceListForPrinting()
    {
        List<object> selectedRecords = new List<object>();
        var selectedRows = dataGrid.SelectionController.SelectedRows.ToList();

        foreach (var row in selectedRows)
        {

            if (row.IsAddNewRow || (row.NodeEntry != null && (!row.NodeEntry.IsRecords)))
                continue;

            if (row.IsUnBoundRow)
            {
                var _row = dataGrid.UnBoundRows.FirstOrDefault(r => r.Position == row.GridUnboundRowInfo.Position && r.ShowBelowSummary == row.GridUnboundRowInfo.ShowBelowSummary && r.RowIndex == row.GridUnboundRowInfo.RowIndex);
                selectedRecords.Add(_row);
            }

            else
                selectedRecords.Add(row.NodeEntry);
        }
        return selectedRecords;
    }
}
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
dataGrid.PrintSettings.PrintManagerBase = new CustomPrintManager(this.dataGrid);
dataGrid.ShowPrintPreview();
{% endhighlight %}
{% endtabs %}


![Print the selected items in WPF DataGrid](Printing_images/Printing_img21.png)


## Creating custom PrintPreview window

You can create custom print preview window by adding [PrintPreviewAreaControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPreviewAreaControl.html) to preview the view. [PrintManagerBase](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPreviewAreaControl.html#Syncfusion_UI_Xaml_Grid_PrintPreviewAreaControl_PrintManagerBase) will handle the printing operations and `PrintPreviewAreaControl` is responsible for preview. 

Steps to create `custom print preview` window.

1.Add [PrintPreviewAreaControl](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPreviewAreaControl.html)  and required controls to print or customize the print settings.
 
{% tabs %}
{% highlight xaml %}
 <Grid>
    <Grid Background="#FFF7F7F7">
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>

        <Border Background="#FFDBDBDB" DataContext="{Binding ElementName=PrintPreviewArea}">
            <StackPanel Margin="10,5"
                        HorizontalAlignment="Center"
                        Orientation="Horizontal">
                    <Button Height="38"
                        Margin="10,3"
                        Command="{Binding PrintCommand}"
                        Content="Print"
                        Style="{StaticResource PrintButtonStyle}"
                        ToolTip="Print" />
                </StackPanel>
        </Border>

        <syncfusion:PrintPreviewAreaControl x:Name="PrintPreviewArea" Grid.Row="1" />

    </Grid>
</Grid>
{% endhighlight %}
{% endtabs %}

2.Assign the instance of [GridPrintManager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridPrintManager.html) to [PrintPreviewAreaControl.PrintManagerBase ](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPreviewAreaControl.html#Syncfusion_UI_Xaml_Grid_PrintPreviewAreaControl_PrintManagerBase) property.

{% tabs %}
{% highlight c# %}
var window = new PreviewWindow
{
    WindowStartupLocation = WindowStartupLocation.CenterScreen,
};
window.PrintPreviewArea.PrintManagerBase = new GridPrintManager(dataGrid);
window.ShowDialog();
{% endhighlight %}
{% endtabs %}

3.You can customize print settings like scaling, Orientation at runtime by using [PrintPreviewAreaControl.PrintManagerBase](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.PrintPreviewAreaControl.html#Syncfusion_UI_Xaml_Grid_PrintPreviewAreaControl_PrintManagerBase) and it will be reflected it custom print preview window. 

{% tabs %}
{% highlight c# %}
this.PrintPreviewArea.PrintManagerBase.PrintScaleOption = PrintScaleOptions.FitAllRowsonOnePage;
this.PrintPreviewArea.PrintManagerBase.Print();
{% endhighlight %}
{% endtabs %}

![Custom print preview window in WPF DataGrid](Printing_images/Printing_img22.png)

You can get the sample for custom print preview [here](http://www.syncfusion.com/downloads/support/directtrac/general/CUSTOM~1272396097.ZIP).
