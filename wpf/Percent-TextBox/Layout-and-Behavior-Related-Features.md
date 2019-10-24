---
layout: post
title: Layout and Behavior Related Features| PercentTextBox  | Wpf | Syncfusion
description: layout and behavior related features
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Layout and Behavior Related Features

## IsReadOnly

If the PercentTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears.

## CornerRadius

The Corner Radius describes the degree to which corners are rounded. This property has no default value.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" PercentValue="123" Height="25" Width="150" CornerRadius="4"/>

{% endhighlight %}
{% endtabs %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img1.png)


## Negative foreground

The Foreground of the PercentTextBox can be customized based on the Value property. When Negative a value is assigned to the PercentValue property, then automatically the NegativeForeground value gets assigned to Foreground property.

N> The NegativeForeground in the PercentTextBox can be enabled by setting the ApplyNegativeForeground property to true.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
                            CornerRadius="2" PercentValue="-123" NegativeForeground="Red" 
                            ApplyNegativeForeground="True"/>

{% endhighlight %}
{% endtabs %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img2.png)


## Zero color

The Foreground of the PercentTextBox can be customized based on the PercentValue property. When zero is assigned as a value to the PercentValue property, then automatically the ZeroColor is set to the Foreground property.

N> The ZeroColor in the PercentTextBox can be enabled by setting the ApplyZeroColor property to true.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
                            CornerRadius="2" PercentValue="-123" ZeroColor="Green" 
                            ApplyZeroColor="True"/>

{% endhighlight %} 
{% endtabs %}






![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img3.png)


## EnterToMoveNext

If you press the Enter key in the PercentTextBox then the Focus moves to the next element in the application. To enable this feature you have to set the EnterToMoveNext property to true.

## TextSelectionOnFocus

The TextSelectionOnFocus property allows the PercentTextBox to act like standard text boxes when the cursor hovers over. 

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img4.png)


![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img5.png)


