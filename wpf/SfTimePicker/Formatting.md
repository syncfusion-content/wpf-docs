---
layout: post
title: Formatting | SfTimePicker | WPF | Syncfusion
description: SfTimePicker control provides formatting option that allows users to format the display text in various ways.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Formatting

The SfTimePicker control allows users to format the display text in various ways.



## Using the FormatString

The FormatString property determines the format specifier by which the display text has to be formatted.

The example below shows how to create a time picker with a [Long Time pattern](http://msdn.microsoft.com/en-us/library/system.globalization.datetimeformatinfo.longtimepattern(v=vs.71).aspx).

{% highlight xaml %}

  



	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfTimePicker VerticalAlignment="Center" 

                                   Width="200" Margin="15"

                                   FormatString="HH:mm:ss"/>

	</Grid>

{% endhighlight %}

![SfTimePicker format string](Features_images/Features_img1.png)

## Specifying format for the TimeSelector

The SelectorFormatString property used to specify format for the TimeSelector



{% highlight xaml %}

	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <syncfusion:SfTimePicker HorizontalAlignment="Center" VerticalAlignment="Center" 

                                   Width="200" Margin="15"

                                   SelectorFormatString="HH:mm:ss"/>
	</Grid>

{% endhighlight  %}


![SfTimePicker selection format string](Features_images/Features_img2.png)

N>  A detailed explanation of standard date time formatting is available[here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers is influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.
