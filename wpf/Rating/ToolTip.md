---
layout: post
title: ToolTip in WPF Rating Control | Syncfusion®
description: Learn about ToolTip support in the Syncfusion® WPF Rating (SfRating) control, including its features and more.
platform: WPF
control: SfRating
documentation: ug
---

# ToolTip in WPF Rating (SfRating)

A tooltip provides additional information about objects that may not be immediately recognizable to users and do not have direct UI representation. In the WPF `SfRating` control, the tooltip displays the data of the `Value` property. It appears when the mouse hovers over the rating items and disappears when the mouse is moved away. The tooltip can be enabled or disabled using the `ShowToolTip` property, which defaults to `true`.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" ShowToolTip="True" >
    </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.ShowToolTip = true;
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![SfRating tooltip](images/ToolTip.png)

### Set Tooltip Precision

The `AutoToolTipPrecision` property defines the number of decimal places displayed in the tooltip. To configure `AutoToolTipPrecision`, set the precision mode to `Exact`.

> **Note:** The default value of `AutoToolTipPrecision` is 1.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemsCount="5" Precision="Exact" AutoToolTipPrecision="6" >
    </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.Precision = Precision.Exact;
    rating.AutoToolTipPrecision = 6;
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![SfRating tooltip precision](images/toolTipPrecision.png)
