---
layout: post
title: Markers
description: markers
platform: wpf
control: Sparkline
documentation: ug
---

# Markers

Markers are used to indicate the value point for line and area series, and we can customize with different template.
{% highlight html %}

  <Syncfusion:SfLineSparkline 

               ItemsSource="{Binding UsersList}" 

MarkerVisibility="Visible"

               YBindingPath="NoOfUsers">

  </Syncfusion:SfLineSparkline >
{% endhighlight  %}
Following is the snapshot for markers,

![C:/Users/ApoorvahR/Desktop/8.png](Markers_images/Markers_img1.png)



