---
layout: post
title: Gauge Customization in WPF Olap Gauge control | Syncfusion
description: Learn about Gauge Customization support in Syncfusion WPF Olap Gauge control, its elements and more details.
platform: wpf
control: OLAP Gauge
 documentation: ug
---

# Gauge Customization in WPF Olap Gauge

## Layout customization

The OLAP gauge displays multiple gauges in a structured layout. You can customize the layout by using the `ColumnsCount` and `RowsCount` properties. These properties are used to specify the number of columns and rows for displaying the control.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" RowsCount="2" ColumnsCount="2"/>

{% endhighlight %}

{% highlight c# %}

this.OlapGauge1.ColumnsCount = 2;
this.OlapGauge1.RowsCount = 2;

{% endhighlight %}

{% highlight vb %}

Me.OlapGauge1.ColumnsCount = 2
Me.OlapGauge1.RowsCount = 2

{% endhighlight %}

{% endtabs %}

![WPF OLAPGauge displays multiple gauges in a structured layout](Gauge-Customization_images/Gauge-customization.png)

## Gauge header

The gauge header is the combination of details about the measure and KPI. The header components of the OLAP gauge can be hidden by using the `ShowGaugeHeaders` property as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" ShowGaugeHeaders="False"/>

{% endhighlight %}

{% highlight c# %}

OlapGauge1.ShowGaugeHeaders = false;

{% endhighlight %}

{% highlight vb %}

OlapGauge1.ShowGaugeHeaders = False

{% endhighlight %}

{% endtabs %}

![Hidden header component in WPF OLAPGauge](Gauge-Customization_images/Gauge-customization-header.png)

## Gauge label

The visibility of gauge labels that are displayed inside the gauge can be toggled with the help of `ShowGaugeLabels` property. The following code snippet shows how to hide labels of the OLAP gauge.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" ShowGaugeLabels="False"/>

{% endhighlight %}

{% highlight c# %}

OlapGauge1.ShowGaugeLabels = false;

{% endhighlight %}

{% highlight vb %}

OlapGauge1.ShowGaugeLabels = False

{% endhighlight %}

{% endtabs %}

![Hide the label in WPF OLAPGauge](Gauge-Customization_images/Gauge-customization-label.png)

## Gauge factor

The gauge factor component can be hidden by using the `ShowGaugeFactors` property as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapGauge x:Name="OlapGauge1" ShowGaugeFactors="False"/>

{% endhighlight %}

{% highlight c# %}

OlapGauge1.ShowGaugeFactors = false;

{% endhighlight %}

{% highlight vb %}

OlapGauge1.ShowGaugeFactors = False

{% endhighlight %}

{% endtabs %}

![Hide the gauge factor component in WPF OLAPGauge](Gauge-Customization_images/Gauge-customization-factor.png)
