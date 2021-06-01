---
layout: post
title: ToolTip in WPF Rating control | Syncfusion
description: Learn here all about ToolTip support in Syncfusion WPF Rating (SfRating) control, its elements and more.
platform: wpf
control: SfRating
 documentation: ug
---

# ToolTip in WPF Rating (SfRating)

Tooltip provides additional information about objects that are unfamiliar to users and are not directly displayed in UI. In the WPF SfRating control, tooltip shows the data of `Value` property. It will be displayed when the mouse is hovered over the rating items, and it will be disappeared when the mouse is moved from the rating items. The tooltip is enabled or disabled using the `ShowToolTip` property. The default value of this property is true.

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

### Set tooltip precision

The `AutoToolTipPrecision` property sets the number precisions to be displayed after decimal point in tooltip. To set AutoToolTipPrecision, set the precision mode to `Exact`.

N> The default value of this property is 1.

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
