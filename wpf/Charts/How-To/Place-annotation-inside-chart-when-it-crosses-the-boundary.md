---
layout: post
title: Overview of Syncfusion SfChart WPF.
description: Overview and the highlighting features (Chart elements and interactive features) of the Essential WPF Chart (SfChart) control.
platform: wpf
control: SfChart
documentation: ug
---

# Position the annotation inside the Chart Area

SfChart allows you to clip the annotation if the annotation crosses the boundary by setting [`EnableClipping`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.Annotation~EnableClipping.html#) property to True as in the below code snippet.

{% tabs %}

{% highlight xaml %}

            <chart:SfChart.Annotations>            
                  
                <chart:ImageAnnotation ImageSource="rain.png"  X1="6" Y1="16" X2="9" Y2="18" EnableClipping="True"></chart:ImageAnnotation>

            </chart:SfChart.Annotations>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

        ImageAnnotation image = new ImageAnnotation()
            {
                X1 = 6,
                Y1 = 16,
                X2 = 9,
                Y2 = 18,
                ImageSource = new BitmapImage(new Uri("rain.png", UriKind.RelativeOrAbsolute)),
                 EnableClipping=true
            };

        chart.Annotations.Add(image);

{% endhighlight %}

{% endtabs %}

The following screenshot explains that even when x value is provided out of bounds the image annotation is placed inside the chart area.

![Annotation clipping support in WPF Chart](/How_to_images/Annotation_Clipping.jpeg)