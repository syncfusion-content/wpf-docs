---
layout: post
title: Annotations in WPF Charts control | Syncfusion
description: Learn here all about Annotations support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---
# Annotations in WPF Charts (SfChart)

SfChart supports Annotations, which allows you to mark the specific area of interest in the chart area. You can draw custom shapes, also text and images can be added using Annotations. 

The following annotations are supported in SfChart

* [Text Annotation](https://help.syncfusion.com/wpf/charts/annotations#text-annotation)
* [Shape Annotation](https://help.syncfusion.com/wpf/charts/annotations#shape-annotation)
* [Image Annotation](https://help.syncfusion.com/wpf/charts/annotations#image-annotation)

## Adding Annotation

You can create an instance for any type of Annotation and add it to [`Annotations`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.AnnotationCollection.html#) collection. Here for instance, the EllipseAnnotation is added.

{% tabs %}

{% highlight xml %}

            <chart:SfChart.Annotations>            
                    <chart:EllipseAnnotation  X1="1.5" Y1="20" Text="Ellipse" X2="3" Y2="23" >
                    </chart:EllipseAnnotation>                           
            </chart:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

        EllipseAnnotation annotation=new EllipseAnnotation()
        {
            X1 = 1.5, Y1 = 20,
            X2 = 3, Y2 = 23,
            Text = "Ellipse"
        };

chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Annotation in WPF Chart](Annotation_images/wpf-chart-annotation.jpeg)


## Positioning the Annotation

Annotations can be positioned in plot area based on [`X1`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_x1) and [`Y1`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_y1)  properties and for image and shape annotations you need to specify [`X2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_x2) and [`Y2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_x2) properties. These X and Y values can be specified with axis units or pixel units and this can be identified using [`CoordinateUnit`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_CoordinateUnit) property.

**Positioning** **based** **on** **CoordinateUnit** **as** **Axis**

To position the annotation based on axis, set the X1 and Y1, X2 and Y2 properties based on axis range values, if needed, set the CoordinateUnit value as [`Axis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.CoordinateUnit.html)..

{% tabs %}

{% highlight xml %}
       
         <chart:RectangleAnnotation  X1="1.25" Y1="1300" FontSize="10" FontFamily="Calibri" Text="Axis Value" X2="2.25" Y2="1500" CoordinateUnit="Axis">
                        </chart:RectangleAnnotation>

{% endhighlight %}

{% highlight c# %}

        RectangleAnnotation annotation=new RectangleAnnotation()
        {
            X1 = 1.25, Y1 = 1300,
            X2 = 2.25, Y2 = 1500,
            Text = "Axis Value",
            CoordinateUnit=CoordinateUnit.Axis,
            Text="Axis Value"
        };

chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Changing Annotation Position based on CoordinateUnit as Axis in WPF Chart](Annotation_images/wpf-chart-annotation-based-on-coordinates.jpg)

**Positioning** **based** **on** **CoordinateUnit** **as** **Pixels**

To position based on the pixel values you have to set the CoordinateUnit as Pixels and the pixel values in X1 and Y1, X2 and Y2 properties in Annotation.


{% tabs %}

{% highlight xml %}

            <chart:RectangleAnnotation  X1="50" Y1="150" Text="Pixel Value" X2="100" Y2="125" CoordinateUnit="Pixel">
                    </chart:RectangleAnnotation>
            
{% endhighlight %}

{% highlight c# %}

        RectangleAnnotation annotation=new RectangleAnnotation()
        {
            X1 = 50, Y1 = 150,
            X2 = 100, Y2 = 125,
            CoordinateUnit=CoordinateUnit.Pixel,
            Text="Pixel Value"
        };

chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Changing Annotation Position based on CoordinateUnit as Pixel in WPF Chart](Annotation_images/wpf-chart-axis-based-on-coordinate-pixel.jpg)

**Adding** **Annotation** **for** **MultipleAxes**

You can also add annotation for a particular axis when there is multiple axes using [`XAxisName`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_XAxisName) and [`YAxisName`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_YAxisName) properties as in the below code snippet.

{% tabs %}

{% highlight xaml %}

        <chart:SfChart Width="400" Height="400" BorderBrush="Transparent">
            <chart:SfChart.RowDefinitions>
                <chart:ChartRowDefinition></chart:ChartRowDefinition>
                <chart:ChartRowDefinition></chart:ChartRowDefinition>
            </chart:SfChart.RowDefinitions>
            <!--PrimaryAxis-->
            <chart:SfChart.PrimaryAxis>
                <chart:CategoryAxis  FontSize="11" ShowGridLines="False"/>
            </chart:SfChart.PrimaryAxis>
            <chart:SfChart.SecondaryAxis>
                <chart:NumericalAxis x:Name="ColumnAxis" Maximum="2000" FontSize="11" Interval="500" chart:ChartBase.Row="0" ShowGridLines="False"/>
            </chart:SfChart.SecondaryAxis>

            <chart:SfChart.Annotations>
                <chart:AnnotationCollection>
                    <chart:RectangleAnnotation YAxisName="ScatterAxis" Fill="LightGray" Stroke="DarkGray" Opacity="0.5" X1="0.5" Y1="900" X2="2.5" Y2="1600" >
                    </chart:RectangleAnnotation>

                    <chart:HorizontalLineAnnotation YAxisName="ColumnAxis" Stroke="DarkGray" X1="-0.5" X2="3.5" Y1="1700" LineCap="Arrow"></chart:HorizontalLineAnnotation>
                </chart:AnnotationCollection>
            </chart:SfChart.Annotations>

            <chart:ColumnSeries  Interior="#777777" ItemsSource="{Binding CategoricalData}" XBindingPath="Category" YBindingPath="Plastic">
            </chart:ColumnSeries>

            <chart:ScatterSeries Interior="#777777" ItemsSource="{Binding CategoricalData}" XBindingPath="Category" YBindingPath="Plastic">
                <chart:ScatterSeries.YAxis>
                    <chart:NumericalAxis x:Name="ScatterAxis" Maximum="2000" FontSize="11" Interval="500" chart:ChartBase.Row="1" ShowGridLines="False"/>
                </chart:ScatterSeries.YAxis>
            </chart:ScatterSeries>
        </chart:SfChart>

{% endhighlight %}

{% highlight c# %}

            SfChart chart = new SfChart();
            chart.RowDefinitions.Add(new ChartRowDefinition());
            chart.RowDefinitions.Add(new ChartRowDefinition());
            chart.PrimaryAxis = new CategoryAxis();
            chart.SecondaryAxis = new NumericalAxis();
            ChartBase.SetRow(chart.SecondaryAxis, 0);

            HorizontalLineAnnotation annotation = new HorizontalLineAnnotation()
            {
                X1 = -0.5,
                Y1 = 1700,
                X2 = 3.5,
                YAxisName = "ColumnAxis",
                LineCap=LineCap.Arrow,
                Stroke=new SolidColorBrush(Colors.DarkGray)
            };

            RectangleAnnotation rect = new RectangleAnnotation()
            {
                YAxisName = "ScatterAxis",
                Fill = new SolidColorBrush(Colors.LightGray),
                Stroke = new SolidColorBrush(Colors.DarkGray),
                Opacity = 0.5,
                X1 = 0.5,
                Y1 = 900,
                X2 = 2.5,
                Y2 = 1600
            };

            ColumnSeries columnSeries = new ColumnSeries()
            {
                ItemsSource = new CategoricalViewModel().CategoricalData,
                XBindingPath = "Category",
                YBindingPath = "Plastic",
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))               
            };

            ScatterSeries scatterSeries = new ScatterSeries()
            {
                ItemsSource = new CategoricalViewModel().CategoricalData,
                XBindingPath = "Category",
                YBindingPath = "Plastic",
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))               
            };

            NumericalAxis axis = new NumericalAxis()
            {
                Name = "ScatterAxis",
                Maximum = 2000,
                FontSize = 11,
                Interval = 500,
                ShowGridLines = false
            };

            scatterSeries.YAxis = axis;
            ChartBase.SetRow(axis, 1);

        chart.Series.Add(columnSeries);
        chart.Series.Add(scatterSeries);

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Annotation with Multiple Axes](Annotation_images/wpf-chart-multiple-annotation.jpeg)

## Text Annotation

[`TextAnnotations`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.TextAnnotation.html#) are used to add simple with help of ['Text'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_Text) property in specific points over the chart area.

{% tabs %}

{% highlight xml %}

        <chart:SfChart.Annotations>
          <chart:TextAnnotation Text="Annotation" X1="2.5" Y1="1400" >
                    </chart:TextAnnotation>
        </chart:SfChart.Annotations>
            
{% endhighlight %}

{% highlight c# %}

        TextAnnotation annotation=new TextAnnotation()
        {
            X1 = 2.5, 
            Y1 = 1400,
            Text="Annotation"
        };

chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![WPF Chart with Text Annotation](Annotation_images/wpf-chart-text-annotation.jpg)

### Customizing Text Annotation

SfChart provides you with an editing option for the text in any annotations. When text annotation is enabled editing, if we click the text annotation it switches to edit mode which provide easy way of customizing the text at run time.

The following properties are used to customize the text:

* [`EnableEditing`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_EnableEditing) - Used to define whether the text in TextAnnotation can be edited or not.

* [`Angle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.TextAnnotation.html#Syncfusion_UI_Xaml_Charts_TextAnnotation_Angle) - Used to get or set the angle for rotating the Annotation.

* ['EnableClipping'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_EnableClipping) - Used to define whether annotation should clip while crossing with boundary.

* [`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_Foreground) - Used to change the text color.

* [`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontSize)– An int value that represents the font size of the annotation text.

* [`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontFamily)– Represents the font family of the annotation text.

* [`FontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontStyle)– Represents the font style of the annotation text.

* [`FontWeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontWeight)- Represents the font weight of the annotation text.

* [`FontStretch`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_FontStretch) - Represents the font stretch for the annotation description.


{% tabs %}

{% highlight xml %}

    <chart:TextAnnotation Angle="90" EnableEditing="True" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" FontWeight="Bold"
    Foreground="Black"  Text="Annotation" X1="3.5" Y1="500" >

{% endhighlight %}

{% highlight c# %}

       TextAnnotation annotation = new TextAnnotation()
            {
                X1 = 3.5,
                Y1 = 500,
                Text = "Annotation",
                EnableEditing=true,
                Foreground=new SolidColorBrush(Colors.Black),
                FontStyle=FontStyles.Bold,
                HorizontalAlignment=HorizontalAlignment.Stretch,
                VerticalAlignment=VerticalAlignment.Stretch
            };

    chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Editing Text Annotation in WPF Chart](Annotation_images/wpf-chart-text-annotation-editing.jpeg)


## Shape Annotation

[`ShapeAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#) allows you to add annotations in the form of shapes such as rectangle, ellipse,horizontal line and vertical line  at the specific area of interest, in the chart area.

* [`EllipseAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.EllipseAnnotation.html#)- Used to draw a circle or an ellipse over the chart area.

* [`RectangleAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RectangleAnnotation.html#)- Used to draw a rectangle over the chart area.

* [`LineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#) - Used to draw a line over the chart area.

* [`VerticalLineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.VerticalLineAnnotation.html#)- Used to draw a vertical line across the chart area.

* [`HorizontalLineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HorizontalLineAnnotation.html#) - Used to add a horizontal line across the chart area.


The following API’s are commonly used in all ShapeAnnotation:

* [`Fill`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_Fill) - Represents the brush inside the Shape Annotation.

* [`X2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_x2)  - Represents the X2 Coordinate of the Shape Annotation.

* [`Y2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_y2) - Represents the Y2 Coordinate of the Shape Annotation.

* [`CanDrag`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanDrag) - A Boolean value that represent to drag the Annotation.

* [`CanResize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize)  - A Boolean value that represent to resize the Annotation.


### Ellipse Annotation

The ['EllipseAnnotation'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.EllipseAnnotation.html#) is used to draw an oval or a circle in specific points over the chart area.


{% tabs %}

{% highlight xml %}

     <chart:EllipseAnnotation  X1="1.5" Y1="1400" X2="2.5" Y2="1600" Text="Ellipse">
                    </chart:EllipseAnnotation>

{% endhighlight %}

{% highlight c# %}

        EllipseAnnotation ellipse = new EllipseAnnotation()
            {
                X1 = 1.5,
                Y1 = 1400,
                X2 = 2.5,
                Y2 = 1600,
                Text = "Ellipse"
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart with Ellipse Annotation](Annotation_images/wpf-chart-ellipse-annotation.jpg)

### Rectangle Annotation

The ['RectangleAnnotation'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.RectangleAnnotation.html#) is used to draw a rectangle or a square in specific points over the chart area.

{% tabs %}

{% highlight xml %}

        <chart:RectangleAnnotation  X1="2.5" Y1="1500" X2="3.5" Y2="1750" Text="Rectangle">
        </chart:RectangleAnnotation>

{% endhighlight %}

{% highlight c# %}

        RectangleAnnotation rectangle = new RectangleAnnotation()
            {
                X1 = 2.5,
                Y1 = 1500,
                X2 = 3.5,
                Y2 = 1750,
                Text = "Rectangle"
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart with Rectangle Annotation](Annotation_images/wpf-chart-rectangle-annotation.jpg)

### Line Annotation

The ['LineAnnotation'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#) is used to draw a line in specific points over the chart area.

{% tabs %}

{% highlight xml %}

        <chart:LineAnnotation  X1="1.5" Y1="1150" X2="3.5" Y2="1600" Text="Line">
        </chart:LineAnnotation>

{% endhighlight %}

{% highlight c# %}

        LineAnnotation line = new LineAnnotation()
            {
                X1 = 1.5,
                Y1 = 1150,
                X2 = 3.5,
                Y2 = 1600,
                Text = "Line"
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart with Line Annotation](Annotation_images/wpf-chart-line-annotation.jpg)

### Vertical and Horizontal line annotation

The ['VerticalLineAnnotation'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.VerticalLineAnnotation.html#) and [`HorizontalLineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HorizontalLineAnnotation.html#) are used to draw vertical and horizontal lines in specific points over the chart area.

{% tabs %}

{% highlight xml %}

        <chart:HorizontalLineAnnotation  X1="-0.5" Y1="1500" X2="4.5">
            </chart:HorizontalLineAnnotation>

        <chart:VerticalLineAnnotation X1="2.5"></chart:VerticalLineAnnotation>

{% endhighlight %}

{% highlight c# %}

        HorizontalLineAnnotation hor = new HorizontalLineAnnotation()
            {
                X1 = -0.5,
                Y1 = 1500,
                X2 = 4.5,
            };

        VerticalLineAnnotation ver = new VerticalLineAnnotation()
            {
                X1 = 2.5
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart with Vertical and Horizontal Line Annotation](Annotation_images/wpf-chart-horizontal-vertical-annotation.jpg)

### Customizing Line Annotation
The appearance of the LineAnnotation, VerticalLineAnnotation and HorizontalLineAnnotation can be customized with use of following properties.

* [`GrabExtent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_GrabExtent) - Used to extent the hit visible area while performing dragging and resizing.

* [`ShowLine`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_ShowLine) - Used to collapse the visibility of the line annotation.

* [`LineCap`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_LineCap)

* [`ShowAxisLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#Syncfusion_UI_Xaml_Charts_StraightLineAnnotation_ShowAxisLabel) - Used to display the axis labels in which the line is placed

**Adding arrow to line annotation**

To display single headed arrow, set the ['LineCap'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_LineCap) property to ['Arrow'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineCap.html). The default value of the ['LineCap'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html#Syncfusion_UI_Xaml_Charts_LineAnnotation_LineCap) property is ['None'](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineCap.html).

{% tabs %}

{% highlight xml %}

       <chart:LineAnnotation  X1="0.5" Y1="1500" X2="3.5" Y2="1500" LineCap="Arrow" Text="Line">
    </chart:LineAnnotation>

{% endhighlight %}

{% highlight c# %}

        LineAnnotation ellipse = new LineAnnotation()
            {
                X1 = 0.5,
                Y1 = 1500,
                X2 = 3.5,
                Y2 = 1500,
                Text = "Line",
                LineCap=LineCap.Arrow
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart displays Arrow in Line Annotation](Annotation_images/wpf-chart-line-annotation-with-arrow.jpg)

**Displaying** **Axis** **Labels** **for** **LineAnnotation**

[`VerticalLineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.VerticalLineAnnotation.html#) and [`HorizontalLineAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.HorizontalLineAnnotation.html#) also displays the axis labels in which the line is placed. This feature can be enabled by setting [`ShowAxisLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#Syncfusion_UI_Xaml_Charts_StraightLineAnnotation_ShowAxisLabel) property to true as in the below code snippet.


{% tabs %}

{% highlight xml %}

        <chart:HorizontalLineAnnotation ShowAxisLabel="True" X1="-0.5" Y1="1500" X2="4.5">
                    </chart:HorizontalLineAnnotation>

        <chart:VerticalLineAnnotation ShowAxisLabel="True" X1="2.5"></chart:VerticalLineAnnotation>

{% endhighlight %}

{% highlight c# %}

        HorizontalLineAnnotation hor = new HorizontalLineAnnotation()
            {
                X1 = -0.5,
                Y1 = 1500,
                X2 = 4.5,
                ShowAxisLabel=true               
            };

        VerticalLineAnnotation ver = new VerticalLineAnnotation()
            {
                X1 = 2.5,
                ShowAxisLabel=true
            };

{% endhighlight %}

{% endtabs %}

![Displaying Axis Label for Line Annotation in WPF Chart](Annotation_images/wpf-chart-line-axis-label.jpg)

Also, axis label can be customized the default appearance using [`AxisLabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#Syncfusion_UI_Xaml_Charts_StraightLineAnnotation_AxisLabelTemplate) property.

### Adding text in shape annotation

For all the shape annotations, the text can be displayed by using the [`Text`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_Text) property.

**Customizing text in shape annotation**

The text alignment can be changed using [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_HorizontalTextAlignment) and [`VerticalTextAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_VerticalTextAlignment) properties. 

{% tabs %}
{% highlight xaml %}

        <chart:EllipseAnnotation  X1="1.5" Y1="1400" X2="2.5" Y2="1600" FontWeight="Bold"  HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text="Ellipse">
        </chart:EllipseAnnotation> 

{% endhighlight %}

{% highlight c# %}

        EllipseAnnotation ellipse = new EllipseAnnotation()
            {
                X1 = 1.5,
                Y1 = 1400,
                X2 = 2.5,
                Y2 = 1600,
                HorizontalTextAlignment =HorizontalAlignment.Center,
                VerticalTextAlignment = VerticalAlignment.Center,
                FontStyle=FontStyles.Bold,
                Text = "Ellipse"               
            };

{% endhighlight %}

{% endtabs %}

![Customizing Text of Shape Annotation in WPF Chart](Annotation_images/wpf-chart-text-in-shape.jpg)

N> [`HorizontalTextAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_HorizontalTextAlignment) and [`VerticalTextAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_VerticalTextAlignment) properties are not applicable for [`TextAnnotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.TextAnnotation.html#).

### Customizing the Shape Annotation

SfChart allows customization of shape annotation using the following properties.

* [`Stroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_Stroke) - Represents the brush for the annotation outline.
* [`StrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeThickness) - Represents the thickness of the annotation outline.
* [`StrokeDashArray`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashArray) - Represents the DashArray of the annotation stroke.
* [`StrokeDashCap`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashCap)- Represents the DashCap of the annotation stroke.
* [`StrokeDashOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeDashOffset) - Represents the DashOffset of the annotation stroke.
* [`StrokeEndLineCap`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeEndLineCap) - Represents the end line cap of the annotation stroke.
* [`StrokeLineJoin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeLineJoin) - Represents the line join of the annotation outline.
* [`StrokeMiterLimit`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_StrokeMiterLimit) - Represents the limit on the ratio of the miter length to half of the annotation shape.

{% tabs %}

{% highlight xaml %}

         <chart:HorizontalLineAnnotation  X1="-0.5" StrokeThickness="3" StrokeDashCap="Square" StrokeEndLineCap="Square" StrokeStartLineCap="Square"
                          Stroke="DarkGray" Fill="LightGray" StrokeDashArray="1,3" Y1="1600" X2="4.5" Y2="1600" Text="Line">
        </chart:HorizontalLineAnnotation>                

{% endhighlight %}

{% highlight c# %}

            SfChart chart = new SfChart();

            HorizontalLineAnnotation annotation = new HorizontalLineAnnotation()
            {

                X1 = -0.5,
                X2 = 4.5,
                Y1 = 1500,
                StrokeThickness = 3,
                Stroke = new SolidColorBrush(Colors.DarkGray),
                Fill = new SolidColorBrush(Colors.LightGray),
                StrokeDashArray = new DoubleCollection() { 1, 3 },
                StrokeStartLineCap = PenLineCap.Square,
                StrokeEndLineCap = PenLineCap.Square,
                StrokeDashCap = PenLineCap.Round
            };

            chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![Customizing Shape Annotations in WPF Chart](Annotation_images/wpf-chart-shape-annotation-customization.jpg)


## Image Annotation

SfChart provides support to add images as Annotation over the chart area, using the class [ImageAnnotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#). 

The following API’s are used in ImageAnnotation.

* [`Angle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SolidShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_SolidShapeAnnotation_Angle)  – An integer value that represents the rotation angle for the text in Annotation.
* [`ImageSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_ImageSource)  - Represents the source from where the image must be added.
* [`X2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_X2) - Represents the X2 Coordinate of the Annotation.
* [`Y2`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ImageAnnotation.html#Syncfusion_UI_Xaml_Charts_ImageAnnotation_Y2) - Represents the Y2 Coordinate of the Annotation.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ImageAnnotation  Text="Annotation" HorizontalTextAlignment="Center" 
            VerticalTextAlignment="Top" ImageSource="Images\Graduate.png" X1="2.5" Y1="1200" X2="3.6" Y2="1700" >
        </syncfusion:ImageAnnotation>                       

{% endhighlight %}

{% highlight c# %}

        ImageAnnotation annotation = new ImageAnnotation()
            {
                Text = "Annotation",
                HorizontalTextAlignment = HorizontalAlignment.Center,
                VerticalTextAlignment = VerticalAlignment.Top,
                X1 = 2.5,
                Y1 = 1200,
                X2 = 3.6,
                Y2 = "1700",
                ImageSource = new BitmapImage(new Uri(@"Images\Graduate.png", UriKind.RelativeOrAbsolute))
            };

{% endhighlight %}

{% endtabs %}

![WPF Chart with Image Annotation](Annotation_images/wpf-chart-image-annotation.jpeg)

## Interaction

SfChart provides dragging and resizing support for [`ShapeAnnotations`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#).

The following API’s are used for dragging and resizing the annotation

* [`CanDrag`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanDrag)- A Boolean value that allows the annotation to drag. 

* [`CanResize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize)- A Boolean value that allows the annotation to resize. 

* [`DraggingMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_DraggingMode)- Represents the dragging direction for the annotation. 

* [`ResizingMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SolidShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_SolidShapeAnnotation_ResizingMode)- Represents the resizing direction for the annotation. 

**Dragging** **the** **Annotation**

The following code example demonstrates the dragging the rectangle annotation.

{% tabs %}

{% highlight xaml %}

        <chart:RectangleAnnotation  X1="0.6" CanDrag="True" X2="2.2" Y2="1500" Y1="1800" 
                Stroke="DarkGray" Fill="LightGray" Opacity="0.5">
        </chart:RectangleAnnotation>

{% endhighlight %}

{% highlight c# %}

        RectangleAnnotation an = new RectangleAnnotation()
            {
                X1 = 0.6,
                Y1 = 1800,
                X2 = 2.2,
                Y2 = 1500,
                Fill = new SolidColorBrush(Colors.LightGray),
                Stroke = new SolidColorBrush(Colors.DarkGray),
                CanDrag = true,
                Opacity = 0.5
            };

{% endhighlight %}

{% endtabs %}

![Dragging Annotation in WPF Chart](Annotation_images/wpf-chart-drag-annotation.jpeg)


Also, the direction of dragging can be customized by using [`DraggingMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_DraggingMode) property.

**Resizing** **the** **Annotation**

You can resize the annotation by enabling [`CanResize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize) property to True as in the below code snippet.

{% tabs %}

{% highlight xaml %}

        <chart:RectangleAnnotation  X1="0.6" CanResize="True" X2="2.2" Y2="1500" Y1="1800" 
            Stroke="DarkGray" Fill="LightGray" Opacity="0.5" >
        </chart:RectangleAnnotation>

{% endhighlight %}

{% highlight c# %}

         RectangleAnnotation an = new RectangleAnnotation()
            {
                X1 = 0.6,
                Y1 = 1800,
                X2 = 2.2,
                Y2 = 1500,
                Fill = new SolidColorBrush(Colors.LightGray),
                Stroke = new SolidColorBrush(Colors.DarkGray),
                CanDrag = true,
                Opacity = 0.5
            };

    {% endhighlight %}

    {% endtabs %}

![Eesizing Annotation in WPF Chart](Annotation_images/wpf-chart-resize-annotation.jpeg)


Also, the direction of resizing can be customized by using [`ResizingMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SolidShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_SolidShapeAnnotation_ResizingMode) property.


## ToolTip

SfChart provides support to view the tooltip when mouse hovered on the annotation. To view to tooltip you have to enable the [`ShowToolTip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ShowToolTip) property. By default for tooltip there is no content, you have to set the content for the tooltip in [`ToolTipContent`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipContent) property.

* [`ToolTipPlacement`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipPlacement) - Used to position the Tooltip with top, bottom, left or right side of the cursor.

* [`TooltipTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipTemplate) - Used to customize the default appearance of the Tooltip.

The following code example demonstrates the default tooltip.

{% tabs %}

{% highlight xaml %}

        <chart:EllipseAnnotation  X1="2.5" Y1="1500" X2="3.6" Y2="1680" 
            ShowToolTip="True" ToolTipContent="Annotation">
        </chart:EllipseAnnotation>
            
{% endhighlight %}

{% highlight c# %}

        SfChart chart = new SfChart();
        EllipseAnnotation annotation=new EllipseAnnotation ()
        {
            X1 = 2.5, 
            Y1 = 1500, 
            X2 = 3.6, 
            Y2 = 1680,
            Stroke = new SolidColorBrush(Colors.DarkGray),
            Fill = new SolidColorBrush (Colors.LightGray),
            ShowToolTip = true ,
            ToolTipContent = "Annotation"
        };
        chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![ToolTip for Annotation in WPF Chart](Annotation_images/wpf-chart-annotation-tooltip.jpeg)

**ToolTipTemplate**

The default appearance of the Tooltip can be changed using [`TooltipTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_ToolTipTemplate) property as in the below code snippet.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfChart x:Name="chart">
        <syncfusion:SfChart.Resources>
                <DataTemplate  x:Key="tooltipTemplate">
                    <Border CornerRadius="5" BorderBrush="DarkGray"  BorderThickness="1">                     
                        <TextBlock FontSize="11" Text="Annotation"                                   
                                   Foreground="Black"/>
                    </Border>
                 </DataTemplate>
        </syncfusion:SfChart.Resources>
        <syncfusion:SfChart.Annotations>
            <syncfusion:EllipseAnnotation  X1="2.5" Y1="1500" Stroke="DarkGray" Fill="LightGray" ShowToolTip="True"    X2="3.6" Y2="1680" ToolTipTemplate="{StaticResource tooltipTemplate}">
            </syncfusion:EllipseAnnotation>
        </syncfusion:SfChart.Annotations>
    </syncfusion:SfChart>

{% endhighlight %}

{% highlight c# %}

        SfChart chart = new SfChart();
        EllipseAnnotation annotation=new EllipseAnnotation ()
        {
            X1 = 2.5, 
            Y1 = 1500, 
            X2 = 3.6, 
            Y2 = 1680,
            Stroke = new SolidColorBrush(Colors.DarkGray),
            Fill = new SolidColorBrush (Colors.LightGray),
            ShowToolTip = true ,
            ToolTipTemplate = chart.Resources["tooltipTemplate"] as DataTemplate
        };
        chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}


![Annotation Tooltip Template in WPF Chart](Annotation_images/wpf-chart-annotation-tooltip-template.jpeg)

## Annotation Clipping

SfChart allows you to clip the annotation if the annotation crosses the boundary by setting [`EnableClipping`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_EnableClipping) property to True as in the below code snippet.

{% tabs %}

{% highlight xaml %}

        <chart:SfChart.Annotations>            
                  
            <chart:ImageAnnotation ImageSource="Images\Graduate.png"  X1="6" Y1="16" X2="9" Y2="18"     EnableClipping="True"/>

        </chart:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

    SfChart chart = new SfChart();

        ImageAnnotation image = new ImageAnnotation()
            {
                X1 = 6,
                Y1 = 16,
                X2 = 9,
                Y2 = 18,
                ImageSource = new BitmapImage(new Uri("Images\Graduate.png", UriKind.RelativeOrAbsolute)),
                EnableClipping=true
            };

        chart.Annotations.Add(image);

{% endhighlight %}

{% endtabs %}

The following screenshot explains that even when x value is provided out of bounds the image annotation is placed inside the chart area.

![Annotation Clipping in WPF Chart](Annotation_images/wpf-chart-annotation-clipping.jpeg)

## Annotation based on axis

The value of X1, X2, Y1, and Y2 properties of annotation will differ based on the axis type. The following table illustrates how to set the values for X1 and X2 properties of annotation based on the corresponding primary axis.

<table>
<tr>
<th>
SI.No
</th>
<th>
Axis Type
</th>
<th>
X1 and X2 values
</th>
<th>
Example
</th>
</tr>
<tr>
<td>
1
</td>
<td>
CategoryAxis
</td>
<td>
Index based
</td>
<td>
X1 = 2, X2 = 3 (start point = 2nd index’s value and end point 3rd index value) 
</td>
</tr>

</tr>
<tr>
<td>
2
</td>
<td>
DateTimeCategoryAxis 
</td>
<td>
Index based 
</td>
<td>
X1 = 2, X2 = 3 (start point = 2nd index’s value and end point 3rd index value) 
</td>
</tr>

</tr>
<tr>
<td>
3
</td>
<td>
DateTimeAxis 
</td>
<td>
Value based 
</td>
<td>
X1 = “2015/01/31”, X2 = “2015/02/01” 
</td>
</tr>

</tr>
<tr>
<td>
4
</td>
<td>
TimeSpanAxis
</td>
<td>
Value based 
</td>
<td>
X1= 00:00:40 X2=00:00:50  
</td>
</tr>

</tr>
<tr>
<td>
5
</td>
<td>
Logarithmic Axis 
</td>
<td>
Value based 
</td>
<td>
X1= 50(XValue) X2=50(XValue) 
</td>
</tr>

</tr>
<tr>
<td>
6
</td>
<td>
Numerical Axis 
</td>
<td>
Value based 
</td>
<td>
X1= 10(XValue) X2=15(XValue)
</td>
</tr>
</table>

**DateTimeAxis**

The corresponding DateTime value will be given as values for X1 and X2 properties.

{% tabs %}

{% highlight xaml %}

        <chart:SfChart.PrimaryAxis>
            <chart:DateTimeAxis  />
        </chart:SfChart.PrimaryAxis>

        <chart:SfChart.SecondaryAxis>
            <chart:NumericalAxis />
        </chart:SfChart.SecondaryAxis>

        <chart:SfChart.Annotations>
            <chart:RectangleAnnotation  X1="2019/12/17" Y1="1200" X2="2020/02/19" Y2="1300" >
                    </chart:RectangleAnnotation>
        </chart:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

 			SfChart chart = new SfChart();
            chart.PrimaryAxis = new DateTimeAxis();
            chart.SecondaryAxis = new NumericalAxis();
            RectangleAnnotation annotation = new RectangleAnnotation()
            {
                X1 = new DateTime(2019,12,17), X2 = new DateTime(2020,02,19), Y1 = 1200, Y2 = 1300,  
            };
            chart.Annotations.Add(annotation);

{% endhighlight %}

{% endtabs %}

![WPF Chart with Annotation based on DareTimeAxis](Annotation_images/wpf-chart-datetime-annotation.jpg)

## Events

SfChart provides the following events in [`Annotation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#).

* [`Selected`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the annotation is selected.
* [`UnSelected`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when annotation is deselected.
* [`DragStarted`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html) - Occurs at the start of the dragging.
* [`DragDelta`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html) - Occurs when the drag takes place.
* [`DragCompleted`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html) - Occurs when the dragging is completed. You can cancel the dragging by using Cancel argument.
* [`DragEnter`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#) - Occurs when the cursor is moved over the annotation for dragging.
* [`DragLeave`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StraightLineAnnotation.html#)- Occurs when the cursor leaves the annotation after dragging.
* [`MouseDown`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when any mouse button is pressed while the pointer is over the annotation.
* [`MouseUp`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when any mouse button is released while the pointer is over the annotation.
* [`MouseLeftButtonDown`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the left mouse button is pressed while the mouse pointer is over the annotation.
* [`MouseRightButtonDown`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html)- Occurs when the right mouse button is pressed while the mouse pointer is over the annotation.
* [`MouseRightButtonUp`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the right mouse button is released while the mouse pointer is over the annotation.
* [`MouseMove`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the mouse pointer moves while over the annotation.
* [`MouseLeave`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html) - Occurs when the mouse pointer leaves the bounds of the annotation.

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.

## See also

[`How to display trackball label or tooltip over chart annotation`](https://www.syncfusion.com/kb/10791/how-to-display-trackball-label-or-tooltip-over-chart-annotation)

[`How to add annotations by using MVVM binding`](https://www.syncfusion.com/kb/4867/how-to-add-annotations-by-using-mvvm-binding)

[`How to change the cursor of the annotation`](https://www.syncfusion.com/kb/4848/how-to-change-the-cursor-of-the-annotation)

[`How to bind the ViewModel property to content template of a TextAnnotation`](https://www.syncfusion.com/kb/2639/how-to-bind-the-viewmodel-property-to-content-template-of-a-textannotation)

[`How to draw horizontal line in chart`]( https://www.syncfusion.com/kb/2850/how-to-draw-horizontal-line-in-chart)
