---
layout: post
title: Rendering Type in WPF Smith Chart | Syncfusion®
description: Rendering type in the WPF Smith Chart determines how series data is displayed, enabling different visualization styles and layouts.
platform: wpf
control: SfSmithChart
documentation: ug
---

# Rendering Type in WPF Smith Chart

WPF Smith Chart plots the transmission line in two different ways by using the `RenderingType` property. The two ways are given below.


## Impedance

In the impedance smith chart, normalized resistance circles and normalized reactance curves are drawn from right to left.  Axis label ranges start from left to right.

Impedance is the default rendering type of SmithChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart RenderingType="Impedance">
            
</syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

SfSmithChart chart = new SfSmithChart();
chart.RenderingType = RenderingType.Impedance;

{% endhighlight %}
    
{% endtabs %}

![SmithChart Impedance Chart](Rendering-Type_images/Rendering-Type_img1.png)

## Admittance

In the admittance smith chart, normalized resistance circles and normalized reactance curves are drawn from left to right.  Axis label ranges start from right to left.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart RenderingType="Admittance">
            
</syncfusion:SfSmithChart>

{% endhighlight %}

{% highlight C# %} 

SfSmithChart chart = new SfSmithChart();
chart.RenderingType = RenderingType.Admittance;

{% endhighlight %}
    
{% endtabs %}

![SmithChart Admittance Chart](Rendering-Type_images/Rendering-Type_img2.png)
