---
layout: post
title: How to customize a data point marker in WPF Sparkline | Syncfusion®
description: Customize a data point marker in the WPF Sparkline to apply distinct styles and improve the visibility of specific data points.
platform: wpf
control: SfSparkline
documentation: ug
---

# How to customize a data point marker in WPF Sparkline

You can customize the marker for a specific data point with a custom template for `SfLineSparkline` and `SfAreaSparkline`. To customize the marker, inherit the `MarkerTemplateSelector` class and override the `SelectTemplate` method.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline
    x:Name="sparkline"
    MarkerVisibility="Visible"
    ItemsSource="{Binding UsersList}"
    YBindingPath="NoOfUsers">

    <Syncfusion:SfLineSparkline.MarkerTemplateSelector>
        <local:CustomMarkersTemplateSelector MarkerHeight="10" MarkerWidth="10"/>
    </Syncfusion:SfLineSparkline.MarkerTemplateSelector>

</Syncfusion:SfLineSparkline>
		
{% endhighlight %}


{% highlight c# %}

public class CustomMarkersTemplateSelector : MarkerTemplateSelector
{
    protected override DataTemplate SelectTemplate(double x, double y)
    {
        if (y == MaximumY)
        {
            DataTemplate markerTemplate = Application.Current.Resources["markerTemplate"] as DataTemplate;
            return markerTemplate;
        }
        else
        {
            return base.SelectTemplate(x, y);
        }
    }
}

{% endhighlight %}

{% endtabs %}



The following is a snapshot of the custom marker position.

![Customize-the-marker-for-specific-data-point_img1](Customize-the-marker-for-specific-data-point_images/Customize-the-marker-for-specific-data-point_img1.png)
