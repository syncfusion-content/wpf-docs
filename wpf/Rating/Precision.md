---
layout: post
title: Precision Settings in WPF Rating Control | Syncfusion®
description: Explore how precision settings in the Syncfusion® WPF Rating (SfRating) control affect rating accuracy and filling behavior.
platform: WPF
control: SfRating
documentation: ug
---

# Precision Settings in WPF Rating (SfRating)

The precision mode in the SfRating control defines its accuracy level, specifying how rating items are filled. The available options are Standard, Half, and Exact, with the default mode being `Standard`.
## Standard

With the precision mode set to `Standard`, each rating item is filled entirely based on the rating value.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemsCount="5" Precision="Standard"></rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.Precision = Precision.Standard;
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![SfRating standard precision mode](images/Precision_Standard.png)

### Half

When the precision mode of the SfRating control is set to `Half`, the rating item will be filled partially based on the rating value.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Precision="Half"></rating:SfRating>	
    
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    ItemsCount = 5;
    rating.Precision = Precision.Half;
    Content = rating;
}

{% endhighlight %} 

{% endtabs %}

![SfRating half precision mode](images/Precision_Half.png)

### Exact

If the precision mode of SfRating is set to `Exact`, the rating item will be filled exactly based on the rating value.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating ItemsCount="5" Precision="Exact"></rating:SfRating>

{% endhighlight %}

{% highlight c# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemsCount = 5;
    rating.Precision = Precision.Exact;
    Content = rating;
}

{% endhighlight %} 

{% endtabs %}

![SfRating exact precision mode](images/Precision_Exact.png) 
