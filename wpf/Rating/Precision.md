---
layout: post
title: Precision in WPF SfRating | Syncfusion®
description: Precision in WPF SfRating enables whole, half, or custom rating values, allowing accurate and flexible user feedback collection.
platform: wpf
control: SfRating
documentation: ug
---

# Precision in WPF Rating

The precision mode defines the accuracy level of the Rating control. It has Standard, Half, and Exact options. By default, the precision mode of the Rating control is set to `Standard`.

## Standard

When the precision mode of the Rating control is set to `Standard`, the rating item will be filled completely based on the rating value.

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

![Rating standard precision mode](images/Precision_Standard.png)

## Half

When the precision mode of the Rating control is set to `Half`, the rating item will be filled partially based on the rating value.

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

![Rating half precision mode](images/Precision_Half.png)

## Exact

If the precision mode of Rating is set to `Exact`, the rating item will be filled exactly based on the rating value.

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

![Rating exact precision mode](images/Precision_Exact.png) 
