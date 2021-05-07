---
layout: post
title: Unbound Column in WPF DataGrid control | Syncfusion
description: Learn here all about Unbound Column support in Syncfusion WPF DataGrid (SfDataGrid) control, its elements and more details.
platform: wpf
control: SfDataGrid
documentation: ug
---

# Unbound Column in WPF DataGrid (SfDataGrid)

SfDataGrid allows you to add **additional columns** which are **not bound with data object** from underlying data source. You can add unbound column using [GridUnBoundColumn](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html) class. Unbound columns supports for sorting, filtering, grouping, exporting and printing as normal columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                                                       
                       AutoGenerateColumns="False" 
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridUnBoundColumn   Expression="UnitPrice*Discount"
                                                                        HeaderText="Discount Price"
                                                                        MappingName="DiscountPrice" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridUnBoundColumn() { HeaderText = "Discount Price", MappingName = "DiscountPrice", Expression = "UnitPrice*Discount" });
{% endhighlight %}
{% endtabs %}

![Displaying Unbound column in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img1.png)

N> It is mandatory to specify the `GridColumn.MappingName` for `GridUnBoundColumn` with some name to identify the column. It is not necessary to define name of field in the data object.

## Populating data for unbound column

You can populate the data for unbound column by setting [Expression](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html#Syncfusion_UI_Xaml_Grid_GridUnBoundColumn_Expression) or [Format](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html#Syncfusion_UI_Xaml_Grid_GridUnBoundColumn_Format) property or through [QueryUnBoundColumnValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

### Using Expression

You can specify the arithmetic or logic expression using `Expression` property to compute the display value. By default `GridUnBoundColumn` evaluates the expression with casing. You can disable the casing while evaluate the expression by setting [CaseSensitive](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html#Syncfusion_UI_Xaml_Grid_GridUnBoundColumn_CaseSensitive) property to `false`. 

Below are the list of Arithmetic and logical operations supported.

<table>
<tr>
<th>
Arithmetic operations
</th>
<th>
Operator
</th>
</tr>
<tr>
<td>
Add
</td>
<td>
+
</td>
</tr>
<tr>
<td>
Subtract
</td>
<td>
-
</td>
</tr>
<tr>
<td>
Multiply
</td>
<td>
*
</td>
</tr>
<tr>
<td>
Divide
</td>
<td>
/
</td>
</tr>
<tr>
<td>
Power
</td>
<td>
^
</td>
</tr>
<tr>
<td>
Mod
</td>
<td>
%
</td>
</tr>
<tr>
<td>
Greater Than
</td>
<td>
>
</td>
</tr>
<tr>
<td>
Less Than
</td>
<td>
<
</td>
</tr>
<tr>
<td>
Equal
</td>
<td>
=
</td>
</tr>
<tr>
<td>
GreaterThanOrEqual
</td>
<td>
>=
</td>
</tr>
<tr>
<td>
LessThanOrEqual
</td>
<td>
<=
</td>
</tr>
</table>

<table>
<tr>
<th>
Logical operations
</th>
<th>
Operators
</th>
</tr>
<tr>
<td>
AND
</td>
<td>
(char)135
</td>
</tr>
<tr>
<td>
OR
</td>
<td>
(char)136
</td>
</tr>
<tr>
<td>
NOT
</td>
<td>
(char)137
</td>
</tr>
</table>

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"                                                                       
                       AutoGenerateColumns="False" 
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridUnBoundColumn HeaderText="Unbound Column"
                                      MappingName="UnboundColumn" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
(this.dataGrid.Columns[3] as GridUnBoundColumn).Expression = "Discount * UnitPrice > 0" + (char)135 + "UnitPrice * Quantity > 100";
{% endhighlight %}
{% endtabs %}

![Displaying Unbound column using Expression in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img2.png)

### Using Format

You can format the values of other columns and display the formatted value in unbound column using [Format](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnBoundColumn.html#Syncfusion_UI_Xaml_Grid_GridUnBoundColumn_Format) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AutoGenerateColumns="False" 
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridUnBoundColumn Format="'{Discount}% for {OrderID}'"
                                      HeaderText="Discount Price"
                                      MappingName="DiscountPrice"/>
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
this.dataGrid.Columns.Add(new GridUnBoundColumn() { HeaderText = "Discount Price", MappingName = "DiscountPrice", Format = "'{Discount}% for {OrderID}'" });
{% endhighlight %}
{% endtabs %}

![Displaying Unbound column using Format in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img3.png)

### Using QueryUnBoundColumnValue event

You can populate the data for unbound column by handling the [QueryUnBoundColumnValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.
[GridUnBoundColumnEventArgs](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnboundColumnEventsArgs.html) of the `QueryUnBoundColumnValue` event provides the information about the cell triggered this event. [GridUnBoundColumnValueEventsArgs.OriginalSender](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridEventArgs.html#Syncfusion_UI_Xaml_Grid_GridEventArgs_OriginalSender) returns the DataGrid fired this event for DetailsView. 

You can get or set the `GridUnBoundColumnEventArgs.Value` property based on the [UnBoundAction](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnboundColumnEventsArgs.html#Syncfusion_UI_Xaml_Grid_GridUnboundColumnEventsArgs_UnBoundAction). 
* UnBoundAction - `QueryData` denotes the event triggered to query value and cell information.
* UnBoundAction - `CommitData` denotes the event triggered to save the edited value. 

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryUnboundColumnValue += dataGrid_QueryUnboundColumnValue;

void dataGrid_QueryUnboundColumnValue(object sender, GridUnboundColumnEventsArgs e)
{

    if (e.UnBoundAction == UnBoundActions.QueryData)
    {
        var unitPrice = Convert.ToDouble(e.Record.GetType().GetProperty("UnitPrice").GetValue(e.Record));
        var disCount = Convert.ToDouble(e.Record.GetType().GetProperty("Discount").GetValue(e.Record));
        var save = unitPrice * disCount;
        e.Value = save.ToString() + "$";
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying Unbound column with data populated using QueryUnBoundColumnValue event in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img4.png)

## Refreshing the unbound column at runtime

You can trigger the [QueryUnBoundColumnValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event or recalculate the value for the cells of unbound column at runtime by calling [UpdateUnboundColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Helpers.GridHelper.html#Syncfusion_UI_Xaml_Grid_Helpers_GridHelper_UpdateUnboundColumn_Syncfusion_UI_Xaml_Grid_SfDataGrid_System_Object_System_String_) method.

{% tabs %}
{% highlight c# %}
this.dataGrid.CurrentCellEndEdit +=dataGrid_CurrentCellEndEdit;

void dataGrid_CurrentCellEndEdit(object sender, CurrentCellEndEditEventArgs args)
{
    this.dataGrid.UpdateUnboundColumn(this.dataGrid.CurrentItem, "Discount");           
}
{% endhighlight %}
{% endtabs %}

## Editing unbound column

### Cancel the editing for unbound column cell

You can cancel the editing of unbound column cell by handling the [SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event.

{% tabs %}
{% highlight c# %}
dataGrid.CurrentCellBeginEdit += dataGrid_CurrentCellBeginEdit;

void dataGrid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
{                                                 
    args.Cancel = args.Column is GridUnBoundColumn;    
}
{% endhighlight %}
{% endtabs %}

### Saving edited value of unbound column using QueryUnBoundColumnValue.

You can get the edited value of unbound column from [GridUnboundColumnEventsArgs.Value](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridUnboundColumnEventsArgs.html#Syncfusion_UI_Xaml_Grid_GridUnboundColumnEventsArgs_Value) property of [QueryUnBoundColumnValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html) event when UnBoundAction is `CommitData`.

{% tabs %}
{% highlight c# %}
this.dataGrid.QueryUnboundColumnValue += dataGrid_QueryUnboundColumnValue;

void dataGrid_QueryUnboundColumnValue(object sender, GridUnboundColumnEventsArgs e)
{

    if(e.UnBoundAction == UnBoundActions.CommitData)
    {
        var editedValue = e.Value;
    }
}
{% endhighlight %}
{% endtabs %}

### Read unbound column values

You can get the value of `GridUnBoundColumn` using [GetUnBoundCellValue](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_GetUnBoundCellValue_Syncfusion_UI_Xaml_Grid_GridColumn_System_Object_) method.

{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.Grid.Helpers;
this.dataGrid.CurrentCellValueChanged += dataGrid_CurrentCellValueChanged;

void dataGrid_CurrentCellValueChanged(object sender, CurrentCellValueChangedEventArgs args)
{
    var updateValue = this.dataGrid.GetUnBoundCellValue(dataGrid.Columns[5], this.dataGrid.CurrentItem); 
}
{% endhighlight %}
{% endtabs %}

## Styling unbound column

You can customize the style of unbound column by writing style of TargetType [GridCell](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridCell.html) or setting [GridColumn.CellStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellStyle) property.

In the below code snippet, Foreground of the cells in GridUnBoundColumn changed based on its content.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
        <local:UnboundCellStyleConverter x:Key="unboundCellStyleConverter"/>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"                                                                       
                       AutoGenerateColumns="False" 
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.Columns>
                <syncfusion:GridUnBoundColumn HeaderText="Discount Price"
                                              MappingName="DiscountPrice">
                    <syncfusion:GridUnBoundColumn.CellStyle>
                        <Style TargetType="syncfusion:GridCell">
                           <Setter  Property="Foreground"  Value="{Binding   RelativeSource={RelativeSource Self}, Converter={StaticResource unboundCellStyleConverter}}" />
                        </Style>
                    </syncfusion:GridUnBoundColumn.CellStyle>
                </syncfusion:GridUnBoundColumn>            
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class UnboundCellStyleConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        var unboundCell = value as GridCell;
        var unboundValue = (unboundCell.Content as TextBlock).Text;
        var data = System.Convert.ToInt16(unboundValue.Substring(0,unboundValue.Length -1));

        if(data > 30)
            return new SolidColorBrush(Colors.DarkGreen);
        return new SolidColorBrush(Colors.Red);
    }

    public object ConvertBack(object value, Type targetType, object parameter, System.Globalization.CultureInfo culture)
    {
        return value;
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying Unbound column styling in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img5.png)

You can refer the [Styling](http://help.syncfusion.com/wpf/sfdatagrid/column-types#styling-gridcolumn) section of `GridColumn` for more information.

## Customize the Unbound column behavior

SfDataGrid allows you to customize the operations like key navigation and UI related interactions by overriding the corresponding renderer associated with the unbound column.  
Below table lists the available cell types for unbound column.

<table>
<tr>
<th>
Cell Type
</th>
<th>
Renderer
</th>
</tr>
<tr>
<td>
UnBoundTemplateColumn
</td>
<td>
{{'[GridUnBoundCellTemplateRenderer](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Cells.GridUnBoundCellTemplateRenderer.html)'| markdownify }}
</td>
</tr>
<tr>
<td>
UnBoundTextColumn
</td>
<td>
{{'[GridUnBoundCellTextBoxRenderer](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Cells.GridUnBoundCellTextBoxRenderer.html)'| markdownify }}
</td>
</tr>
</table>

If the [GridUnBoundColumn.EditTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridTemplateColumn.html#Syncfusion_UI_Xaml_Grid_GridTemplateColumn_EditTemplate) not defined then the `UnboundTextColumn` set as default cell type of `GridUnBoundColumn`. 
If `GridUnBoundColumn.EditTemplate` property defined then `UnBoundTemplateColumn` set as cell type of `GridUnBoundColumn`.

### Overriding Existing CellType

You can customize the unbound row cell behavior by overriding existing renderer and replace the default one in [SfDataGrid.CellRenderers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CellRenderers).

In the below code snippet, [GridUnBoundCellTextBoxRenderer](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Cells.GridUnBoundCellTextBoxRenderer.html) is customized to change the foreground and replaced the default renderer with customized renderer in `SfDataGrid.CellRenderer` collection.

{% tabs %}
{% highlight c# %}
this.dataGrid.CellRenderers.Remove("UnBoundTextColumn");
this.dataGrid.CellRenderers.Add("UnBoundTextColumn", new GridUnBoundCellTextBoxRendererExt());

public class GridUnBoundCellTextBoxRendererExt : GridUnBoundCellTextBoxRenderer
{

    public override void OnInitializeDisplayElement(DataColumnBase dataColumn, TextBlock uiElement, object dataContext)
    {
        object cellValue = null;

        if (dataContext != null)
            cellValue = DataGrid.GetUnBoundCellValue(dataColumn.GridColumn, dataContext);
        uiElement.Text = cellValue == null ? string.Empty : cellValue.ToString(); ;
        uiElement.Foreground = new SolidColorBrush(Colors.Blue);
    }

    public override void OnInitializeEditElement(DataColumnBase dataColumn, TextBox uiElement, object dataContext)
    {                
        object cellValue = null;

        if (dataContext != null)
            cellValue = DataGrid.GetUnBoundCellValue(dataColumn.GridColumn, dataContext);
        uiElement.Text = cellValue == null ? string.Empty : cellValue.ToString();        
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying unbound column behavior customization in WPF SfDataGrid](Unbound-Column_images/Unbound-Column_img6.png)

### Custom Renderer

You can change the renderer of unbound column by removing the predefined cell type value from [CellRenderers](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfDataGrid.html#Syncfusion_UI_Xaml_Grid_SfDataGrid_CellRenderers) collection and add the newly derived renderer from [GridVirtualizingCellRenderer](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.Cells.GridVirtualizingCellRenderer%602.html). Refer the [Create the renderer for existing column section](http://help.syncfusion.com/wpf/sfdatagrid/column-types#create-the-renderer-of-existing-column) for more information to create the custom renderer in columns section.

## Templating unbound column

You can load any WPF control in the display mode for `GridUnBoundColumn` by setting [GridColumn.CellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.GridColumnBase.html#Syncfusion_UI_Xaml_Grid_GridColumnBase_CellTemplate) property. In edit mode, corresponding editor will be loaded based on column type. You can refer the [CellTemplate](http://help.syncfusion.com/wpf/sfdatagrid/column-types#celltemplate-in-gridcolumn) section of `GridColumn` and [GridTemplateColumn](http://help.syncfusion.com/wpf/sfdatagrid/column-types#gridtemplatecolumn) for more information.
