---
layout: post
title: Restrict User Selection | SfRating | wpf | Syncfusion
description: restrict user selection
platform: wpf
control: SfRating
documentation: ug
---

# Restrict User Selection 

The SfRating control provides support to changeable or unchangeable values. This is achieved using the `IsReadOnly` property. When this property is set to true, the rating value becomes unchangeable. By default, value of this property is false.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemsCount="5" IsReadOnly="True"/>
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainWindow()
{
    InitializeComponent();
    rating = new SfRating();
    rating.IsReadOnly = true;
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![SfRating read only](images/readOnly.jpg)
