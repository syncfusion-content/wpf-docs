---
layout: post
title: Set-the-interval-where-the-numeric-values-are-increased-or-decreased-in-the-UpDown-control
description: set the interval where the numeric values are increased or decreased in the updown control 
platform: wpf
control: UpDown Control
documentation: ug
---

# Set the interval where the numeric values are increased or decreased in the UpDown control 

The Step property is used to specify the interval to be incremented or decremented in the UpDown control when the repeat buttons are clicked. The Step value can be set for the UpDown control as shown in the following code example. Here the Step value is set to 3 so that the value in the UpDown control increases or decreases by 3 when you click the repeat buttons.
{% highlight xml %}

 [XAML]

<syncfusion:UpDown Name="upDown" Step="3">

</ syncfusion:UpDown> 

{% endhighlight %}

{% highlight C# %}

[C#]

UpDown upDown = new UpDown();

upDown.Step = 3;
{% endhighlight %}


