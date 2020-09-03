---
layout: post
title: Create cubic curve segments of connectors | Syncfusion
description: Create and editing simple cubic curve segments and adding mutilple cubic curve segments of connectors
platform: wpf
control: SfDiagram
documentation: ug
---

# Cubic Curve Segments

Cubic curve segments are used to create curve segments and the curves are configurable with end control points.

## how to create cubic curve segments

To create a Curve line, you should specify the segment as [CubicCurveSegment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html).

{% tabs %}
{% highlight xaml %}
<!--Initialize the Sfdiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Connectors>
        <!--Initialize the Connector Collection-->
        <syncfusion:ConnectorCollection>
            <!--create the connector with cubic curve segments-->
            <syncfusion:ConnectorViewModel SourcePoint="900,100" TargetPoint="1000,200">
                <syncfusion:ConnectorViewModel.Segments>
                    <syncfusion:ConnectorSegments>
                        <!--Specify the segment as cubic curve segment-->
                        <syncfusion:CubicCurveSegment/>
                    </syncfusion:ConnectorSegments>
                </syncfusion:ConnectorViewModel.Segments>
            </syncfusion:ConnectorViewModel>
        </syncfusion:ConnectorCollection>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
{% endhighlight %}

{% highlight C# %}
//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//create the connector with cubic bezier segments
ConnectorViewModel cubicBezierConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(900, 100),
    TargetPoint = new Point(1000, 200),
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        //Specify the segment as cubic curve segment
        new CubicCurveSegment()
    }
};

//Adding connector into Collection
(diagram.Connectors as ConnectorCollection).Add(cubicBezierConnector);

{% endhighlight %}
{% endtabs %}

![Cubic curve segments](Connector_images/Connector_img12.PNG)

## How to edit the cubic bezier segments

Cubic bezier segments are annotated with thumbs to represent the control points. Control points of the curve can be configured by clicking and dragging the control point thumbs which are consisting of dashed lines from source point and target point.

![Cubic curve segments](Connector_images/CubicSegment.PNG)

![control points editing at runtime using segment thumbs](Connector_images/Bezier3.gif)

## How to add multiple cubic bezier segments

'n' number of cubic bezier segments can be added into single connector by using [Point1](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html#Syncfusion_UI_Xaml_Diagram_CubicCurveSegment_Point1), [Point2](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html#Syncfusion_UI_Xaml_Diagram_CubicCurveSegment_Point2) and [Point3](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html#Syncfusion_UI_Xaml_Diagram_CubicCurveSegment_Point3) properties of `CubicCurveSegment` class. 

*   Point1: Specifies the left side control point of the segment.
*   Point2: Specifies the right side control point of the segment.
*   Point3: Specifies the end point point of the current cubic bezier segment and starting point to the next cubic bezier segment.

{% tabs %}
{% highlight xaml %}

<!--create the connector with cubic curve segments with points-->
<syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="300,300">
    <syncfusion:ConnectorViewModel.Segments>
        <syncfusion:ConnectorSegments>
            <syncfusion:CubicCurveSegment Point1="50,150" Point2="260,150" Point3="200,200"/>
            <syncfusion:CubicCurveSegment Point1="100,250" Point2="350,260" />
        </syncfusion:ConnectorSegments>
    </syncfusion:ConnectorViewModel.Segments>
</syncfusion:ConnectorViewModel>
                 
{% endhighlight %}

{% highlight C# %}

//create the connector with cubic bezier segments
ConnectorViewModel cubicBezierConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(300, 300),
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        //Specify the segment as cubic curve segment
        new CubicCurveSegment()
        {
            //Specifies the left side control point
            Point1 = new Point(50,150),
            //Specifies the right side control point
            Point2 = new Point(260,150),
            //Specifies the ending point of the segment
            Point3 = new Point(200,200),
        },
        new CubicCurveSegment()
        {
            Point1 = new Point(100,250),
            Point2 = new Point(350,260),
        }
    }
};

{% endhighlight %}
{% endtabs %}

Vectors also can be used to define the control points of the cubic bezier segments by using [Vector1](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html#Syncfusion_UI_Xaml_Diagram_CubicCurveSegment_Vector1), [Vector2](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.CubicCurveSegment.html#Syncfusion_UI_Xaml_Diagram_CubicCurveSegment_Vector2) properties of `CubicCurveSegment` class. 

{% tabs %}
{% highlight xaml %}

<!--create the connector with cubic curve segments with vector points-->
<syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="300,300">
    <syncfusion:ConnectorViewModel.Segments>
        <syncfusion:ConnectorSegments>
            <syncfusion:CubicCurveSegment Vector1="-50,50" Vector2="60,-50" Point3="200,200"/>
            <syncfusion:CubicCurveSegment Vector1="-100,50" Vector2="50,-40" />
        </syncfusion:ConnectorSegments>
    </syncfusion:ConnectorViewModel.Segments>
</syncfusion:ConnectorViewModel>
                 
{% endhighlight %}

{% highlight C# %}

//create the connector with cubic bezier segments
ConnectorViewModel cubicBezierConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(300, 300),
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        //Specify the segment as cubic curve segment
        new CubicCurveSegment()
        {
            //Specifies the left side control point as vector
            Vector1 = new Vector(-50,50),
            //Specifies the right side control point as vector
            Vector2 = new Vector(60,-50),
            //Specifies the ending point of the segment
            Point3 = new Point(200,200),
        },
        new CubicCurveSegment()
        {
            Vector1 = new Vector(-100,50),
            Vector2 = new Vector(50,-40),
        }
    }
};

{% endhighlight %}
{% endtabs %}

![Cubic curve segments](Connector_images/MultipleCubicSegments.PNG) &ensp;&ensp;&ensp;&ensp; ![Cubic curve segments](Connector_images/CubicSegmentEdit.png)

