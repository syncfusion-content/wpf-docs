---
layout: post
title: Range-Settings
description: range settings
platform: wpf
control: Circular Gauge
documentation: ug
---

# Range Settings

## Ranges

Range is a visual element that begins and ends at specified values within a scale. These start and end values are set by the StartValue and EndValue properties of the range. A range’s UI is customized by the Stroke and StrokeThickness properties.



### Code Example

{% tabs %}
{% highlight xml %}



<syncfusion:SfCircularGauge x:Name="gauge">

<syncfusion:SfCircularGauge.MainScale>

<syncfusion:CircularScale >

<syncfusion:CircularScale.Ranges>

<syncfusion:CircularRange StartValue="0" EndValue="40" Stroke="Green" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="40" EndValue="60" Stroke="Yellow" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="60" EndValue="100" Stroke="Red" StrokeThickness ="10"/>

</syncfusion:CircularScale.Ranges>

</syncfusion:CircularScale>

</syncfusion:SfCircularGauge.MainScale>

</syncfusion:SfCircularGauge>
{% endhighlight %}


{% highlight C# %}


SfCircularGauge circularGauge = new SfCircularGauge();

CircularScale _mainscale = new CircularScale();

_mainscale.Ranges.Add(new CircularRange() { StartValue = 0, EndValue = 40, Stroke = new SolidColorBrush(Colors.Green), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 40, EndValue = 60, Stroke = new SolidColorBrush(Colors.Yellow), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 60, EndValue = 100, Stroke = new SolidColorBrush(Colors.Red), StrokeThickness = 10 });

circularGauge.MainScale = _mainscale;
this.Grid.Children.Add(circularGauge);
 {% endhighlight %}           

{% endtabs %}

###Screenshot

![](Range-Settings_images/Range-Settings_img1.png)





## Range Width Customization

Range start and end width can be customized by using the StartWidth and EndWidth property of range.

### Code Example

{% tabs %}
{% highlight xml %}





<syncfusion:SfCircularGauge x:Name="gauge">

<syncfusion:SfCircularGauge.Scales>

<syncfusion:CircularScale  RangePosition="Inside">

<syncfusion:CircularScale.Ranges>

<syncfusion:CircularRange StartValue="30" EndValue="100" Stroke="Red" StartWidth="2" EndWidth="20" />

</syncfusion:CircularScale.Ranges>

</syncfusion:CircularScale>

</syncfusion:SfCircularGauge.Scales>

</syncfusion:SfCircularGauge>
{% endhighlight %}



{% highlight C# %}




SfCircularGauge circularGauge = new SfCircularGauge();

CircularScale scale = new CircularScale();

scale.Ranges.Add(

new CircularRange() { 

StartValue = 30,

EndValue = 100, 

Stroke = new SolidColorBrush(Colors.Red),

StartWidth = 2,

EndWidth =20

});

circularGauge.Scales.Add(scale);

this.Grid.Children.Add(circularGauge);
{% endhighlight %}
{% endtabs %}


### Screenshot

![](Range-Settings_images/Range-Settings_img2.png)



## Binding Range Stroke

You can bind the range’s stroke to the tick lines and labels within its range by setting the BindRangeStrokeToLabels and BindRangeStrokeToTicks properties to true.

### Code Example

{% tabs %}
{% highlight xml %}


<syncfusion:SfCircularGauge x:Name="gauge">

<syncfusion:SfCircularGauge.MainScale>

<syncfusion:CircularScale  BindRangeStrokeToLabels="True"

   BindRangeStrokeToTicks="True">

<syncfusion:CircularScale.Ranges>

<syncfusion:CircularRange StartValue="0" EndValue="40" Stroke="Green" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="40" EndValue="60" Stroke="Yellow" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="60" EndValue="100" Stroke="Red" StrokeThickness ="10"/>

</syncfusion:CircularScale.Ranges>

</syncfusion:CircularScale>

</syncfusion:SfCircularGauge.MainScale>

</syncfusion:SfCircularGauge>

{% endhighlight %}

{% highlight C# %}



SfCircularGauge circularGauge = new SfCircularGauge();

CircularScale _mainscale = new CircularScale();

_mainscale.BindRangeStrokeToLabels = true;

_mainscale.BindRangeStrokeToTicks = true;

_mainscale.Ranges.Add(new CircularRange() { StartValue = 0, EndValue = 40, Stroke = new SolidColorBrush(Colors.Green), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 40, EndValue = 60, Stroke = new SolidColorBrush(Colors.Yellow), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 60, EndValue = 100, Stroke = new SolidColorBrush(Colors.Red), StrokeThickness = 10 });

circularGauge.MainScale = _mainscale;

this.Grid.Children.Add(circularGauge);

{% endhighlight %}

{% endtabs %}


### Screenshot:

![](Range-Settings_images/Range-Settings_img3.png)


## RangePosition

The range can be placed inside the scale, outside the scale, or on the scale by selecting one of the options available in the RangePosition property. These options are:

1. Inside
2. Outside
3. SetAsGaugeRim (Default)



### Code Example

{% tabs %}
{% highlight xml %}



<syncfusion:SfCircularGauge x:Name="gauge">

<syncfusion:SfCircularGauge.MainScale>

<syncfusion:CircularScale RangePosition="Outside">

<syncfusion:CircularScale.Ranges>

<syncfusion:CircularRange StartValue="0" EndValue="40" Stroke="Green" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="40" EndValue="60" Stroke="Yellow" StrokeThickness ="10"/>

<syncfusion:CircularRange StartValue="60" EndValue="100" Stroke="Red" StrokeThickness ="10"/>

</syncfusion:CircularScale.Ranges>

</syncfusion:CircularScale>

</syncfusion:SfCircularGauge.MainScale>

</syncfusion:SfCircularGauge>

{% endhighlight %}


{% highlight C# %}





SfCircularGauge circularGauge = new SfCircularGauge();

CircularScale _mainscale = new CircularScale();

_mainscale.RangePosition = RangePosition.Outside;

_mainscale.Ranges.Add(new CircularRange() { StartValue = 0, EndValue = 40, Stroke = new SolidColorBrush(Colors.Green), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 40, EndValue = 60, Stroke = new SolidColorBrush(Colors.Yellow), StrokeThickness = 10 });

_mainscale.Ranges.Add(new CircularRange() { StartValue = 60, EndValue = 100, Stroke = new SolidColorBrush(Colors.Red), StrokeThickness = 10 });

circularGauge.MainScale = _mainscale;

this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

### Screenshot:

![](Range-Settings_images/Range-Settings_img4.png)



