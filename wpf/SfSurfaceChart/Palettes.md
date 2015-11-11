---
layout: post
title: Palettes | SfSurfaceChart | wpf | Syncfusion
description: palettes
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Palettes

Surface chart provides options to apply different kinds of palettes.

Some of the predefined palettes include:

* Metro
* AutumnBrights
* FloraHues
* Pineapple
* TomotoSpectrum
* RedChrome
* PurpleChrome
* BlueChrome
* GreenChrome
* Elite
* LightCandy
* SandyBeach

### Applying Predefined Brushes

Using the above palette you can apply a set of predefined brushes to surface chart as shown in the following code example. 

{% highlight xaml %}

<chart:SfSurfaceChart Palette="Metro" />
	
{% endhighlight %}

![](surface_chart_images/surface_chart_img12.jpeg)


### Applying Custom Brushes

The custom palette option enables you to define your own color brushes for the Palette using ColorModel property as given in the following code example.

{% highlight xaml %}

<chart:SfSurfaceChart Palette="Custom" >

	<Syncfusion:SfSurfaceChart.ColorModel>

			<Syncfusion:ChartColorModel>
			
				<Syncfusion:ChartColorModel.CustomBrushes>
				
					<SolidColorBrush Color="Blue"/>	
					
					<SolidColorBrush Color="Lime"/>
					
					<SolidColorBrush Color="Yellow"/>
												
					<SolidColorBrush Color="OrangeRed"/>
					
				</Syncfusion:ChartColorModel.CustomBrushes>
				
			</Syncfusion:ChartColorModel>
			
	</Syncfusion:SfSurfaceChart.ColorModel>
	   
<chart:SfSurfaceChart />
	
{% endhighlight %}

![](surface_chart_images/surface_chart_img13.jpeg)