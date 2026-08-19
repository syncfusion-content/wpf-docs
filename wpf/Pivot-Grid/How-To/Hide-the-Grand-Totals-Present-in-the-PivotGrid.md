---
layout: post
title: How to Hide Grand Totals in WPF Pivot Grid | Syncfusion®
description: Hide the grand totals in Syncfusion® WPF Pivot Grid control by setting the ShowGrandTotals property to false.
platform: wpf
control: PivotGridControl
documentation: ug
---

# How to Hide Grand Totals in WPF Pivot Grid

It can be achieved by setting the property `ShowGrandTotals` to false. By default, PivotGrid displays Grand Total for both column and row headers. 
It can be mentioned either in *XAML* or in *Code-Behind*.

If through *XAML*, please refer the below code sample.

{% highlight xaml %}

    <Grid>
       <syncfusion:PivotGridControl x:Name="pivotGrid" ShowGrandTotals="False">
       </syncfusion:PivotGridControl>
    </Grid>

{% endhighlight %}

Else if through *Code-Behind*, please refer the below code sample.

{% highlight C# %}

    public MainWindow()
        {
            InitializeComponent();
            this.pivotGrid.ShowGrandTotals = false;
        }

{% endhighlight %}
