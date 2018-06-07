---
layout: post
title: Getting Started documentation of the Edit control for WPF
description: Getting Started documentation of the Edit control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

# Getting Started

This section explains how to get started with the EditControl.

## Adding EditControl to an application

The EditControl can be added to an application by using the Visual Studio.

### Creating an EditControl using XAML 

1. Drag and drop the EditControl available in the Visual Studio Toolbox as follows.

![](Getting-Started_images/Getting-Started_img1.jpeg)


N> If the EditControl is not listed in the toolbox, add it manually from the Syncfusion.Edit.Wpf assembly which is to be added to the project references folder.

The EditControl can be created in XAML as follows.

{% tabs %}

{% highlight XAML %}
<syncfusion:EditControl x:Name="editControl1" BorderBrush="Black" BorderThickness="1" Background="White" Foreground="Black" HorizontalAlignment="Left" Height="300" Margin="0" VerticalAlignment="Top" Width="300"/>

{% endhighlight %}

{% endtabs %}


### Creating an EditControl using C#

The EditControl can be created in C# as follows.

{% tabs %}

{% highlight C# %}

[C#]

EditControl EditControl = new EditControl();

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.jpeg)



