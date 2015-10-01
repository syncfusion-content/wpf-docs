# ColorBar

ColorBar is used to represent the value range in surface via colors. We can define color bar for surface chart in the below code. 

XAML:

{% highlight xml %}

<chart:SfSurfaceChart />
      <chart:SfSurfaceChart.ColorBar>
           <chart:ColorBar DockPosition="Right" ></chart:ColorBar>
      </chart:SfSurfaceChart.ColorBar>
<chart:SfSurfaceChart />
	
{% endhighlight %}

C#:

{% highlight c# %}

SfSurfaceChart surface = new SfSurfaceChart();
surface.ColorBar = new ChartColorBar();
surface.DockPosition = ChartDock.Right;
	
{% endhighlight %}

The following properties are used to customize the color bar. 

### Properties

<table>
<tr>
<td>
******Name******<br/><br/></td><td>
******Description******<br/><br/></td></tr>
<tr>
<td>
DockPosition<br/><br/></td><td>
Get or Set the dock value that is used to position the color bar at top, bottom, left and right.  <br/><br/></td></tr>
<tr>
<td>
ShowLabel<br/><br/></td><td>
Get or Set bool that represent whether showing the label in color bar. <br/><br/></td></tr>
</table>