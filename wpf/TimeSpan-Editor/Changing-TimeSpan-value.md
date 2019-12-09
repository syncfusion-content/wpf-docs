---
layout: post
title: Changing-the-timespan-value
description: changing the timespan value
platform: wpf
control: TimeSpanEdit
documentation: ug
---

## Editing value

This section describes how to edit the value in `TimeSpanEdit` control.

### By Programatically

You can also change the value of timespan using this code.

{% tabs %}

{% highlight C# %}

//Create the instance of TimeSpanEdit

TimeSpanEdit timespan = new TimeSpanEdit();

timespan.Width = 150;

timespan.Height = 30;

timespan.Value = new TimeSpan(3,5,4,3);

//Adding control to the window

this.Content = timespan;

{% endhighlight %}

{% endtabs %}

### Using keyboard and mouse wheel

You can also change the timespan value by using up/down arrow keys by selecting the field or you can be incremented or decremented by scrolling using MouseWheel.

![](Getting-Started_images/scrolling1.png)

![](Getting-Started_images/scrolling2.png)


### Mouse click and drag

You can increment or decrement the values by enable the `EnableExtendedScrolling` value as `true` and click mouse and drag, over the control to change value.

### Clicking up down arrow button

The SpinArrowButtons can be used to increase or decrease the values in any field.

![](Getting-Started_images/sp1.png)

![](Getting-Started_images/sp2.png)

## Field navigation

-- In `TimeSpanEdit` control, we have the automatic field navigation after validate the value is given to corresponding field.

-- You can also press the key to move to the field.

Press "d" - you will navigate to `day` field.
Press "h" - you will navigate to `hour` field.
Press "m" - you will navigate to `Minute` field.
Press "s" - you will navigate to `Second` field.

-- If the format is like this "d'days' h'hours' m'minute' s'second'" and if you press the character key, next to field to navigate the selection to next.
