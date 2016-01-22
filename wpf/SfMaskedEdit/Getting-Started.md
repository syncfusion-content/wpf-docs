---
layout: post
title: Getting Started| SfMaskedEdit | Wpf | Syncfusion
description: getting started
platform: wpf
control: SfMaskedEdit
documentation: ug
---

# Getting Started

## Add SfMaskedEdit to an application

Namespace : Syncfusion.Windows.Controls.Input

Assembly: Syncfusion.SfInput.WPF

Dependentassembly: Syncfusion.SfShared.WPF

### Create the SfMaskedEdit control by using XAML

Create a new WPF application in the Visual Studio and follow the steps given.

1. Drag and drop the SfMaskedEdit control from the toolbox to the designer. It generates the SfMaskedEdit as shown:

   ![](Getting-Started_images/Getting-Started_img1.png)



The following code example shows how to create the SfMaskedEdit from XAML.

{% highlight xaml %}



<syncfusion:SfMaskedEdit HorizontalAlignment="Left" Margin="103,143,0,0" TextWrapping="Wrap" Text="SfMaskedEdit" VerticalAlignment="Top" Width="255" Height="46"/>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.jpeg)



### Create the SfMaskedEdit control by using C#

To create a MaskedEdit control, use the following code.

{% highlight C# %}



SfMaskedEdit maskededit = new SfMaskedEdit() { Text = "SfMaskedEdit", Width = 150, Height = 50 };

this.Content = maskededit;

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.jpeg)



### Create the SfMaskedEdit control by using the Expression Blend

The SfMaskedEdit control can also be created and configured by using the ExpressionBlend. The following steps display this.

1. Create a WPF project in the Expression Blend and add the reference to the following assemblies.
   1. Syncfusion.SfInput.WPF
   2. Syncfusion.SfShared.WPF
2. Search for the SfMaskedEdit in the toolbox.



   ![](Getting-Started_images/Getting-Started_img4.png)



3. Now drag and drop the SfMaskedEdit into the designer. It generates the SfMaskedEdit. Then configure the properties of the SfMaskedEdit control by using the properties area.

   ![](Getting-Started_images/Getting-Started_img5.jpeg)



This generates the SfMaskedEdit as follows:

![](Getting-Started_images/Getting-Started_img6.jpeg)



