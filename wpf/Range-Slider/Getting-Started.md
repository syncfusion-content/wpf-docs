---
layout: post
title: Getting Started | SfRangeSlider | wpf | Syncfusion
description: getting started 
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Getting Started 

This section describes how to design a `SfRangeSlider` control in a WPF application and overview of its basic functionalities.

## Assembly deployment

 Namespace:  Syncfusion.Windows.Controls.Input

 Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

Dependent assembly: Syncfusion.SfShared.WPF.dll


# Creating simple application with SfRadialSlider

The SfRangeSlider control can be added to an application using Visual Studio.

You can create the WPF application with SfRangeSlider control as follows:

1. [Creating project](#creating-the-project)
2. [Adding control via designer](#adding-control-via-designer)
3. [Adding control manually in code](#adding-control-manually-in-code)

## Creating the project

The steps to create a SfRangeSlider control by using Visual Studio in C# are as follows:

1.	Open Visual Studio.

2.	On the File menu, select New -> Project. This opens the New Project Dialog box.

## Adding control via designer

SfRangeSlider control can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly references will be added automatically:

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

![](GettingStarted_images/img1.png)

{% tabs %}

{% highlight XAML %}

<Window xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"> 

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">     

<editors:SfRangeSlider Width="500" HorizontalAlignment="Center" VerticalAlignment="Center" Minimum="0" Maximum="100"/>

</Grid>

</Window> 

{%endhighlight%}

{% endtabs %}

## Adding control manually in code

The following code sample shows how to create the SfRangeSlider from code-behind.

{%tabs%}

{%highlight C#%}

SfRangeSlider rangeSlider = new SfRangeSlider();

{%endhighlight%}

{%highlight VB%}

Dim rangeSlider As SfRangeSlider = New SfRangeSlider

{%endhighlight%}

{%endtabs%}

![](GettingStarted_images/img2.png)