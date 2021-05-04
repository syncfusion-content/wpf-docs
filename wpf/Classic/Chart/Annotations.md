---
layout: post
title: Annotations in WPF Wizard Control control | Syncfusion
description: Learn here all about Annotations support in Syncfusion WPF Chart (Classic) control and more.
platform: wpf
control: Chart (Classic)
documentation: ug
---
# Annotations in WPF Chart (Classic)

## Annotations in WPF Chart (Classic) at X-Y Coordinates

Annotations at specific X-Y coordinates can be added to the chart programmatically. The ChartSeriesAnnotation type used to define an annotation provides these properties:


<table>
<tr>
<th>
ChartSeriesAnnotation Property</th><th>
Description</th></tr>
<tr>
<td>
Description</td><td>
String description of the annotation.</td></tr>
<tr>
<td>
X</td><td>
Specifies the x coordinate in the plot.</td></tr>
<tr>
<td>
Y</td><td>
Specifies the y coordinate in the plot.</td></tr>
<tr>
<td>
OffsetX</td><td>
X offset for locating the annotation.</td></tr>
<tr>
<td>
OffsetY</td><td>
Y offset for locating the annotation.</td></tr>
<tr>
<td>
Template</td><td>
Apecifies the look and feel of a specific annotation instance.</td></tr>
</table>
The AnnotationsCollection type, which is the container for the above ChartSeriesAnnotation instances, provides some properties that are applied on all the annotations:


<table>
<tr>
<th>
AnnotationsCollection Property</th><th>
Description</th></tr>
<tr>
<td>
AnnotationsTemplate</td><td>
Specifies the look and feel for all the annotations in the ChartSeries.</td></tr>
<tr>
<td>
LineColor</td><td>
Specifies the color of the line drawn from the location to the annotation, in case OffsetX and OffsetY are specified.</td></tr>
<tr>
<td>
IsRelative</td><td>
Z and y values above are x-y coordinates of the plotIf {{ '_true_' | markdownify }}, they are in Chart Area coordinates. Default value is {{ '_false_' | markdownify }}.</td></tr>
</table>


Here is a code example that adds a few annotations to a chart.

{% tabs %}
{% highlight xaml %}


<sfchart:ChartSeries Name="series1"  Label="Series1" Type="Area" Interior="LightSkyBlue">

    <sfchart:ChartSeries.Annotations>

        <sfchart:AnnotationsCollection LineColor="White" x:Uid="Annot">

            <!--Define the look and feel of the annotation.-->

            <sfchart:AnnotationsCollection.AnnotationsTemplate>

                <DataTemplate>

                    <Button Content="{Binding Y}" ToolTip="{Binding Description}"  Background="LightGray" Name="Button1"

                    Click="Button_Click" />

                </DataTemplate>

            </sfchart:AnnotationsCollection.AnnotationsTemplate>

        </sfchart:AnnotationsCollection>

        <!--The annotations are added to this collection in code-behind.-->

    </sfchart:ChartSeries.Annotations>

</sfchart:ChartSeries>

{% endhighlight  %}
{% highlight c# %}

// Series1 Annotations

ChartSeriesAnnotation ser1LowPoint = new ChartSeriesAnnotation() { X = 1, Y = 20, Description = "Series 1 Low Point" };

ChartSeriesAnnotation ser1HighPoint = new ChartSeriesAnnotation() { X = 7, Y = 56, Description = "Series 1 High Point" };



this.Chart1.Areas[0].Series[0].Annotations.Items.Add(ser1LowPoint);

this.Chart1.Areas[0].Series[0].Annotations.Items.Add(ser1HighPoint);

{% endhighlight  %}

{% endtabs %}

The resultant annotations look like this.

![Chart-Controls_img229](Chart-Controls_images/Chart-Controls_img229.jpeg)


## Annotations in WPF Chart (Classic) At Control Coordinates

Chart for WPF also lets you add some annotations to the chart at specific control coordinates. By default, these annotations appear as simple text labels. But, their look and feel can be fully customized using custom templates.

Here are some Chart control properties that let you add annotations at Chart control coordinates:


<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
AnnotationLabels</td><td>
Collection into which you add the ChartAnnotationLabel instances representing the annotations.</td></tr>
<tr>
<td>
AnnotationLabelTemplate</td><td>
Defines a custom look and feel for the annotation.</td></tr>
</table>
The ChartAnnotationLabel type used to define an annotation exposes these properties.


<table>
<tr>
<th>
ChartAnnotationLabel Property</th><th>
Description</th></tr>
<tr>
<td>
Content</td><td>
Content that needs to be displayed in the annotation (usually a string).</td></tr>
<tr>
<td>
OffsetX</td><td>
X offset from the top-left of the control used to determine the x-location of the annotation.</td></tr>
<tr>
<td>
OffsetY</td><td>
Y offset from the top-left of the control used to determine the y-location of the annotation.</td></tr>
</table>
Here is some code example that shows how to add annotations at Chart coordinates and how to customize their look and feel.


{% highlight xaml %}


<syncfusion:Chart Name="chart1">



   <!--Template defining the custom look and feel of the annotations.-->

    <syncfusion:Chart.AnnotationLabelTemplate>

        <DataTemplate>

            <Border Background="MintCream"  BorderBrush="Black" BorderThickness="1">

                <TextBlock Text="{Binding}" Foreground="Black" FontFamily="Tahoma" FontSize="12"  Margin="5"/>

            </Border>

        </DataTemplate>

    </syncfusion:Chart.AnnotationLabelTemplate>

    <syncfusion:Chart.AnnotationLabels>

        <syncfusion:ChartAnnotationLabelsCollection>



            <!--ChartAnnotationLabel instance representing the location and content of the annotation.-->

            <syncfusion:ChartAnnotationLabel x:Name="label1"  Content="Top 6 Products" OffsetX="50" OffsetY="60">

            </syncfusion:ChartAnnotationLabel>

        </syncfusion:ChartAnnotationLabelsCollection>

    </syncfusion:Chart.AnnotationLabels>

</syncfusion:Chart>
{% endhighlight  %}


![Chart-Controls_img230](Chart-Controls_images/Chart-Controls_img230.jpeg)


## Annotation Shapes

Predefined shapes for annotation objects are used to point at specific information about a position in the chart. For example: Circle, Arrow etc. 

The following table describes more about the annotation shapes:

<table>
<tr>
<th>
Name of the Property</th><th>
Type of Property</th><th>
Values It accepts</th></tr>
<tr>
<td>
Content</td><td>
Dependency Property</td><td>
String</td></tr>
<tr>
<td>
AnnotationShape</td><td>
Dependency Property</td><td>
Enum of type AnnotationShapes</td></tr>
<tr>
<td>
Fill</td><td>
Dependency Property</td><td>
Colors from brushes</td></tr>
<tr>
<td>
Offset X</td><td>
Dependency Property</td><td>
Double value</td></tr>
<tr>
<td>
Offset Y</td><td>
Dependency Property</td><td>
Double Value</td></tr>
</table>



> The Content property helps represent the required content in an annotation shape.

> The AnnotationShape property helps create the required shape for an annotation object and the Fill property helps fill the selected shape with required color.



The following code example illustrates the creation of predefined annotation shape for a Chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:Chart.AnnotationsLabel>

<syncfusion:ChartAnnotationLabelsCollection>

<syncfusion:ChartAnnotationLabel x:Name="Annotlabel" Content="Target Reached" OffsetY="200" OffsetX="200" AnnotationShape="Circle" Fill="Red"/>

</syncfusion:ChartAnnotationLabelsCollection>

</syncfusion:Chart.AnnotationsLabel>

<syncfusion:ChartArea >

{% endhighlight  %}
{% highlight c# %}

Chart1.AnnotationsLabel[0].OffsetX = 200;

Chart1.AnnotationsLabel[0].OffsetY = 200;

Chart1.AnnotationsLabel[0].Content = "TargetReached";

Chart1.AnnotationsLabel[0].AnnotationShape = AnnotationShapes.Circle;

Chart1.AnnotationsLabel[0].AnnotationShape = Red;
{% endhighlight  %}

{% endtabs %}

Run the code. The following output is displayed.

![Chart-Controls_img231](Chart-Controls_images/Chart-Controls_img231.jpeg)



A sample which demonstrates the various predefined annotation shapes in Essential Chart, is available in the following install location:

_C:\Documents and Settings\<user name>\My Documents\Syncfusion\Essential Studio\ Samples\WPF\Chart.WPF\Samples\3.5\WindowsSamples\Annotations_
