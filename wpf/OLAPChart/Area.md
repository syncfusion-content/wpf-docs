---
layout: post
title: Area| OlapChart | Wpf | Syncfusion
description: Area
platform: wpf
control: OlapChart
documentation: ug
---

# Area

OlapArea is a ChartArea, which contains the ChartSeries and ChartAxes.

## Adding Chart Header

Chart header is the title of the chart, which is usually displayed at the top center of the ChartArea. The following illustration displays the Chart header displayed in the chart area:

![](Area_images/Area_img1.png)

In general, ChartSeries contains the ChartArea instance, which can be used to customize the OlapArea. The following code sample describes how to add a chart header to an OlapChart:

{% tabs %}

{% highlight c# %}

this.olapchart1.Series[0].Area.Header = "Simple Report";
	
{% endhighlight %}

{% highlight vbnet %}

Me.olapchart1.Series(0).Area.Header = "Simple Report"
	
{% endhighlight %}

{% endtabs %}
   
N> The series will be available only after the data is bound to the control. In other words, you can access the series property of the OlapChart only after the call to DataBind() is made.

## Area Customization

OlapArea is basically derived from the ChartArea class belonging to the base Chart WPF control. So, it has the advantage of the customization options available in the ChartArea. However, 3D charts and multiple chart areas are not supported in an OlapChart. So, those customizations are not applicable.

The following are the frequently used customization options that are available in the ChartArea:

* Background
* GridBackground
* Foreground
* FontFamily
* FontSize
* FontStyle
* FontWeight
* BorderBrush
* BorderThickness
* CornerRadius

OlapArea allows you to customize the border properties. The following code sample explain how these properties can be customized:

### BorderBrush

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].Area.BorderBrush = Brushes.Black;

{% endhighlight %}

{% highlight vbnet %}
 
Me.olapChart.Series(0).Area.BorderBrush = Brushes.Black

{% endhighlight %}

{% endtabs %}

### BorderThickness

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].Area.BorderThickness = new Thickness(2);

{% endhighlight %}

{% highlight vbnet %}
 
Me.olapChart.Series(0).Area.BorderThickness = New Thickness(2)

{% endhighlight %}

{% endtabs %}

### CornerRadius

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].Area.CornerRadius = new CornerRadius(5);

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).Area.CornerRadius = New CornerRadius(5)

{% endhighlight %}

{% endtabs %}

### Background

{% tabs %}

{% highlight c# %}

this.olapChart.Series[0].Area.Background = Brushes.SkyBlue;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).Area.Background = Brushes.SkyBlue

{% endhighlight %}

{% endtabs %}

### GridBackground

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].Area.GridBackground = Brushes.LightBlue;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).Area.GridBackground = Brushes.LightBlue

{% endhighlight %}

{% endtabs %}

### FontStyle

{% tabs %}

{% highlight c# %}
 
this.olapChart.Series[0].Area.FontStyle = FontStyles.Italic;

{% endhighlight %}

{% highlight vbnet %}
  
Me.olapChart.Series(0).Area.FontStyle = FontStyles.Italic

{% endhighlight %}
 
{% endtabs %}
