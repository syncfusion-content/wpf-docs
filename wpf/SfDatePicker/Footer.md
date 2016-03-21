---
layout: post
title: Deals with the Visibility of Done and Cancel Buttons of SfDatePicker contol for WPF
description: Deals with the Visibility of Done and Cancel Buttons of SfDatePicker contol for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Footer

## Done and Cancel Buttons

The done and cancel buttons can be made visible or hidden using the following properties.

## ShowDoneButton

The ShowDoneButton property is used to show or hide the done button. The default value is true.

The following code sample shows how to hide the done button:

{% highlight xaml %}

	<syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

                    <Setter Property="ShowDoneButton" Value="False"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>  

        </syncfusion:SfDatePicker>
		
{% endhighlight %}

![](Features_images/Features_img11.png)




## ShowCancelButton

The ShowCancelButton property is used to show or hide the cancel button. The default value is true.

The following code sample shows how to hide the cancel button:

{% highlight xaml %}



	<syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

			<Setter Property="ShowCancelButton" Value="False"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>        
			
			</syncfusion:SfDatePicker>

			{% endhighlight  %}
			
![](Features_images/Features_img12.png)