---
layout: post
title: Gridlines are pattern of lines | Syncfusion.
description: Visual guidance while dragging or arranging the objects
platform: wpf
control: SfDiagram
documentation: ug
---

# Gridlines

**Gridlines** are crisscross lines drawn in diagram page like the lines on traditional graph paper. It helps to position the diagram elements on the diagram page.

The `SnapConstraints` property of SnapSettings class enables you to control the visibility of the gridlines.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram" >
  <!--Initialize SnapSettings constraints to show Gridlines-->
  <syncfusion:SfDiagram.SnapSettings >
    <syncfusion:SnapSettings SnapConstraints="ShowLines"/>
  </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight C# %}
//Initialize SfDiagram
SfDiagram Diagram = new SfDiagram();
//Initialize SnapSettings constraints to show Gridlines
Diagram.SnapSettings = new SnapSettings()
    {
        SnapConstraints = SnapConstraints.ShowLines,
    };
{% endhighlight %}
{% endtabs %}

| Enum  | Value| Output |
|---|---|---|
| SnapConstraints| None | ![Snap to Gridlines](Gridlines_images/GridlinesNone.png) |
|  |VerticalLines | ![Snap to Gridlines](Gridlines_images/GridlinesVertical.png) |
|  | HorizontalLines| ![Snap to Gridlines](Gridlines_images/GridlinesHorizontal.png) |
|  | ShowLines| ![Snap to Gridlines](Gridlines_images/GridlinesShowLines.png) |

## Change grid lines appearance

The `HorizontalGridLines` and `VerticalGridLines` properties of SnapSettings class allows you to customize the appearance of the gridlines. 

{% tabs %}
{% highlight xaml %}

<!--Style for Gridlines-->
<local:Gridlinestyle x:Key="gridlinestyle">
    <Style TargetType="Path">
        <Setter Property="Stroke" Value="Blue"/>
        <Setter Property="StrokeDashArray" Value="3"/>
    </Style>
</local:Gridlinestyle>

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram" >
    <!--Initialize SnapSettings-->
    <syncfusion:SfDiagram.SnapSettings>
        <syncfusion:SnapSettings SnapConstraints="ShowLines">
            <!--Initialize HorizontalGridlines-->
            <syncfusion:SnapSettings.HorizontalGridlines>
                <syncfusion:Gridlines Strokes="{StaticResource gridlinestyle}"/>
            </syncfusion:SnapSettings.HorizontalGridlines>
            <!--Initialize VerticalGridlines-->
            <syncfusion:SnapSettings.VerticalGridlines>
                <syncfusion:Gridlines Strokes="{StaticResource gridlinestyle}"/>
            </syncfusion:SnapSettings.VerticalGridlines>
        </syncfusion:SnapSettings>
    </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Initialize SfDiagram
SfDiagram Diagram = new SfDiagram();
//Style for HorizontalGridlines
Style PathStyle = new Style(typeof(Path));
SolidColorBrush Strokes = new SolidColorBrush(Colors.Black);
PathStyle.Setters.Add(new Setter(Shape.StrokeProperty, new SolidColorBrush(Colors.Blue)));
PathStyle.Setters.Add(new Setter(Shape.StrokeDashArrayProperty, new DoubleCollection() { 3, 3 }));

//Initialize SnapSettings constraints with HorizontalGridlines and VerticalGridlines values
Diagram.SnapSettings = new SnapSettings()
    {
        SnapConstraints = SnapConstraints.ShowLines,
        HorizontalGridlines = new Gridlines()
            {
            },
        VerticalGridlines = new Gridlines()
            {
            },
    };

    //Creates collection for the style.
    public class Gridlinestyle : List<Style>
    {
    }
{% endhighlight %}
{% endtabs %}

![Snap to Gridlines](Gridlines_images/CustomGridlines.png)

## Change grid spacing

The thickness and the space between gridlines can be customized by using `LinesInterval` property of Gridlines class. The `LinesInterval` is a type of List<double> collection where the values at the odd indexes are referred as the thickness of lines and the values at the even indexes are referred as the space between gridlines.

{% tabs %}
{% highlight xaml %}
<!--Initializes the double collection-->
<local:Intervals x:Key="Intervals">
    <!--Thickness of the grid line-->
    <sys:Double>0.25</sys:Double>
    <!--Space between each gridlines-->
    <sys:Double>10</sys:Double>
    <sys:Double>0.5</sys:Double>
    <sys:Double>20</sys:Double>
    <sys:Double>1</sys:Double>
    <sys:Double>30</sys:Double>
    <sys:Double>1.25</sys:Double>
    <sys:Double>40</sys:Double>
    <sys:Double>1.5</sys:Double>
    <sys:Double>50</sys:Double>
</local:Intervals>

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram" >
    <syncfusion:SfDiagram.SnapSettings>
        <syncfusion:SnapSettings SnapConstraints="ShowLines">
            <!--Initialize HorizontalGridlines-->
            <syncfusion:SnapSettings.HorizontalGridlines>
                <syncfusion:Gridlines LinesInterval="{StaticResource Intervals}" />
            </syncfusion:SnapSettings.HorizontalGridlines>
            <!--Initialize VerticalGridlines-->
            <syncfusion:SnapSettings.VerticalGridlines>
                <syncfusion:Gridlines LinesInterval="{StaticResource Intervals}"/>
            </syncfusion:SnapSettings.VerticalGridlines>
        </syncfusion:SnapSettings>
    </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight C# %}

//Initialize SfDiagram
SfDiagram Diagram = new SfDiagram();

//Initializes the double collection
List<double> Intervals = new List<double>() { 0.25, 10, 0.5, 20, 1, 30, 1.25, 40, 1.5, 50 };
//Initialize SnapSettings constraints with HorizontalGridlines and VerticalGridlines values
Diagram.SnapSettings = new SnapSettings()
    {
        SnapConstraints = SnapConstraints.ShowLines,
        HorizontalGridlines = new Gridlines()
            {
                LinesInterval = Intervals,
            },
        VerticalGridlines = new Gridlines()
            {
                LinesInterval = Intervals,
            },
    };

//Creates collection for the double values.
public class Intervals : List<double>
{
}
{% endhighlight %}
{% endtabs %}

![Snap to Gridlines](Gridlines_images/LineIntervals.png)
