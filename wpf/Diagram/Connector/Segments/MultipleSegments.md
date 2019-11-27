---
layout: post
title: How to add multiple and different types of segments into a single connector and how to edit the multiple connectors | Syncfusion
description: How to create the multiple segments for a connector
platform: wpf
control: SfDiagram
documentation: ug
---

# Multiple segments

Multiple segments can be added in a single connector one after another. you can add above four type of segments in single connector at a time.

{% tabs %}
{% highlight xaml %}
<!--create the connector with multiple segments segments-->
<syncfusion:ConnectorViewModel SourcePoint="100,400" TargetPoint="550,700" >
    <syncfusion:ConnectorViewModel.Segments>
        <syncfusion:ConnectorSegments>
            <!--Specify the segment as quadratic curve segment-->
            <syncfusion:QuadraticCurveSegment Point1="50,600" Point2="200,480"/>
            <!--Specify the segment as straight segment-->
            <syncfusion:StraightSegment Point="300,600"/>
            <!--Specify the segment as orthogonal segment-->
            <syncfusion:OrthogonalSegment>
                <syncfusion:OrthogonalSegment.Length>
                    <syncfusion:DoubleExt Value ="100"/>
                </syncfusion:OrthogonalSegment.Length>
            </syncfusion:OrthogonalSegment>
        </syncfusion:ConnectorSegments>
    </syncfusion:ConnectorViewModel.Segments>
</syncfusion:ConnectorViewModel>
{% endhighlight %}
{% highlight C# %}

//create the connector with multiple segments
ConnectorViewModel multipleSegments = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 400),
    TargetPoint = new Point(550, 700),
    Segments = new ObservableCollection<IConnectorSegment>()
    {
        //Specify the segment as Quadratic curve segment
        new QuadraticCurveSegment()
        {
            Point1 = new Point(50, 600),
            Point2 = new Point(200, 480),
        },
        //Specify the segment as straight segment
        new StraightSegment()
        {
            Point = new Point(300,600),
        },
        //Specify the segment as orthogonal segment
        new OrthogonalSegment()
        {
            Length = 100,
        },
    },
};

{% endhighlight %}
{% endtabs %}

![Multiple Segments](Connector_images/MultipleSegments.PNG)

For Adding Connector and Segments sample, please refer to [Segments](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AddConnector1815455151.zip "Segments")

