---
layout: post
title: Chart-Labels in WPF Chart Control | Syncfusion
description: Learn here all about Chart-Labels support in Syncfusion WPF Chart (Classic) control, its elements and more details.
platform: wpf
control: Chart (Classic)
 documentation: ug
---
# Chart-Labels in WPF Chart (Classic)

## Chart Font Settings

Font settings of each and every part of Chart such as Chart, ChartArea, ChartLegend and ChartAreaLegend can be customized with the following given properties.

* FontFamily
* FontSize
* FontStretch
* FontStyle
* FontWeight
* Foreground



N> Font settings set to the Chart will be applied to all the units of chart. However, properties set separately for those units such as ChartArea, ChartAxis, ChartLegend will override, these settings.



![Chart-Controls_img171](Chart-Controls_images/Chart-Controls_img171.png)


## Chart Axis Label

ChartAxis Labels can be customized by using the following given properties.


<table>
<tr>
<th>
ChartAxis Property</th><th>
Description</th></tr>
<tr>
<td>
LabelBackground</td><td>
gets or sets the Background of the ChartAxis Label</td></tr>
<tr>
<td>
LabelForeground</td><td>
gets or sets the Foreground of the ChartAxis Label</td></tr>
<tr>
<td>
LabelBorderBrush</td><td>
gets or sets the Border brush of the ChartAxis Label</td></tr>
<tr>
<td>
LabelBorderThickness</td><td>
gets or sets the Border thickness of the ChartAxis Label</td></tr>
<tr>
<td>
LabelCornerRadius</td><td>
gets or sets the Corner Radius of the ChartAxis Label</td></tr>
<tr>
<td>
LabelFontFamily</td><td>
gets or sets the FontFamily of the ChartAxis Label</td></tr>
<tr>
<td>
LabelFontSize</td><td>
gets or sets the FontSize of the ChartAxis Label</td></tr>
<tr>
<td>
LabelFontWeight</td><td>
gets or sets the FontWeight of the ChartAxis Label</td></tr>
<tr>
<td>
LabelFormat</td><td>
gets or sets the Format of the ChartAxis Label such as 0.00 or 0 precent</td></tr>
<tr>
<td>
LabelDateTimeFormat</td><td>
gets or sets the DateTime Format of the ChartAxis LabelApplicable when Axis.ValueType is DateTime</td></tr>
</table>
The following code example could be used to customize the Chart Axis Labels.


{% tabs %}

{% highlight xaml %}

<sfchart:ChartArea.PrimaryAxis>

<sfchart:ChartAxis  LabelForeground="Blue" LabelBackground="Orange" LabelBorderBrush="Black" LabelBorderThickness="1" LabelCornerRadius="2" LabelFontFamily="Calibri" LabelFontSize="10" LabelFontWeight="Bold" LabelFormat="0%"/>

</sfchart:ChartArea.PrimaryAxis>

{% endhighlight  %}
{% highlight c# %}



//Sets the Label settings of PrimaryAxis

 Area.PrimaryAxis.LabelForeground = Brushes.Blue;

 Area.PrimaryAxis.LabelBackground = Brushes.Orange;

 Area.PrimaryAxis.LabelBorderBrush = Brushes.Black;

 Area.PrimaryAxis.LabelBorderThickness = new Thickness(1);

 Area.PrimaryAxis.LabelCornerRadius = new CornerRadius(2);

 Area.PrimaryAxis.LabelFontFamily = new FontFamily("Calibri");

 Area.PrimaryAxis.LabelFontSize = 10;            

 Area.PrimaryAxis.LabelFontWeight = FontWeights.Bold;

 Area.PrimaryAxis.LabelFormat = "0%";           
{% endhighlight  %}

{% endtabs %}


Following given figure illustrates Chart with customized Primary Axis labels.

![Chart-Controls_img172](Chart-Controls_images/Chart-Controls_img172.jpeg)


## Customizing Label Text

Apart from the default Labels displayed, you can also add Custom Labels to be displayed in the Chart. This section discusses the following topics.

Properties Used to Customize Label Text

The following properties are used to determine the data source for the text of the Labels.

<table>
<tr>
<th>
ChartAxis Property</th><th>
Description</th></tr>
<tr>
<td>
LabelsMode</td><td>
{{ '_Auto_' | markdownify }}: content is determined automatically{{ '_Custom_' | markdownify }}: custom values are used for labels content representation{{ '_DataSource_' | markdownify }}: external datasource is used for labels content{{ '_Default_' | markdownify }}: content for labels is either determined automatically, taken from external dataSource or being set with custom values{{ '_None_' | markdownify }}: labels values are taken from point's X-coordinate</td></tr>
<tr>
<td>
LabelsSource</td><td>
gets or sets the Labels Source</td></tr>
<tr>
<td>
PositionPath</td><td>
gets or sets the position path</td></tr>
<tr>
<td>
ContentPath</td><td>
gets or sets the content path</td></tr>
</table>
By assigning the LabelsMode property to ChartAxis.CustomLabels, you can add Custom Labels to the ChartAxis.


{% tabs %}

{% highlight xaml %}


<syncfusion:Chart Name="Chart1" >

          <syncfusion:ChartArea Name="area" >

                    <syncfusion:ChartArea.PrimaryAxis>

                        <syncfusion:ChartAxis LabelsMode="Custom" RangeCalculationMode="AdjustAcrossChartTypes">

                            <syncfusion:ChartAxis.CustomLabels>

                                <syncfusion:ChartAxisLabel Content="III place" Position="0" />

                                <syncfusion:ChartAxisLabel Content="I place" Position="1" />

                                <syncfusion:ChartAxisLabel Content="II place" Position="4" />

                            </syncfusion:ChartAxis.CustomLabels>

                        </syncfusion:ChartAxis>

                    </syncfusion:ChartArea.PrimaryAxis>                  

          </syncfusion:ChartArea>

</syncfusion:Chart>         

{% endhighlight  %}
{% highlight c# %}


// Indicates that the axis labels need to be taken from a custom source.

area.PrimaryAxis.LabelsMode = ChartAxisLabelsMode.Custom;



ChartAxisLabel customLabel1 = new ChartAxisLabel();

customLabel1.Content = "III place";

customLabel1.Position = 0;



ChartAxisLabel customLabel2 = new ChartAxisLabel();

customLabel2.Content = "I place";

customLabel2.Position = 1;



ChartAxisLabel customLabel3 = new ChartAxisLabel();

customLabel3.Content = "II place";

customLabel3.Position = 4;



// Adding custom label to labels collection.

area.PrimaryAxis.CustomLabels.Add(customLabel1);

area.PrimaryAxis.CustomLabels.Add(customLabel2);

area.PrimaryAxis.CustomLabels.Add(customLabel3);           

The following screenshot illustrates Chart PrimaryAxis with Custom Labels.
{% endhighlight  %}

{% endtabs %}


![Chart-Controls_img173](Chart-Controls_images/Chart-Controls_img173.jpeg)



### Labels from Data Source

The following code example illustrates how Custom Labels can be used in the ChartAxis.


{% highlight c# %}


// Indicates that the axis labels need to be taken from a data source.

area.PrimaryAxis.LabelsMode = ChartAxisLabelsMode.DataSource;   



// Creates DataSource with desired labels.

List<object> labels = new List<object>();

for (double i = 1; i < 6; i++)

{

labels.Add(new { Position = i, Content = "Label " + i.ToString() });

}



// Associates DataSource with the Chart Labels.

area.PrimaryAxis.LabelsSource = labels;       

// Set the position path where the labels should be placed.

area.PrimaryAxis.PositionPath = "Position";

// Set the content path from which labels are to be taken.

area.PrimaryAxis.ContentPath = "Content";
{% endhighlight  %}

The following screenshot illustrates Chart PrimaryAxis with Labels from Data Source.

![Chart-Controls_img174](Chart-Controls_images/Chart-Controls_img174.jpeg)



## Chart Axis Label Rotate

ChartAxis labels could be rotated with custom angles. Axis.LabelRotateAngle property is used to define the angle in which the Axis Labels need to be rotated.

The following code example could be used to customize the labels to be rotated with 90'.

{% tabs %}

{% highlight xaml %}

<sfchart:ChartArea.PrimaryAxis>

<sfchart:ChartAxis LabelRotateAngle="90" LabelFormat="0.000000" />

</sfchart:ChartArea.PrimaryAxis>

{% endhighlight  %}

{% highlight c# %}

//Sets the Label to be rotated with 90' angle

 Area.PrimaryAxis.LabelRotateAngle = 90;           
{% endhighlight  %}

{% endtabs %}

The following figure illustrates Chart with Primary Axis labels rotated with 90' angle

![Chart-Controls_img175](Chart-Controls_images/Chart-Controls_img175.jpeg)


N> LabelRotateAngle property will not have effect when the Axis.IntersectAction property is set as Rotate.


## Intersecting Labels

Sometimes the chart dimensions could cause the labels to intersect. The chart will, by default, render those texts one over the other. But, it also has some built-in capabilities to work around this overlap and lets you dictate the technique to follow. Refer to the properties as follows.


<table>
<tr>
<th>
ChartAxis Property</th><th>
Description</th></tr>
<tr>
<td>
IntersectAction</td><td>
{{ '_Hide_' | markdownify }} – labels are hidden to avoid intersection{{ '_MultipleRows_' | markdownify }} – labels are wrapped into multiple rows to avoid intersection{{ '_None_' | markdownify }} – no special actionLabels may intersect{{ '_Rotate_' | markdownify }} – labels are rotated to avoid intersection{{ '_Wrap_' | markdownify }} – labels are wrapped to avoid intersection</td></tr>
<tr>
<td>
HidePartialLabel</td><td>
{{ '_True_' | markdownify }} – hides the labels that appear partiallyUsually the labels in the edges will be affected.{{ '_False_' | markdownify }} - labels are drawn as suchNo action will be taken.</td></tr>
<tr>
<td>
EdgeLabelsDrawingMode</td><td>
{{ '_Center_' | markdownify }} – draws the edge labels at the center of the GridLines{{ '_Shift_' | markdownify }} – value indicating that edge label should be shifted to either left or right so that it comes within the Chart Area</td></tr>
</table>


{% tabs %}

{% highlight c# %}


Chart1.Areas[0].PrimaryAxis.IntersectAction = ChartLabelIntersectAction.MultipleRows;

Chart1.Areas[0].PrimaryAxis.HidePartialLabel = true;

Chart1.Areas[0].PrimaryAxis.EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Shift;

{% endhighlight  %}
{% highlight xaml %}

<syncfusion:ChartArea.PrimaryAxis>

<syncfusion:ChartAxis Header="Product Name"  IntersectAction="MultipleRows" HidePartialLabel="True" EdgeLabelsDrawingMode="Shift"  />

</syncfusion:ChartArea.PrimaryAxis>
{% endhighlight  %}

{% endtabs %}

The following screenshot illustrates various techniques for avoiding the Label intersection.

![Chart-Controls_img176](Chart-Controls_images/Chart-Controls_img176.jpeg)



![Chart-Controls_img177](Chart-Controls_images/Chart-Controls_img177.jpeg)



![Chart-Controls_img178](Chart-Controls_images/Chart-Controls_img178.jpeg)


## Legend Panel Customization 

Essential Chart enables you to arrange the legend items in any panel. You can arrange them in common panels like Grid, StackPanel, Canvas and WrapPanel. You can also create custom panel and arrange them. 

### Property

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type </th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
LegendItemsPanel</td><td>
Sets a template panel for arranging legend items.  </td><td>
Dependency Property</td><td>
ItemsPanelTemplate </td><td>
{{ '[ItemsPanelTemplate Class](http://msdn.microsoft.com/en-us/library/system.windows.controls.itemspaneltemplate.aspx)' | markdownify }}</td></tr>
</table>

### Customizing legend Panel

You can customize the legend panel using the _LegendItemsPanel_ property of ChartLegend. Following code illustrates this:


{% highlight xaml %}


<syncfusion:ChartLegend IconVisibility="Visible" BorderThickness="0" LegendPanel="Custom">                                    <syncfusion:ChartLegend.LegendItemsPanel>                                        <ItemsPanelTemplate>                                            <StackPanel Orientation="Vertical"/>                                        </ItemsPanelTemplate>                                    </syncfusion:ChartLegend.LegendItemsPanel>                                </syncfusion:ChartLegend>

{% endhighlight %}

![Chart-Controls_img179](Chart-Controls_images/Chart-Controls_img179.png)



### Sample Link

To view sample:

1. Open the Syncfusion Dashboard.
2. Select User Interface.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to WPF\Chart.WPF\Samples\3.5\WindowsSamples\Chart Customization\Custom Legend Items Panel Demo\
