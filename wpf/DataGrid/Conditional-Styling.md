---
layout: post
title: ConditionalStyling | DataGrid | WPF | Syncfusion
description: How to apply conditional styling in SfDataGrid
platform: wpf
control: SfDataGrid
documentation: ug
---

# Conditional Styling

You can style the SfDataGrid and its inner elements conditionally based on data in three ways,

1. Using Converter
2. Using Data Triggers
3. Using StyleSelector 

<table>
<tr>
<td>
{{'**Styling ways**'| markdownify }}
</td>
<td>
{{'**Performance details**'| markdownify }}
</td>
</tr>
<tr>
<td>
Using Converter
</td>
<td>
Provide good performance when compared other two ways.
</td>
</tr>
<tr>
<td>
Using Data Triggers
</td>
<td>
When compared to converter, performance is slow while styling more number of columns or rows.
</td>
</tr>
<tr>
<td>
Using StyleSelector
</td>
<td>
It affects scrolling performance while styling more number of columns based on number of columns visible.
</td>
</tr>
</table>

## Cells

### Styling cells using Converter

The record cells ([GridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCell.html)) can be customized conditionally by changing its property value based on `cell value` or `data object` using `converter`. 

Here, `GridCell` background is changed using `converter`, where converter returns the value based on `OrderID` property of underlying record.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
</Window.Resources>

<syncfusion:GridTextColumn MappingName="TotalPrice">
    <syncfusion:GridTextColumn.CellStyle>
        <Style TargetType="syncfusion:GridCell">
            <Setter Property="Background" Value="{Binding Path=OrderID,Converter={StaticResource converter}}"/>
        </Style>
    </syncfusion:GridTextColumn.CellStyle>
</syncfusion:GridTextColumn>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        int input = (int)value;

      //custom condition is checked based on data.

        if (input < 1003)
            return new SolidColorBrush(Colors.LightBlue);

        else if (input < 1007)
            return new SolidColorBrush(Colors.Bisque);

        else
            return DependencyProperty.UnsetValue;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying cell styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img1.png)

### Styling cells based on record using Converter

You can also style the cells based on record instead of passing single property to converter, where `converter` returns the value based on underlying record. This can be assigned to `GridColumn.CellStyle` to style the column based on other column properties.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridCell">
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}" />

{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var data = value as OrderInfo;

        //custom condition is checked based on data.

        if (data.OrderID < 1003)
            return new SolidColorBrush(Colors.LightBlue);

        else if (data.OrderID < 1007)
            return new SolidColorBrush(Colors.Bisque);

        else
            return DependencyProperty.UnsetValue;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying cell styling based on record using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img2.png)

### Styling cells using Style.Triggers

The record cells ([GridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCell.html)) can be customized by setting [Style.Triggers](https://msdn.microsoft.com/en-us/library/system.windows.style.triggers(v=vs.110).aspx) that apply property values based on specified conditions. Multiple conditions can be specified by setting [MultiDataTrigger](https://msdn.microsoft.com/en-us/library/system.windows.multidatatrigger(v=vs.110).aspx).

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn MappingName="OrderID" >
    <syncfusion:GridTextColumn.CellStyle>
        <Style TargetType="syncfusion:GridCell">
            <Style.Triggers>
                <!--Background property set based on cell content-->
                <DataTrigger Binding="{Binding Path=OrderID}" Value="1001">
                    <Setter Property="Background" Value="Bisque" />
                </DataTrigger>
                <!--Background property set based on multiple conditions-->
                <MultiDataTrigger>
                    <MultiDataTrigger.Conditions>
                        <Condition Binding="{Binding Path=OrderID}" Value="1008" />
                        <Condition Binding="{Binding Path=CustomerID}" Value="BOLID" />
                    </MultiDataTrigger.Conditions>
                    <Setter Property="Background" Value="LightBlue" />
                </MultiDataTrigger>
            </Style.Triggers>
        </Style>
    </syncfusion:GridTextColumn.CellStyle>
</syncfusion:GridTextColumn>
{% endhighlight %}
{% endtabs %}

Here, GridCell’s are conditionally customized based on `OrderID` value.

![Displaying cell styling using Style.Triggers in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img3.png)

### Styling cells using StyleSelector

The record cells ([GridCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCell.html)) can be customized conditionally based on data by setting [SfDataGrid.CellStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~CellStyleSelector.html) property and the particular column record cells can be customized by setting [GridColumn.CellStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridColumnBase~CellStyleSelector.html) property and you can get the container as `GridCell` in the StyleSelector.

N> `GridColumn.CellStyleSelector` takes higher priority than `SfDataGrid.CellStyleSelector` property.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
         <local:SelectorClass x:Key="styleSelector"/>
    <Style x:Key="redCellStyle" TargetType="syncfusion:GridCell">
        <Setter Property="Foreground" Value="Red" />
    </Style>
    <Style x:Key="blueCellStyle" TargetType="syncfusion:GridCell">
        <Setter Property="Foreground" Value="DarkBlue" />
    </Style>    
</Application.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
        ItemsSource="{Binding Orders}" CellStyleSelector="{StaticResource styleSelector}"/>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var data = item as OrderInfo;

        if (data != null && ((container as GridCell).ColumnBase.GridColumn.MappingName == "TotalPrice"))
        {

            //custom condition is checked based on data.

            if (data.TotalPrice < 1005)
                return App.Current.Resources["redCellStyle"] as Style;
            return App.Current.Resources["blueCellStyle"] as Style;
        }
        return base.SelectStyle(item, container);
    }
}
{% endhighlight %}
{% endtabs %}

Here, GridCell’s are customized based on `TotalPrice` property of underlying record.

![Displaying cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img4.png)

## Rows

### Styling rows using Converter

The record rows ([VirtualizingCellsControl](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html) ) can be customized conditionally by changing its property value based on ‘cell value’ or ‘data object’ by using `converter`, where converter returns the value based on Underlying record.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}" />
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
ItemsSource="{Binding Orders}"/>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var input = (value as OrderInfo).TotalPrice;

       //custom condition is checked based on data.

        if (input < 1003)
            return new SolidColorBrush(Colors.Bisque);

        else if (input < 1007)
            return new SolidColorBrush(Colors.LightBlue);

        else
            return DependencyProperty.UnsetValue;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, rows are customized based on `TotalPrice` property of underlying record.

![Displaying row styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img5.png)

### Styling rows using StyleSelector

The record rows ([VirtualizingCellsControl](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.VirtualizingCellsControl.html) ) can be customized conditionally based on data by setting [SfDataGrid.RowStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~RowStyleSelector.html) property and you can get the container as `VirtualizingCellsControl` in StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style x:Key="rowStyle1" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Bisque" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Aqua" />
    </Style>
</Application.Resources>

<Window.Resources>
    <local:CustomRowStyleSelector x:Key="rowStyleSelector" />
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}"
                       RowStyleSelector="{StaticResource rowStyleSelector}"/>
{% endhighlight %}
{% highlight c# %}
public class CustomRowStyleSelector : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var row = (item as DataRowBase).RowData;
        var data = row as OrderInfo;

        if (data.TotalPrice < 1004)
            return App.Current.Resources["rowStyle1"] as Style;
        return App.Current.Resources["rowStyle2"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, rows are customized based on `TotalPrice` property of underlying record.

![Displaying row styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img6.png)

### Styling Alternate Rows

The appearance of alternating rows can be customized conditionally based on data by setting [SfDataGrid.AlternatingRowStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~AlternatingRowStyleSelector.html) property.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style x:Key="rowStyle1" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Bisque" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:VirtualizingCellsControl">
        <Setter Property="Background" Value="Aqua" />
    </Style>
</Application.Resources>

<Window.Resources>
    <local:CustomRowStyleSelector x:Key="alternatingRowStyleSelector" />
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}"                             
                       AlternatingRowStyleSelector="{StaticResource alternatingRowStyleSelector}"/>
{% endhighlight %}
{% highlight c# %}
public class CustomRowStyleSelector : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var row = (item as DataRowBase).RowData;
        var data = row as OrderInfo;

        // Applying alternating background for rows.

        if (data.OrderID < 1006)
            return App.Current.Resources["rowStyle1"] as Style;
        return App.Current.Resources["rowStyle2"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, alternating rows are customized based on `OrderID` property of underlying record.

![Displaying alternate row styling using AlternatingRowStyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img7.png)

## CaptionSummaryCell

### Styling caption summary cell using Converter

The appearance of caption summary cell can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value. 

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridCaptionSummaryCell">
        <Setter Property="Foreground" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
        <syncfusion:SfDataGrid.CaptionSummaryRow>
            <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                <syncfusion:GridSummaryRow.SummaryColumns>
                    <syncfusion:GridSummaryColumn Name="price"
                                                  Format="'{Sum:c}'"
                                                  MappingName="TotalPrice"
                                                  SummaryType="DoubleAggregate" />
                    <syncfusion:GridSummaryColumn Name="customerID"
                                                  Format="'{Count:c}'"
                                                  MappingName="CustomerID"
                                                  SummaryType="CountAggregate" />
                </syncfusion:GridSummaryRow.SummaryColumns>
            </syncfusion:GridSummaryRow>
        </syncfusion:SfDataGrid.CaptionSummaryRow>
    </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as Group).SummaryDetails.SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 1005)
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.DarkBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary cells are customized based on `TotalPrice` summary value.

![Displaying caption summary cell styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img8.png)

### Styling caption summary using StyleSelector

The appearance of caption summary cell can be customized conditionally based on summary value by setting [SfDataGrid.CaptionSummaryCellStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~CaptionSummaryCellStyleSelector.html) and you can get the container as GridCaptionSummaryCell using StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridCaptionSummaryCell" x:Key="captionSummaryStyle ">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="selector"/>
</Window.Resources>	

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       CaptionSummaryCellStyleSelector="{StaticResource  selector}"
                       ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:c}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var summaryValue = (item as Group).SummaryDetails.SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 0)
            return App.Current.Resources["captionSummaryStyle"] as Style;
        return base.SelectStyle(item, container);
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary cells are customized based on `TotalPrice` summary value.

![Displaying caption summary cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img9.png)

### Styling caption summary cell based on column

The caption summary cells can be conditionally customized summary column. 

Here, caption summary cells are customized based on `TotalPrice` summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridCaptionSummaryCell" x:Key="captionSummaryStyle ">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="selector"/>
</Window.Resources>	

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       CaptionSummaryCellStyleSelector="{StaticResource  selector}"
                       ItemsSource="{Binding Orders}">

    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow ShowSummaryInRow="False">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:c}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var cell = container as GridCaptionSummaryCell;

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
        {
            var groupKey = (int)(item as Group).Key;

            //custom condition is checked.

            if (groupKey < 0)
                return App.Current.Resources["captionSummaryStyle"] as Style;
        }
        return null;
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying caption summary cell styling based on column using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img10.png)

## CaptionSummaryRow

### Styling caption summary row using Converter

The appearance of caption summary row can be customized conditionally based on summary value by using `converter`, where converter returns the value based on summary value. 

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price : {price}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:c}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as Group).SummaryDetails.SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 1005)
            return new SolidColorBrush(Colors.LightBlue);
        return new SolidColorBrush(Colors.Bisque);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized based on `TotalPrice` summary value.

![Displaying caption summary row styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img11.png)

### Styling caption summary row using StyleSelector

In another way, appearance of caption summary row can be customized conditionally based on summary value by setting [SfDataGrid.CaptionSummaryRowStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~CaptionSummaryRowStyleSelector.html) and you can get the container as `CaptionSummaryRowControl` in StyleSelector.

Here, caption summary rows are customized where [group key](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Data.WPF~Syncfusion.Data.Group~Key.html) value is negative.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:CaptionSummaryRowControl" x:Key="captionSummaryStyle">
        <Setter Property="Background" Value="Bisque"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>    
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       CaptionSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
    <syncfusion:SfDataGrid.CaptionSummaryRow>
        <syncfusion:GridSummaryRow Title="Total Price : {price}" ShowSummaryInRow="True">
            <syncfusion:GridSummaryRow.SummaryColumns>
                <syncfusion:GridSummaryColumn Name="price"
                                              Format="'{Sum:c}'"
                                              MappingName="TotalPrice"
                                              SummaryType="DoubleAggregate" />
                <syncfusion:GridSummaryColumn Name="customerID"
                                              Format="'{Count:c}'"
                                              MappingName="CustomerID"
                                              SummaryType="CountAggregate" />
            </syncfusion:GridSummaryRow.SummaryColumns>
        </syncfusion:GridSummaryRow>
    </syncfusion:SfDataGrid.CaptionSummaryRow>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{
    public override Style SelectStyle(object item, DependencyObject container)
    {
        var row = (item as SpannedDataRow).RowData;
        var groupKey = (int)(row as Group).Key;        
        //custom condition is checked.
        if (groupKey < 0)
            return App.Current.Resources["captionSummaryStyle"] as Style;
        return null;
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized based on `TotalPrice` summary value.

![Displaying caption summary row styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img12.png)

### Styling caption summary row based on grouping level

The appearance of caption summary row can be conditionally customized based on [grouping level](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.DataRowBase~Level.html) using StyleSelector. 

{% tabs %}
{% highlight xaml %}
<Application.Resources>

    <Style x:Key="rowStyle1" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightPink" />
        <Setter Property="FontSize" Value="16" />
    </Style>
    <Style x:Key="rowStyle2" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightSteelBlue" />
        <Setter Property="FontStyle" Value="Italic" />
    </Style>
    <Style x:Key="rowStyle3" TargetType="syncfusion:CaptionSummaryRowControl">
        <Setter Property="Background" Value="LightGreen" />
    </Style>

</Application.Resources>

<Window.Resources>
    <local:CustomCaptionSummaryRowStyleSelector x:Key="styleSelector" />
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       CaptionSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}"
                       ShowGroupDropArea="True">
{% endhighlight %}
{% highlight c# %}
public class CustomCaptionSummaryRowStyleSelector : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var dataRow = item as DataRowBase;
        var level = dataRow.Level;

        //based on group levels, style applied to CaptionSummaryRow

        if (level == 1)
            return App.Current.Resources["rowStyle1"] as Style;

        else if (level == 2)
            return App.Current.Resources["rowStyle2"] as Style;

        else if (level == 3)
            return App.Current.Resources["rowStyle3"] as Style;
        return base.SelectStyle(item, container);
    }
}
{% endhighlight %}
{% endtabs %}

Here, caption summary rows are customized based on `grouping level` (example: level1, level2, level3, etc.).

![Displaying caption summary row styling based on group level in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img13.png)

## GroupSummaryCell

Group summary cells can be customized conditionally by getting particular summary value from [SummaryValues](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Data.WPF~Syncfusion.Data.SummaryRecordEntry~SummaryValues.html) through converter or style selector. Likewise, you can also customize the group summary cell based on various properties exposed in [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow_members.html) (example: [ShowSummaryInRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow~ShowSummaryInRow.html) property).

### Styling group summary cell using Converter

The appearance of group summary cell can be customized conditionally based on summary value by using ‘converter’, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridGroupSummaryCell">
        <Setter Property="Foreground" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
         <syncfusion:SfDataGrid.GroupSummaryRows>
                <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
                <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.GroupSummaryRows>
  </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);      
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.DarkBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary cells are customized based on `TotalPrice` summary value.

![Displaying group summary cell styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img14.png)

### Styling group summary cell using StyleSelector

The appearance of group summary cell can be customized conditionally based on summary value by setting [SfDataGrid.GroupSummaryCellStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GroupSummaryCellStyleSelector.html) and you can get the container as `GridGroupSummaryCell` in StyleSelector.

Here, group summary cells are customized based on summary values whether it’s positive or negative.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary1">
        <Setter Property="Background" Value="Red"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>        
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ShowGroupDropArea="True"
                       GroupSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.GroupSummaryRows>
                <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
                <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.GroupSummaryRows>
     </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ((double)calculatedValue < 0)
            return App.Current.Resources["customGroupSummary1"] as Style;

        return App.Current.Resources["customGroupSummary"] as Style;                 
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary cells are customized based on `TotalPrice` summary value.

![Displaying group summary cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img15.png)

### Styling group summary cell based on column

The group summary cells can be conditionally customized based on summary column. 

Here, group summary cells are customized based on `TotalPrice` summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
    <Style TargetType="syncfusion:GridGroupSummaryCell" x:Key="customGroupSummary1">
        <Setter Property="Background" Value="Red"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>        
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ShowGroupDropArea="True"
                       GroupSummaryCellStyleSelector="{StaticResource styleSelector}"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.GroupSummaryRows>
                <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
                <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.GroupSummaryRows>
     </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var cell = container as GridGroupSummaryCell;

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
        {            
            var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
            var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
            var calculatedValue = aggregateValue.Value;

            //custom condition is checked.

            if (aggregateValue.Key != "Count" && (double)calculatedValue < 0)
                return App.Current.Resources["customGroupSummary1"] as Style;
        }
        return App.Current.Resources["customGroupSummary"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying group summary cell styling based on column in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img16.png)

## GroupSummaryRow

Group summary row can be customized conditionally by getting particular summary value from [SummaryValues](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Data.WPF~Syncfusion.Data.SummaryRecordEntry~SummaryValues.html) through `converter` or `style selector`. Likewise, you can also customize the group summary row based on various properties exposed in [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow_members.html) (example: [ShowSummaryInRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow~ShowSummaryInRow.html) property).

### Styling group summary row using Converter

The appearance of group summary row can be customized conditionally based on summary value by using ‘converter’, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GroupSummaryRowControl">
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.GroupSummaryRows>
                <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
                <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.GroupSummaryRows>
    </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);      
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.LightBlue);
        return new SolidColorBrush(Colors.Bisque);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary rows are customized based on `TotalPrice` summary value.

![Displaying group summary row styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img17.png)

### Styling group summary row using StyleSelector

The appearance of group summary row can be customized conditionally based on summary value by setting [SfDataGrid.GroupSummaryRowStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~GroupSummaryRowStyleSelector.html) and you can get the container as `GridGroupSummaryRowControl` in StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GroupSummaryRowControl" x:Key="customGroupSummary ">
        <Setter Property="Background" Value="LightBlue"/>
    </Style>
    <Style TargetType="syncfusion:GroupSummaryRowControl" x:Key="customGroupSummary1">
        <Setter Property="Background" Value="Yellow"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>    
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       GroupSummaryRowStyleSelector="{StaticResource styleSelector}"
                       ShowGroupDropArea="True"
                       ItemsSource="{Binding Orders}">
            <syncfusion:SfDataGrid.GroupSummaryRows>
                <syncfusion:GridSummaryRow ShowSummaryInRow="False">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
                <syncfusion:GridSummaryRow Title="TotalPrice:  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.GroupSummaryRows>
    </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var summaryRecordEntry = (item as SpannedDataRow).RowData;
        var summaryValue = (summaryRecordEntry as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if ( (double)calculatedValue < 0)
            return App.Current.Resources["customGroupSummary1"] as Style;

        return App.Current.Resources["customGroupSummary"] as Style;                 
    }
}
{% endhighlight %}
{% endtabs %}

Here, group summary rows are customized based on `TotalPrice` summary value whether it’s positive or negative.

![Displaying group summary cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img18.png)

## TableSummaryCell

Table summary cells can be customized conditionally by getting particular summary value from [SummaryValues](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Data.WPF~Syncfusion.Data.SummaryRecordEntry~SummaryValues.html) through `converter` or `style selector`. Likewise, you can also customize the table summary cell based on various properties exposed in [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow_members.html) (example: [ShowSummaryInRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow~ShowSummaryInRow.html) property).

### Styling table summary cell using Converter

The appearance of table summary cell can be customized conditionally based on summary value using `converter`, where converter returns the value based on summary value. 

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:GridTableSummaryCell">
        <Setter Property="Foreground" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ShowRowHeader="True"
                       ItemsSource="{Binding Orders}">
              <syncfusion:SfDataGrid.TableSummaryRows>
                <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
                    <syncfusion:GridTableSummaryRow.SummaryColumns>

                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />

                    </syncfusion:GridTableSummaryRow.SummaryColumns>
                </syncfusion:GridTableSummaryRow>

                <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="count"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />

                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.TableSummaryRows>
        </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);      
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.Red);
        return new SolidColorBrush(Colors.LightBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary cells are customized based on `TotalPrice` summary value.

![Displaying table summary cell styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img19.png)

### Styling table summary cell using StyleSelector

The appearance of table summary cell can be customized conditionally based on summary value by setting [SfDataGrid.TableSummaryCellStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~TableSummaryCellStyleSelector.html) and you can get the container as GridTableSummaryCell in StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary1">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>        
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"    
                       ShowRowHeader="True"            
                       ItemsSource="{Binding Orders}"
                       TableSummaryCellStyleSelector="{StaticResource styleSelector}">
           <syncfusion:SfDataGrid.TableSummaryRows>
                <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
                    <syncfusion:GridTableSummaryRow.SummaryColumns>

                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />

                    </syncfusion:GridTableSummaryRow.SummaryColumns>
                </syncfusion:GridTableSummaryRow>

                <syncfusion:GridSummaryRow Title="Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>                        
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />

                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.TableSummaryRows>
        </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var summaryValue = (item as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;
        var cell = container as GridTableSummaryCell;

        //custom condition is checked.

        if ((double)calculatedValue < 8500 && cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["customTableSummary"] as Style;

        return App.Current.Resources["customTableSummary1"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary cells are customized based on `TotalPrice` summary value.

![Displaying table summary cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img20.png)

### Styling table summary cell based on column

The table summary cells can be conditionally customized based on summary column.

Here, table summary cells are customized based on `TotalPrice` summary column.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary">
        <Setter Property="Foreground" Value="Red"/>
    </Style>
    <Style TargetType="syncfusion:GridTableSummaryCell" x:Key="customTableSummary1">
        <Setter Property="Foreground" Value="DarkBlue"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>        
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"    
                       ShowRowHeader="True"            
                       ItemsSource="{Binding Orders}"
                       TableSummaryCellStyleSelector="{StaticResource styleSelector}">
           <syncfusion:SfDataGrid.TableSummaryRows>
                <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
                    <syncfusion:GridTableSummaryRow.SummaryColumns>

                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />

                    </syncfusion:GridTableSummaryRow.SummaryColumns>
                </syncfusion:GridTableSummaryRow>

                <syncfusion:GridSummaryRow Title="Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>                        
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />

                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.TableSummaryRows>
        </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var cell = container as GridTableSummaryCell;

        // column name is checked.

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["TableSummaryStyle1"] as Style;
        return App.Current.Resources["TableSummaryStyle2"] as Style;

    }
}
{% endhighlight %}
{% endtabs %}

![Displaying table summary cell styling based on column in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img21.png)

## TableSummaryRow

Table summary rows can be customized conditionally by getting particular summary value from [SummaryValues](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Data.WPF~Syncfusion.Data.SummaryRecordEntry~SummaryValues.html) through converter or style selector. Likewise, you can also customize the table summary row based on various properties exposed in [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow_members.html) (example: [ShowSummaryInRow](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridSummaryRow~ShowSummaryInRow.html) property).

### Styling table summary row using Converter

The appearance of table summary row can be customized conditionally based on summary value using `converter`, where converter returns the value based on summary value.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <local:ColorConverter x:Key="converter"/>
    <Style TargetType="syncfusion:TableSummaryRowControl">
        <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}"/>
    </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ShowRowHeader="True"
                       ItemsSource="{Binding Orders}">

{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var summaryValue = (value as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);      
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 1500)
            return new SolidColorBrush(Colors.Bisque);
        return new SolidColorBrush(Colors.LightBlue);
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary rows are customized based on `TotalPrice` summary value.

![Displaying table summary row styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img22.png)

### Styling table summary row using StyleSelector

The appearance of table summary row can be customized conditionally based on summary value by setting [SfDataGrid.TableSummaryRowStyleSelector](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.SfDataGrid~TableSummaryRowStyleSelector.html) and you can get the container as `GridTableSummaryRowControl` in StyleSelector.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style TargetType="syncfusion:TableSummaryRowControl" x:Key="tableSummaryRowStyle">
        <Setter Property="Background" Value="Bisque"/>
    </Style>
    <Style TargetType="syncfusion:TableSummaryRowControl" x:Key="tableSummaryRowStyle1">
        <Setter Property="Background" Value="LightBlue"/>
    </Style>
</Application.Resources>

<Window.Resources>
    <local:SelectorClass x:Key="styleSelector"/>    
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"             
                       ShowRowHeader="True"   
                       ItemsSource="{Binding Orders}" 
                       TableSummaryRowStyleSelector="{StaticResource styleSelector}" >
            <syncfusion:SfDataGrid.TableSummaryRows>
                <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
                    <syncfusion:GridTableSummaryRow.SummaryColumns>

                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />

                    </syncfusion:GridTableSummaryRow.SummaryColumns>
                </syncfusion:GridTableSummaryRow>

                <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="count"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />

                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.TableSummaryRows>
        </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class SelectorClass : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var summaryRecordEntry = (item as SpannedDataRow).RowData;
        var summaryValue = (summaryRecordEntry as SummaryRecordEntry).SummaryValues[0];
        var aggregateValue = summaryValue.AggregateValues.ElementAt(0);
        var calculatedValue = aggregateValue.Value;

        //custom condition is checked.

        if (aggregateValue.Key != "Count" && (double)calculatedValue < 0)
            return App.Current.Resources["customTableSummary"] as Style;

        return App.Current.Resources["customTableSummary1"] as Style;                 
    }
}
{% endhighlight %}
{% endtabs %}

Here, table summary rows are customized based on `TotalPrice` summary value.

![Displaying table summary cell styling using StyleSelector in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img23.png)

## Alignment customization based on column

The alignment of summary cells can be customized conditionally based on summary column. 

Here, horizontal alignment of table summary cells are changed based on column name. Likewise, you can change the horizontal alignment of group, caption summary cells.

{% tabs %}
{% highlight xaml %}
<Application.Resources>
    <Style x:Key="TableSummaryStyle1" TargetType="syncfusion:GridTableSummaryCell">
        <Setter Property="HorizontalContentAlignment" Value="Center" />
    </Style>
    <Style x:Key="TableSummaryStyle2" TargetType="syncfusion:GridTableSummaryCell">
        <Setter Property="HorizontalContentAlignment" Value="Right" />
    </Style>
</Application.Resources>

<Window.Resources>
    <local:TableSummaryStyleSelector x:Key="tableSummaryStyleSelector" />
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}"
                       TableSummaryCellStyleSelector="{StaticResource tableSummaryStyleSelector}">
<syncfusion:SfDataGrid.TableSummaryRows>
                <syncfusion:GridTableSummaryRow Position="Top" ShowSummaryInRow="False">
                    <syncfusion:GridTableSummaryRow.SummaryColumns>

                        <syncfusion:GridSummaryColumn Name="price"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="customerID"
                                                      Format="'{Count:c}'"
                                                      MappingName="CustomerID"
                                                      SummaryType="CountAggregate" />

                    </syncfusion:GridTableSummaryRow.SummaryColumns>
                </syncfusion:GridTableSummaryRow>

                <syncfusion:GridSummaryRow Title="Count : {count}, Total Price :  {totalPrice}" ShowSummaryInRow="True">
                    <syncfusion:GridSummaryRow.SummaryColumns>
                        <syncfusion:GridSummaryColumn Name="count"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />
                        <syncfusion:GridSummaryColumn Name="totalPrice"
                                                      Format="'{Sum:c}'"
                                                      MappingName="TotalPrice"
                                                      SummaryType="DoubleAggregate" />

                    </syncfusion:GridSummaryRow.SummaryColumns>
                </syncfusion:GridSummaryRow>
            </syncfusion:SfDataGrid.TableSummaryRows>
        </syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class TableSummaryStyleSelector : StyleSelector
{

    public override Style SelectStyle(object item, DependencyObject container)
    {
        var cell = container as GridTableSummaryCell;

        // Horizontal Alignments changed based on MappingName

        if (cell.ColumnBase.GridColumn.MappingName == "TotalPrice")
            return App.Current.Resources["TableSummaryStyle1"] as Style;
        return App.Current.Resources["TableSummaryStyle2"] as Style;
    }
}
{% endhighlight %}
{% endtabs %}

Here, horizontal alignment of `TotalPrice` column alone left, other column horizontal alignment are changed into right.

![Displaying alignment customization based on column in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img24.png)

## Row Header

The appearance of row header ([GridRowHeaderCell](http://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridRowHeaderCell.html)) can be customized conditionally by changing its property value based on ‘cell value’ or ‘data object’ by using `converter`, where converter returns the value based on Underlying record.

Here, row headers are customized based on `AmountPaid` property of underlying record.

{% tabs %}
{% highlight xaml %}
<Window.Resources>
            <local:ColorConverter x:Key="converter" />
            <Style TargetType="syncfusion:GridRowHeaderCell">
                <Setter Property="Background" Value="{Binding Converter={StaticResource converter}}" />
            </Style>
</Window.Resources>

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding Orders}"
                       ShowRowHeader="True">
     <syncfusion:SfDataGrid.Columns>
                <syncfusion:GridCheckBoxColumn MappingName="AmountPaid" />
     </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public class ColorConverter : IValueConverter
{

    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        var data = value as OrderInfo;

        //custom condition is checked.

        if (data.AmountPaid)
            return Brushes.Green;

        else
            return Brushes.Red;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException();
    }
}
{% endhighlight %}
{% endtabs %}

![Displaying row header styling using converter in WPF SfDataGrid](Conditional-Styling_images/Conditional-Styling_img25.png)

