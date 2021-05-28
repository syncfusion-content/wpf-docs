---
layout: post
title: Chart-Events in WPF Chart Control | Syncfusion
description: Learn here all about Chart-Events support in Syncfusion WPF Chart (Classic) control, its elements and more details.
platform: wpf
control: Chart (Classic)
documentation: ug
---
# Chart-Events in WPF Chart (Classic)

## Chart Axis Events

ChartAxis events that could be used to track the Axis changes are as follows.

Axis.Changed

This event is triggered whenever any properties of the axis are changed.



{% highlight c#  %}

Area.PrimaryAxis.Changed += new EventHandler(PrimaryAxis_Changed);   



// PrimaryAxis.Changed Event

void PrimaryAxis_Changed(object sender, EventArgs e)

{

   MessageBox.Show(Area.PrimaryAxis.ToString());

}

Axis.RangeChanged
{% endhighlight  %}

Both Primary and Secondary Axis comes with Rangechanged event. This event occurs when the Range of the axis is changed. We could get the old and new range from this event.
{% highlight c# %}


///<summary>

///Event triggered when Axis range is changed.

///</summary>

///<param name="sender">Sender Axis of event.</param>

///<param name="e">ChartAxisRangeArgument that returns old and new range values.</param>



void PrimaryAxis_RangeChanged(object sender, ChartAxisRangeArgs e)

{

    Console.WriteLine (e.OldValue.Start.ToString();

    Console.WriteLine (e.OldValue.End.ToString();

    Console.WriteLine (e.NewValue.Start.ToString();

    Console.WriteLine (e.NewValue.End.ToString();

}
{% endhighlight  %}

## Chart Series Mouse Events

The following are the mouse events and their corresponding descriptions:


<table>
<tr>
<th>
Event</th><th>
Description</th></tr>
<tr>
<td>
MouseClick</td><td>
This event is handled when any mouse button is clicked, while mouse pointer is over the series.</td></tr>
<tr>
<td>
MouseDown</td><td>
This event is handled when any mouse button is pressed, while mouse pointer is over the series.</td></tr>
<tr>
<td>
MouseEnter</td><td>
This event is handled when mouse pointer enters the bounds of the series.</td></tr>
<tr>
<td>
MouseLeave</td><td>
This event is handled when mouse pointer leaves the bounds of the series.</td></tr>
<tr>
<td>
MouseUp</td><td>
This event is handled when any mouse button is released over the series.</td></tr>
<tr>
<td>
MouseLeftButtonUp</td><td>
This event is handled when left mouse button is released over the series.</td></tr>
<tr>
<td>
MouseLeftButtonDown</td><td>
This event is handled when left mouse button is pressed over the series.</td></tr>
<tr>
<td>
MouseRightButtonUp</td><td>
This event is handled when right mouse button is released over the series.</td></tr>
<tr>
<td>
MouseRightButtonDown</td><td>
This event is handled when right mouse button is pressed over the series.</td></tr>
</table>
These events can be initialized using the following lines of code.

{% tabs %}

{% highlight xaml %}


<sfchart:ChartSeries Data="0 3 1 4 2 5 3 9 6 4 7 3 8 5 9 11" Type="Pie" MouseClick="ChartSeries_MouseClick"

MouseHover="ChartSeries_MouseHover"/>
{% endhighlight  %}
{% highlight c# %}

ChartSeries chartSeries = new ChartSeries();

this.MouseClick += new EventHandler(ChartSeries_MouseClick);



private void ChartSeries_MouseClick(object sender, EventArgs e)

{

// Your code here

}
{% endhighlight  %}

{% endtabs %}

## Chart MouseEventArgs

ChartMouseEventArgs are the arguments returned when the mouse events are triggered by ChartSeries. ChartMouseEventArgs returns the segment on which the mouse events are triggered along with default mouse event args. This event args can be used to perform customization of a segment when a mouse event is encountered. The segment returns different values that can be used to perform calculations or operations. The following lines of code demonstrates how ChartMouseEventArgs can be used to retrieve information about the ChartSeries segment.


{% highlight c# %}

series.MouseClick += new ChartMouseEventHandler(series_MouseClick);

static void series_MouseClick(object sender, ChartMouseEventArgs e)

{

ChartPoint point = (ChartPoint)e.Segment.CorrespondingPoints[0].DataPoint;

MessageBox.Show("X = " + point.X.ToString() + "\n" + "Y = " + point.Y.ToString());

}
{% endhighlight  %}


![Chart-Controls_img221](Chart-Controls_images/Chart-Controls_img221.jpeg)


