---
layout: post
title: Auto scale Y axis when X axis is zoomed | wpf | Syncfusion
description: Learn here all about Auto-scale-Y-axis-when-X-axis-is-zoomed support in Syncfusion WPF Chart (Classic) control and more.
platform: wpf
control: Chart (Classic)
documentation: ug
---

## Auto scale Y axis when X axis is zoomed

 The auto scale of y-axis when the x-axis is zoomed can be achieved by the following steps:

1. Get the start and end value of the visible range of X axis. 
2. Filter out the point’s collection using the RecordFilters and get the points within that range.
3. Get the maximum and minimum value of Y axis.
4. Change the range of the Y axis with the interval.



The following code example must be given under the VisibleRangeChanged event.

{% tabs %}

{% highlight c# %}


void chartControl1_VisibleRangeChanged(object sender, EventArgs e)

        {

            MinMaxInfo xInfo = chartControl1.PrimaryXAxis.VisibleRange;



            double max = double.MinValue;

            double min = double.MaxValue;

            bool toChange = false;

            double start = 0;

            double end = 0;

           // 1.	Get the Start and End value of the visible range of X axis. 

            start = xInfo.Min + xInfo.Interval;

            end = xInfo.Max + xInfo.Interval;



            //2.	Filter out the point’s collection using the Record filter and get the points with in that range. 

            GetVisiblePoints(start, end,ref max,ref min,ref toChange);



          //  4.	Change the range of the Y axis with the interval. 

            double steps = (max-min)/5;



            if (toChange)

            {

                m_Min = min - steps;

                m_Max = max + steps;

                chartControl1.PrimaryYAxis.Range = new MinMaxInfo(m_Min, m_Max, steps);



                chartControl1.ZoomFactorY = 1;

            }

        }



 private void GetVisiblePoints(double start, double end, ref double max, ref double min, ref bool toChange)

        {

           ChartPointIndexer points =  this.chartControl1.Series[0].Points;

           Engine group = new Engine();

           group.SetSourceList(points);

           RecordFilterDescriptor rfd = new RecordFilterDescriptor("X",FilterLogicalOperator.And,new FilterCondition[]{new FilterCondition(FilterCompareOperator.GreaterThanOrEqualTo,start),new FilterCondition(FilterCompareOperator.LessThanOrEqualTo ,end)});



           // add the record filter to group engine

           group.TableDescriptor.RecordFilters.Add(rfd);

           // 3.	Get the maximum and minimum value of Y.

           foreach (Record rec in group.Table.FilteredRecords)

           {

               toChange = true;

               double[] yvalues = (double[])rec["YValues"];

               max = yvalues[0] > max ? yvalues[0] : max;

               min = yvalues[0] < min ? yvalues[0] : min;

           } 



        } 	

{% endhighlight  %}
{% highlight vbnet %}



Private Sub chartControl1_VisibleRangeChanged(ByVal sender As Object, ByVal e As EventArgs)

Dim xInfo As MinMaxInfo = chartControl1.PrimaryXAxis.VisibleRange



Dim max As Double = Double.MinValue

Dim min As Double = Double.MaxValue

Dim toChange As Boolean = False

Dim start As Double = 0

Dim [end] As Double = 0

' 1. Get the Start and End value of the visible range of X axis. 

start = xInfo.Min + xInfo.Interval

[end] = xInfo.Max + xInfo.Interval



'2. Filter out the point’s collection using the Record filter and get the points within that range. 

GetVisiblePoints(start, [end],max,min,toChange)



' 4. Change the range of the Y axis with the interval. 

Dim steps As Double = (max-min)/5



If toChange Then

m_Min = min - steps

m_Max = max + steps

chartControl1.PrimaryYAxis.Range = New MinMaxInfo(m_Min, m_Max, steps)



chartControl1.ZoomFactorY = 1

End If

End Sub



Private Sub GetVisiblePoints(ByVal start As Double, ByVal [end] As Double, ByRef max As Double, ByRef min As Double, ByRef toChange As Boolean)

Dim points As ChartPointIndexer = Me.chartControl1.Series(0).Points

Dim group As Engine = New Engine()

group.SetSourceList(points)

Dim rfd As RecordFilterDescriptor = New RecordFilterDescriptor("X",FilterLogicalOperator.And,New FilterCondition(){New FilterCondition(FilterCompareOperator.GreaterThanOrEqualTo,start),New FilterCondition(FilterCompareOperator.LessThanOrEqualTo,[end])})



' add the record filter to group engine

group.TableDescriptor.RecordFilters.Add(rfd)

' 3. Get the maximum and minimum value of Y.

For Each rec As Record In group.Table.FilteredRecords

toChange = True

Dim yvalues() As Double = CType(rec("YValues"), Double())

max = If(yvalues(0) > max, yvalues(0), max)

min = If(yvalues(0) < min, yvalues(0), min)

Next rec

End Sub
{% endhighlight  %}


{% endtabs %}