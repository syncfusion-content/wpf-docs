---
layout: post
title: Track ball | SfSparkline | wpf | Syncfusion
description: track ball
platform: wpf
control: SfSparkline
documentation: ug
---

# Track ball

This is used to indicate the value point on mouse move and this feature is applicable for line and area sparkline.

{% highlight xaml %}

<Syncfusion:SfLineSparkline 

                ItemsSource="{Binding UsersList}" 

                ShowTrackBall="True”

                YBindingPath="NoOfUsers">

  </Syncfusion:SfLineSparkline >
  
{% endhighlight %}

Following is the snapshot for track ball,

![](Track-ball_images/Track-ball_img1.png)