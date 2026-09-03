---
layout: post
title: Restrict User Selection in WPF Rating | Syncfusion®
description: Restrict user selection in WPF Rating limits rating input based on application requirements, ensuring controlled interactions.
platform: wpf
control: Rating
documentation: ug
---

# Restrict User Selection in WPF Rating

The Rating control provides support to changeable or unchangeable values. This is achieved using the `IsReadOnly` property. When this property is set to true, the rating value becomes unchangeable. By default, value of this property is false.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemsCount="5" IsReadOnly="True"/>
	
{% endhighlight %}

{% highlight C# %}

public MainWindow()
{
    InitializeComponent();
    SfRating rating = new SfRating();
    rating.IsReadOnly = true;
    Content = rating;
}

{% endhighlight %}

{% endtabs %}

![Read only support in WPF Rating control](images/readOnly.png)
