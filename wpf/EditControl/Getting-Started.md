---
layout: post
title: Getting Started documentation of the Edit control for WPF
description: Getting Started documentation of the Edit control for WPF
platform: wpf
control: Edit Control
documentation: ug
---

# Getting Started

This section guides you on getting started with the EditControl control. It covers the following topics:

##  Adding EditControl control to an Application

The EditControl  control can be added to an application by using Visual Studio 

### Creating the EditControl Control using XAML 

1. Drag and drop the **EditControl** available in the Visual Studio **Toolbox** as shown below. 

![](Getting-Started_images/Getting-Started_img1.jpeg)




N> If the Edit control is not listed in the toolbox, add it manually from the Syncfusion.Edit.Wpf assembly.The Syncfusion.Edit .Wpf assembly has to be added also to the project References folder.

The EditControl control can be created in XAML as follows.

{% highlight xaml %}
<syncfusion:EditControl x:Name="editControl1" BorderBrush="Black" BorderThickness="1" Background="White" Foreground="Black" HorizontalAlignment="Left" Height="300" Margin="0" VerticalAlignment="Top" Width="300"/>



{% endhighlight %}


### Creating the EditControl Control using C#

The EditControl control can be created in C# as follows:



{% highlight c# %}

[C#]

EditControl EditControl = new EditControl();

{% endhighlight %}



![](Getting-Started_images/Getting-Started_img3.jpeg)



