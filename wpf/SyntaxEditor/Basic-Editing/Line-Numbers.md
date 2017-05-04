---
layout: post
title: Line Numbers property of the Edit Control for WPF
description: Line Numbers property of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

## Line Numbers

Edit WPF enables users to display line numbers for the content in the Edit Control. Line numbers can be displayed or hidden by using the **ShowLineNumber** property of the EditControl class. The following lines of code can be used to display or hide line numbers in Edit Control. 

{% highlight xaml %}

<sfedit:EditControl Name="editControl" ShowLineNumber="False">

</sfedit:EditControl>




{% endhighlight %}

{% highlight c# %}

editControl.ShowLineNumber = false;

{% endhighlight %}


The following image displays hidden Line Numbers



![](Line-Numbers_images/Line-Numbers_img1.jpeg)


