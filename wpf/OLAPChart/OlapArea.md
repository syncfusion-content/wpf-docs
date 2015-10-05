---
layout: post
title: OlapArea| OLAP Chart | Wpf | Syncfusion
description: OlapArea
platform: wpf
control: OLAP Chart
documentation: ug
---
# OlapArea

The OlapArea is a ChartArea, which contains the ChartSeries and ChartAxes. This section discusses the following topics.



## How to add a Chart header to an OlapArea?

Chart header is the title of the chart, which is usually displayed at the top center of the ChartArea.  The following illustration displays the Chart header displayed in the chart area:

![](Core-Features_images/Core-Features_img1.png)


## Steps to Add a Chart Header

The steps to add a chart header are as follows:

1. In general, ChartSeries contains the ChartArea instance, which can be used to customize the OlapArea. The following code snippet describes how to add a chart header to an OlapChart:

  

{% highlight c# %}

    this.olapchart1.Series[0].Area.Header = "Simple report";
	
{% endhighlight  %}


{% highlight vbnet %}


    Me.olapchart1.Series(0).Area.Header = "Simple report"
	
{% endhighlight  %}

   

N> The series will be available only after the data is bound to the control. In other words, you can access the series property of the OlapChart only after the call to DataBind() is made.


##  How to customize the appearance of an OlapArea?

OlapArea is basically derived from the ChartArea of the Essential Chart WPF. So, it has the advantage of the customization options available in the ChartArea. However, 3D charts and multiple chart areas are not supported in an OlapChart. So, those customizations are not applicable.

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

These properties are explained in the following topics:

* How to customize the border properties of the OlapArea.
* How to customize the background properties of the OlapArea.
* How to customize the font properties of the OlapArea.
* How to customize the border properties of the OlapArea?


OlapArea allows you to customize the border properties. The following code snippets explain how these properties can be customized:

## BorderBrush

 {% highlight c# %}
 
   



this.olapchart1.Series[0].Area.BorderBrush = Brushes.Black;

 {% endhighlight %}




 {% highlight vbnet %}
  
  



      Me.olapchart1.Series(0).Area.BorderBrush = Brushes.Black

 {% endhighlight %}









## BorderThickness

 {% highlight c# %}
 
   



       this.olapchart1.Series[0].Area.BorderThickness = new Thickness(2);

 {% endhighlight %}




 {% highlight vbnet %}
  
   



      Me.olapchart1.Series(0).Area.BorderThickness = New Thickness(2)

 {% endhighlight %}











## CornerRadius

 {% highlight c# %}
 
   



       this.olapchart1.Series[0].Area.CornerRadius = new CornerRadius(5);

 {% endhighlight %}




 {% highlight vbnet %}
  
   



      Me.olapchart1.Series(0).Area.CornerRadius = New CornerRadius(5)

 {% endhighlight %}













![](Core-Features_images/Core-Features_img2.png)


## How to customize the background properties of the OlapArea?

OlapArea allows you to customize the background properties in an easy manner. The following code snippets explain how to customize the OlapArea with various background properties:

 {% highlight c# %}
 
   



       this.olapchart1.Series[0].Area.Background = Brushes.SkyBlue;

 {% endhighlight %}




 {% highlight vbnet %}
  
  



       Me.olapchart1.Series(0).Area.Background = Brushes.SkyBlue

 {% endhighlight %}

## Background











### GridBackground

 {% highlight c# %}
 
    



       this.olapchart1.Series[0].Area.GridBackground = Brushes.LightBlue;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



       Me.olapchart1.Series(0).Area.GridBackground = Brushes.LightBlue

 {% endhighlight %}













![](Core-Features_images/Core-Features_img3.png)


## How to customize the font properties of the OlapArea?

Typically, the primary axis and the secondary axis font settings will override the font properties applied to their content in the OlapArea. To set the font properties such as Foreground, FontFamily, FontSize, and FontWeight consider using the font properties available in the primary and the secondary axis.

## FontStyle

 {% highlight c# %}
 
   



       this.olapchart1.Series[0].Area.FontStyle = FontStyles.Italic;

 {% endhighlight %}




 {% highlight vbnet %}
  
  




      Me.olapchart1.Series(0).Area.FontStyle = FontStyles.Italic

 {% endhighlight %}




