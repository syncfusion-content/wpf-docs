---
layout: post
title: Gridines are pattern of lines | Syncfusion.
description: Visual guidance while dragging or arranging the objects
platform: wpf
control: SfDiagram
documentation: ug
---

# Gridlines

## Appearance

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

The `SnapConstraints` property of SnapSettings enables you to show/hide the gridlines.

{% tabs %}
{% highlight xaml %}
<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="Diagram" >
  <!--Initialize SnapSettings-->
  <syncfusion:SfDiagram.SnapSettings >
    <syncfusion:SnapSettings SnapConstraints="ShowLines"/>
  </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight C# %}

//Shows both Horizontal and Vertical Gridlines
diagram.SnapSettings.SnapConstraints = SnapConstraints.ShowLines;

{% endhighlight %}
{% endtabs %}

![Snap to Gridlines](Gridlines_images/Gridlines_img1.jpeg)

## Customization

The `HorizontalGridLines` and `VerticalGridLines` properties allow us to customize the appearance of the gridlines. 

{% tabs %}
{% highlight xaml %}

 <!--Style for HorizontalGridlines-->
        <local:Gridlinestyle x:Key="horizontalline">
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="Blue"/>
                <Setter Property="StrokeDashArray" Value="3"/>
            </Style>
        </local:Gridlinestyle>
        <!--Style for VerticalGridlines-->
        <local:Gridlinestyle x:Key="verticalline">
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="Blue"/>
                <Setter Property="StrokeDashArray" Value="3"/>
            </Style>
        </local:Gridlinestyle>

        <syncfusion:SnapSettings SnapConstraints="ShowLines">
                    <!--Initialize HorizontalGridlines-->
                    <syncfusion:SnapSettings.HorizontalGridlines>
                        <syncfusion:Gridlines Strokes="{StaticResource horizontalline}"/>
                    </syncfusion:SnapSettings.HorizontalGridlines>
                    <!--Initialize VerticalGridlines-->
                    <syncfusion:SnapSettings.VerticalGridlines>
                        <syncfusion:Gridlines Strokes="{StaticResource verticalline}" />
                    </syncfusion:SnapSettings.VerticalGridlines>
                </syncfusion:SnapSettings>
{% endhighlight %}

{% highlight C# %}
 
{% endhighlight %}
{% endtabs %}

![Snap to Gridlines](Gridlines_images/CustomGridlines.png)

## Line Intervals

Thickness and the space between gridlines can be customized by using `LinesInterval` property. In the line Interval collections, values at the odd places are referred as the thickness of lines and the values at the even places are referred as the space between gridlines.

{% tabs %}
{% highlight xaml %}
 <!--Initializes the double collection-->
        <local:Intervals x:Key="Intervals">
            <sys:Double>4</sys:Double>
            <sys:Double>14</sys:Double>
            <sys:Double>0.25</sys:Double>
            <sys:Double>15</sys:Double>
            <sys:Double>0.25</sys:Double>
            <sys:Double>15</sys:Double>
            <sys:Double>0.25</sys:Double>
            <sys:Double>15</sys:Double>
            <sys:Double>0.25</sys:Double>
            <sys:Double>15</sys:Double>
        </local:Intervals>

        <!--Initialize HorizontalGridlines-->
                    <syncfusion:SnapSettings.HorizontalGridlines>
                        <syncfusion:Gridlines Strokes="{StaticResource horizontalline}" LinesInterval="{StaticResource Intervals}"></syncfusion:Gridlines>
                    </syncfusion:SnapSettings.HorizontalGridlines>
                    <!--Initialize VerticalGridlines-->
                    <syncfusion:SnapSettings.VerticalGridlines>
                        <syncfusion:Gridlines Strokes="{StaticResource verticalline}" LinesInterval="{StaticResource Intervals}"></syncfusion:Gridlines>
                    </syncfusion:SnapSettings.VerticalGridlines>
{% endhighlight %}

{% highlight C# %}
//Creates collection for the double values.
public class Intervals : List<double>
{
}
{% endhighlight %}
{% endtabs %}

![Snap to Gridlines](Gridlines_images/LineIntervals.png)