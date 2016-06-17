---
layout: post
title: Add gridlines behind nodes and connectors to ease alignments.
description: How to add gridlines behind Nodes and Connectors?
platform: wpf
control: SfDiagram
documentation: ug
---

#Gridlines

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

##Customize the gridlines visibility

The `SnapConstraints` property of SnapSettings enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

{% highlight xaml %}

<!--Initialize SfDiagram-->
<diagram:SfDiagram x:Name="diagram"> 
  <!--Initialize SnapSettings-->		
  <diagram:SfDiagram.SnapSettings>
    <diagram:SnapSettings SnapConstraints="ShowLines"/>
  </diagram:SfDiagram.SnapSettings>
</diagram:SfDiagram>

{% endhighlight %}

{% highlight C# %}

//Shows both Horizontal and Vertical Gridlines
diagram.SnapSettings.SnapConstraints = SnapConstraints.ShowLines;

{% endhighlight %}

![](Gridlines_images/Gridlines_img1.jpeg)

To show only horizontal/vertical gridlines or to hide gridlines, refer to [SnapConstraints](/wpf/sfdiagram/Constraints#SnapConstraints "SnapConstraints").

##Appearance

You can customize the appearance of the gridlines by using a set of predefined properties. The `HorizontalGridLines` and `VerticalGridLines` properties allow to customize the appearance of the gridlines. The following code example illustrates how to customize the appearance of gridlines.

{% highlight C# %}

//Creates collection for the style.
public class Gridlinestyle : List<Style>
{

}
	
{% endhighlight %}

{% highlight xaml %}

<!--Style for HorizontalGridlines-->
<local:Gridlinestyle x:Key="Horizontalgridline">
	<Style TargetType="Path">
    	<Setter Property="Stroke" Value="Blue" ></Setter>
        <Setter Property="StrokeDashArray" Value="2"></Setter>
	</Style>
</local:Gridlinestyle>

<!--Style for VerticalGridlines-->
<local:Gridlinestyle x:Key="Verticalgridline">
	<Style TargetType="Path">
		<Setter Property="Stroke" Value="Blue" ></Setter>
    	<Setter Property="StrokeDashArray" Value="2"></Setter>
	</Style>
</local:Gridlinestyle>

{% endhighlight %}

{% highlight xaml %}

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagramcontrol">
	<syncfusion:SfDiagram.SnapSettings>
    	<syncfusion:SnapSettings SnapConstraints="ShowLines">
        	<!--Initialize HorizontalGridlines-->
              	<syncfusion:SnapSettings.HorizontalGridlines>
                	<syncfusion:Gridlines Strokes="{StaticResource Horizontalgridline}">
                	</syncfusion:Gridlines>
				</syncfusion:SnapSettings.HorizontalGridlines>
                 
			<!--Initialize VerticalGridlines-->
            <syncfusion:SnapSettings.VerticalGridlines>
            	<syncfusion:Gridlines Strokes="{StaticResource Verticalgridline}">
                </syncfusion:Gridlines>
            </syncfusion:SnapSettings.VerticalGridlines>
		</syncfusion:SnapSettings>
   </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>

{% endhighlight %}

![](Gridlines_images/Gridlines_img2.jpeg)

###Line Intervals

Thickness and the space between gridlines can be customized by using `LineInterval` property. In the lineInterval collections, values at the odd places are referred as the thickness of lines and the values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% highlight C# %}

//Creates collection for the style.
public class Gridlinestyle : List<Style>
{

}

//Creates collection for the double values.
public class Intervals : List<double>
{

}
	
{% endhighlight %}

{% highlight xaml %}

<!--Initializes the double collection-->
<local:Intervals x:Key="Intervals">
	<sys:Double>1.25</sys:Double>
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

<!--Style for HorizontalGridlines-->
<local:Gridlinestyle x:Key="Horizontalgridline">
	<Style TargetType="Path">
    	<Setter Property="Stroke" Value="Blue" ></Setter>
        <Setter Property="StrokeDashArray" Value="2"></Setter>
	</Style>
</local:Gridlinestyle>

<!--Style for VerticalGridlines-->
<local:Gridlinestyle x:Key="Verticalgridline">
	<Style TargetType="Path">
		<Setter Property="Stroke" Value="Blue" ></Setter>
    	<Setter Property="StrokeDashArray" Value="2"></Setter>
	</Style>
</local:Gridlinestyle>

{% endhighlight %}

{% highlight xaml %}

<!--Initialize SfDiagram-->
<syncfusion:SfDiagram x:Name="diagramcontrol">
	<syncfusion:SfDiagram.SnapSettings>
    	<syncfusion:SnapSettings SnapConstraints="ShowLines">
        	<!--Initialize HorizontalGridlines-->
              	<syncfusion:SnapSettings.HorizontalGridlines>
                	<syncfusion:Gridlines Strokes="{StaticResource Horizontalgridline}" LinesInterval="{StaticResource Intervals}">
                	</syncfusion:Gridlines>
				</syncfusion:SnapSettings.HorizontalGridlines>
                 
			<!--Initialize VerticalGridlines-->
            <syncfusion:SnapSettings.VerticalGridlines>
            	<syncfusion:Gridlines Strokes="{StaticResource Verticalgridline}" LinesInterval="{StaticResource Intervals}">
                </syncfusion:Gridlines>
            </syncfusion:SnapSettings.VerticalGridlines>
		</syncfusion:SnapSettings>
   </syncfusion:SfDiagram.SnapSettings>
</syncfusion:SfDiagram>

{% endhighlight %}

![](Gridlines_images/Gridlines_img3.jpeg)

#Snapping

##Snap To Lines

This feature allows the Diagram objects to snap to the nearest interaction of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the SnapConstraints property of SnapSettings. The following code example illustrates how to enable/disable the snapping to gridlines.

{% highlight C# %}

//Enables snapping to both the horizontal and vertical lines.
diagram.SnapSettings.SnapConstraints = SnapConstraints.SnapToLines;

{% endhighlight %}

To enable/disable snapping to horizontal/vertical lines, refer to **SnapConstraints**

##Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram. A Node can be snapped with its neighboring objects based on certain alignments. Such alignments are visually represented as smart guides.

diagramControl.SnapSettings.SnapToObject determines whether Nodes can be snapped to objects.

Snapping to objects can be enabled by assigning values other than SnapToObject.None to SfDiagram.SnapSettings.SnapToObject.

The following code illustrates how to enable/disable the smart guide.

{% highlight C# %}

//Enables or disables the default behaviors of the Snapping in SfDiagram.
diagram.SnapSettings.SnapConstraints = SnapConstraints.All;

//Disables the default behaviors snapping Nodes/Connectors to objects.
diagram.SnapSettings.SnapToObject = SnapToObject.None;

{% endhighlight %}