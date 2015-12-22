---
layout: post
title: Layout and Behavior Related Features | IntegerTextBox | wpf | Syncfusion
description: layout and behavior related features
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Layout and Behavior Related Features

## IsReadOnly

If the IntegerTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears.

## CornerRadius

The Corner Radius describes the degree to which corners are rounded. This property has no default value.

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img1.png)



## Negative Foreground

The Foreground of the IntegerTextBox can be customized based on the Value property. When a Negative value is assigned to the Value property, then automatically the NegativeForeground value gets assigned to the Foreground property.

Note: The NegativeForeground in the integer textbox can be enabled by setting the ApplyNegativeForeground property to true.



{% highlight xml %}



<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" Value="-123" 

                           ApplyNegativeForeground="True" NegativeForeground="Red"/>

{% endhighlight %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img2.png)



## Zero Color

The Foreground of the IntegerTextBox can be customized based on the Value property. When zero is assigned as a value to the Value property, then automatically the ZeroColor is set to the Foreground property.

Note: The ZeroColor in the integer textbox can be enabled by setting the ApplyZeroColor property to true.



{% highlight xml %}



<syncfusion:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" Value="0" 

                           ApplyZeroColor="True" ZeroColor="Magenta"/>

{% endhighlight %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img3.png)



## EnterToMoveNext

If you press the Enter key in the IntegerTextBox then the Focus moves to the next element in the application. To enable this feature you have to set the EnterToMoveNext property to true.

## TextSelectionOnFocus

The TextSelectionOnFocus property allows the IntegerTextBox to act like standard text boxes when the cursor hovers over. 

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img4.png)



![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img5.png)



