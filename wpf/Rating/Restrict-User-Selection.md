---
layout: post
title: Restrict User Selection in WPF Rating Control | Syncfusion®
description: Learn all about the Restrict User Selection feature in the Syncfusion® WPF Rating (SfRating) control.
platform: WPF
control: SfRating
documentation: ug
---

# Restrict User Selection in WPF Rating (SfRating)

The `SfRating` control allows for both changeable and unchangeable rating values. This functionality is controlled by the `IsReadOnly` property. Setting this property to `true` makes the rating value unchangeable. By default, this property is set to `false`.

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

![SfRating Read-Only](images/readOnly.png)
