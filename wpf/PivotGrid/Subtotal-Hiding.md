---
layout: post
title: Subtotal Hiding| | Wpf | Syncfusion
description: Subtotal Hiding
platform: wpf
control: PivotGrid
documentation: ug
---

# Subtotal Hiding

The sub-total hiding feature is used to show or hide sub-totals in PivotGrid. This feature enables you to have an abstract view of the data, in case of a larger data table by hiding sub-totals using the ShowSubTotals__property.

### Use Case Scenarios

When the user has more computational fields with sub-totals for each group in PivotGrid, as shown here, it can be difficult to view all the data. In such cases, you can hide the sub-totals and make it visible when required.

The following screenshot shows the PivotGrid with the sub-totals shown and hidden.

![](Features_images/Features_img27.png)



![](Features_images/Features_img28.png)



### Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Value it Accepts</th><th>
Data Type</th></tr>
<tr>
<td>
ShowSubTotals</td><td>
Shows or hides sub-totals </td><td>
True(Default)False </td><td>
Boolean </td></tr>
<tr>
<td>
ShowRowSubTotals</td><td>
Shows or hides sub-totals for pivot rows</td><td>
True(Default)False</td><td>
Boolean</td></tr>
<tr>
<td>
ShowColumnSubTotals</td><td>
Shows or hides sub-totals for pivot columns</td><td>
True(Default)False</td><td>
Boolean</td></tr>
</table>


### Methods



<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<th>
SubTotalsRendering</th><th>
Handles rendering of cells(showing or hiding the cells) by calculating the cell range values in the Pivot Engine based on the ShowSubTotals property value in the control</th><th>
</th><th>
Server Side </th><th>
Void </th></tr>
<tr>
<th>
SubTotalsVisibilityRenderer</th><th>
Handles rendering of cells(showing or hiding the cells) by calculating the cell range values for both rows and columns in the PivotEngine</th><th>
PivotItem</th><th>
Server Side</th><th>
Void</th></tr>
</table>


### Adding sub-total hiding to an application 

The following code example shows how to set values for the ShowSubTotals property:

### To hide sub-totals

In XAML,

To hide sub-totals, set the ShowSubTotals property as False as illustrated here.


{% highlight xml %} 



<Grid>

<syncfusion:PivotGridControl HorizontalAlignment="Left" Name="PivotGridControl1" VerticalAlignment="Top"

ShowSubTotals="False" ItemSource="{Binding Source={StaticResource data}}" >

</syncfusion:PivotGridControl>

</Grid>

{% endhighlight %} 

Through Code Behind,

To hide sub-totals, set the ShowSubTotals property as False in the MainWindow() constructor.

{% tabs %}
{% highlight C# %} 



public MainWindow()

{

    InitializeComponent();

    this.pivotGrid1.ShowSubTotals = false;   

}

 {% endhighlight %} 

{% highlight vbnet %} 



Public Sub MainWindow()

    InitializeComponent()

    Me.pivotGrid1.ShowSubTotals = False

End Sub


{% endhighlight %} 
{% endtabs %}

![](Features_images/Features_img29.png)



To hide sub-totals for columns

 In XAML,

To hide sub-totals, set the ShowColumnSubTotals property as False as illustrated here.

{% highlight xml %} 



<Grid>

<syncfusion:PivotGridControl HorizontalAlignment="Left" Name="PivotGridControl1" VerticalAlignment="Top"

ShowColumnSubTotals="False" ItemSource="{Binding Source={StaticResource data}}" >

</syncfusion:PivotGridControl>

</Grid>

{% endhighlight %} 

### Through Code Behind,

To hide sub-totals for columns, set the ShowColumnSubTotals property to False in MainWindow() constructor.

{% tabs %}
{% highlight C# %}  



public MainWindow()

{

    InitializeComponent();

    this.pivotGrid1.ShowColumnSubTotals = false;

}

{% endhighlight %} 

{% highlight vbnet %} 



Public Sub MainWindow()

    InitializeComponent()

    Me.pivotGrid1.ShowColumnSubTotals = False

End Sub

{% endhighlight %} 
{% endtabs %}

![](Features_images/Features_img30.png)


 To hide sub-totals for rows:

In XAML,

To hide sub-totals, set the ShowRowSubTotals property as False as illustrated here.


{% highlight xml %} 



<Grid>

<syncfusion:PivotGridControl HorizontalAlignment="Left" Name="PivotGridControl1" VerticalAlignment="Top"

ShowRowSubTotals="False" ItemSource="{Binding Source={StaticResource data}}" >

</syncfusion:PivotGridControl>

</Grid>

{% endhighlight %} 

### Through Code Behind

To hide sub-totals for rows, set the ShowRowSubTotals property as False in the MainWindow() constructor.

{% tabs %}
{% highlight C# %}  



public MainWindow()

{

    InitializeComponent();

    this.pivotGrid1.ShowRowSubTotals = false;

_}_

{% endhighlight %} 

{% highlight vbnet %} 



Public Sub MainWindow()

    InitializeComponent()

    Me.pivotGrid1.ShowRowSubTotals = False

End Sub

{% endhighlight %} 
{% endtabs %}

Subtotal Hiding

![](Features_images/Features_img31.png)



