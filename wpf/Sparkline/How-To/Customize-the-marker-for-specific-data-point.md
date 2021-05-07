---
layout: post
title: Customize the marker for specific data point | SfSparkline | wpf | Syncfusion
description: customize the marker for specific data point in Syncfusion WPF SfSparkline control, its elements and more.
platform: wpf
control: SfSparkline
documentation: ug
---

# Customize the marker for specific data point

We can customize the marker for specific data point with custom template for LineSparkline and AreaSparkline, in order to customize the marker we need to inherit the MarkerTemplateSelector class and override the SelectTemplate method.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfLineSparkline x:Name="sparkline" MarkerVisibility="Visible" ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

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

			return base.SelectTemplate(x, y);

	}

}

{% endhighlight %}

{% endtabs %}



Following is the snapshot for custom marker position,

![Customize-the-marker-for-specific-data-point_img1](Customize-the-marker-for-specific-data-point_images/Customize-the-marker-for-specific-data-point_img1.png)
