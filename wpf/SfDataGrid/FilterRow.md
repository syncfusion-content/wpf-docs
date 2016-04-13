---
layout: post
title: FilterRow | SfDataGrid | WPF | Syncfusion
description: filterrow
platform: wpf
control: SfDataGrid
documentation: ug
---

# FilterRow

SfDataGrid allows you to filter the data by typing the value in FilterRow which is placed either in top or bottom of the DataGrid. You can enable the FilterRow by specifying the position in SfDataGrid.FilterRowPosition property.

The FilterRowPosition property contains the below positions to load the FilterRow in SfDataGrid.

1. FixedTop – Placed in top of the SfDataGrid in frozen state
2. Top – Placed in top of the SfDataGrid.
3. Bottom – Placed in bottom of the SfDataGrid.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="sfgrid"
                       FilterRowPosition="FixedTop"
                       AllowEditing="True" 
                       AutoGenerateColumns="True"  
                       ItemsSource="{Binding OrderList}"/>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.FilterRowPosition = FilterRowPosition.FixedTop;

{% endhighlight %}
{% endtabs %}

![](FilterRow_images/FilterRow_img1.png)


The each GridFilterRowCell which loads TextBox, DoubleTextBox and DateTimeEdit will contains the filter options button in right corner to change the FilterRowCondition at runtime. The below FilterRowConditions will be loaded based on editors.

<table>
<tr>
<th>
Editors
</th>
<th>
FilteRowConditions
</th>
</tr>
<tr>
<td>
TextBox
</td>
<td>
Equals, NotEquals, Empty, NotEmpty, Contains, BeginsWith, EndsWith, Null, NotNull
</td>
</tr>
<tr>
<td>
DoubleTextBox
</td>
<td>
Equals, NotEquals, GreaterThan, GreaterThanOrEqual, LessThan, LessThanOrEqual, Null, NotNull
</td>
</tr>
<tr>
<td>
DateTimeEdit
</td>
<td>
Equls, NotEquals, After, AfterOrEqual, Before, BeforeOrEqual, Null, NotNull
</td>
</tr>
</table>
You can remove the filter options button by using GridColumn.FilterRowOptionsVisibility property and also you can change the default FilterRowCondition of particular column using GridColumn.FilterRowCondition property.

{% tabs %}
{% highlight xaml %}

<syncfusion:GridTextColumn MappingName="CustomerID"
                           FilterRowCondition="Contains"
                           FilterRowOptionsVisibility="Collapsed"
                           HeaderText="Customer ID"/>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.Columns[0].FilterRowCondition = FilterRowCondition.Contains;
this.dataGrid.Columns[0].FilterRowOptionsVisibility = Visibility.Collapsed;

{% endhighlight %}
{% endtabs %}

You have to set true to GridColumn.ImmediateUpdateColumnFilter property for immediate filtering while typing the value. 

{% tabs %}
{% highlight xaml %}

<syncfusion:GridTextColumn MappingName="CustomerID"
                           ImmediateUpdateColumnFilter="True"
                           HeaderText="Customer ID"/>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.Columns[0].ImmediateUpdateColumnFilter = true;

{% endhighlight %}
{% endtabs %}

## Built-In Editors

The FilterRow will loads with different editors based on underlying type of each column. You can change this default editors by using GridColumn.FilterRowEditorType property. The FilterRow contains the below editors type.

<table>
<tr>
<th>
EditorType
</th>
<th>
Editor
</th>
<th>
Renderer
</th>
</tr>
<tr>
<td>
TextBox
</td>
<td>
TextBox
</td>
<td>
GridFilterRowTextBoxRenderer
</td>
</tr>
<tr>
<td>
Numeric
</td>
<td>
DoubleTextBox
</td>
<td>
GridFilterRowNumericRenderer
</td>
</tr>
<tr>
<td>
ComboBox
</td>
<td>
ComboBoxAdv
</td>
<td>
GridFilterRowComboBoxRenderer
</td>
</tr>
<tr>
<td>
MultiSelectComboBox
</td>
<td>
ComboBoxAdv
</td>
<td>
GridFilterRowMultiSelectRenderer
</td>
</tr>
<tr>
<td>
CheckBox
</td>
<td>
CheckBox
</td>
<td>
GridFilterRowCheckBoxRenderer
</td>
</tr>
<tr>
<td>
DateTime
</td>
<td>
DateTimeEdit
</td>
<td>
GridFilterRowDateTimeRenderer
</td>
</tr>
</table>

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn MappingName="CustomerID" 
                           FilterRowEditorType="MultiSelectComboBox"
                           ImmediateUpdateColumnFilter="True"
                           HeaderText="Customer ID"/>

{% endhighlight %}

{% highlight c# %}

this.dataGrid.Columns[1].FilterRowEditorType = "MultiSelectComboBox";

{% endhighlight %}
{% endtabs %}

![](FilterRow_images/FilterRow_img2.png)

