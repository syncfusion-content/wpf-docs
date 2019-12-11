---
layout: post
title: Range | SfRangeSlider | wpf | Syncfusion
description: This section explains how to set the starting range, the end range and the drag range of the Syncfusion WPF SfRangeSlider.
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Range 

The SfRangeSlider control supports to select range of value using two Thumbs.  

## ShowRange  

When ShowRange property is set to true, two Thumbs are placed in the track. One thumb is used to update the start of the range selection and another thumb is used to update the end of the range selection.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="40" RangeEnd="70"/>

{%endhighlight%}

![ShowRange](Range_images/Range_img1.jpeg)



## RangeStart  

Gets or sets the start value of the range start.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="10" ShowRange="True" RangeStart="10" RangeEnd="70"/>

{%endhighlight%}

![RangeStart](Range_images/Range_img2.jpeg)



## RangeEnd 

Gets or sets the end value of the range end.  

{%highlight xaml%}


<editors:SfRangeSlider Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="30" RangeEnd="90"  />

{%endhighlight%}

![RangeEnd](Range_images/Range_img3.jpeg)

## Drag Selected Range

The `AllowRangeDrag` API allows the user to adjust the range in the Range Slider and to drag the range without changing the start and end ranges individually. The default value for `AllowRangeDrag` is false.

{% tabs %}

{% highlight xaml %}

<Window x:Class="SfRangeSliderSample_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfRangeSliderSample_WPF"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <editors:SfRangeSlider Width="400" 
                               RangeStart="0" 
                               RangeEnd="20" 
                               Minimum="0" 
                               Maximum="100"
                               ShowValueLabels="True" 
                               AllowRangeDrag="True" 
                               ShowRange="True" 
                               TickFrequency="20" 
                               HorizontalAlignment="Center" 
                               VerticalAlignment="Center"/>
</Window>
		
{% endhighlight %}  

{% highlight c# %}

using Syncfusion.Windows.Controls.Input;
using System.Windows;

namespace SfRangeSliderSample_WPF
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfRangeSlider rangeSlider = new SfRangeSlider()
            {
                Width = 400,
                RangeStart = 0,
                RangeEnd = 20,
                Minimum = 0,
                Maximum = 100,
                ShowValueLabels = true,
                AllowRangeDrag = true,
                ShowRange = true,
                TickFrequency = 20,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center
            };

            this.Content = rangeSlider;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Drag Range](Range_images/RangeSlider.gif)

