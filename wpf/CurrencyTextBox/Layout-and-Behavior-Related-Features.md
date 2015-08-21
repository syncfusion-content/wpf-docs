---
layout: post
title: Layout-and-Behavior-Related-Features
description: layout and behavior related features
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Layout and Behavior Related Features

## IsReadOnly

If the CurrencyTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears.

## CornerRadius

The Corner Radius describes the degree to which corners are rounded. This property has no default value.



{% highlight xml %}





<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Value="123" Height="25" Width="150" CornerRadius="4"/>

{% endhighlight %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img1.png)



## Negative Foreground

The Foreground of the CurrencyTextBox can be customized based on the Value property. When Negative value is assigned to the Value property, then automatically the NegativeForeground value gets assigned to the Foreground property.

> Note: The NegativeForeground in the CurrencyTextBox can be enabled by setting the ApplyNegativeForeground property to true.


{% highlight xml %}





<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 

                            CornerRadius="2" Value="-123" NegativeForeground="Red" 

                            ApplyNegativeForeground="True"/>

{% endhighlight %}

![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img2.png)



## Zero Color

The Foreground of the CurrencyTextBox can be customized based on the Value property. When zero is assigned as a value to the Value property, then automatically the ZeroColor is set to the Foreground property.

> Note: The ZeroColor in the CurrencyTextBox can be enabled by setting the ApplyZeroColor property to true.



{% highlight xml %}





<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 

                            CornerRadius="2" Value="0" ZeroColor="Magenta" 

                            ApplyZeroColor="True"/>
{% endhighlight %}


![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img3.png)



## EnterToMoveNext

If you press the Enter key in the CurrencyTextBox then the Focus moves to the next element in the application. To enable this feature you have to set the EnterToMoveNext property to true.

## TextSelectionOnFocus

The TextSelectionOnFocus property allows the CurrencyTextBox to act like standard text boxes when the cursor hovers over. 



![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img4.png)





![](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img5.png)



