---
layout: post
title: ColorBar | SfSurfaceChart | wpf | Syncfusion
description: colorbar
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# ColorBar

ColorBar is used to represent the value range in surface via colors. You can define ColorBar for surface chart as shown in the following code example. 

{% tabs %}

{% highlight xaml %}

<chart:SfSurfaceChart />

	<chart:SfSurfaceChart.ColorBar>

		<chart:ColorBar DockPosition="Right" ></chart:ColorBar>
	   
	</chart:SfSurfaceChart.ColorBar>
	  
<chart:SfSurfaceChart />
	
{% endhighlight %}

{% highlight c# %}

SfSurfaceChart surface = new SfSurfaceChart();

surface.ColorBar = new ChartColorBar();

surface.DockPosition = ChartDock.Right;
	
{% endhighlight %}

{% endtabs %}


The following properties are used to customize the ColorBar. 

### Properties

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
DockPosition<br/><br/></td><td>
Gets or sets the dock value that is used to position the ColorBar at top, bottom, left and right.  <br/><br/></td></tr>
<tr>
<td>
ShowLabel<br/><br/></td><td>
Gets or sets bool that represent whether showing the label in ColorBar. <br/><br/></td></tr>
</table>