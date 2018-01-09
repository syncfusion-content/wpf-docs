---
layout: post
title: Gauge Customization | OlapGauge | wpf | Syncfusion
description: gauge customization
platform: wpf
control: OlapGauge
documentation: ug
---

# Gauge Customization

## Layout Customization

OlapGauge provides support to display multiple gauges in a structured layout. You can customize the layout by using the `ColumnsCount` and `RowsCount` properties. These properties are used to specify the number of columns and rows for displaying the control.

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

![](Gauge-Customization_images/Gauge-customization.png)

## Gauge header

Gauge header is the combination of details about the measure and KPI. The header components of the OlapGauge can be hidden by using the property of `ShowGaugeHeaders` as specified in the following code snippet:

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

![](Gauge-Customization_images/Gauge-customization-header.png)

## Gauge label

The visibility of gauge labels that are displayed inside the gauge can be toggled with the help of `ShowGaugeLabels` property. The following code snippet shows how to hide labels of the OlapGauge:

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

![](Gauge-Customization_images/Gauge-customization-label.png)

## Gauge factor

Gauge factor component can be hidden by using the property of `ShowGaugeFactors` as specified in the below code snippet:

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

![](Gauge-Customization_images/Gauge-customization-factor.png)