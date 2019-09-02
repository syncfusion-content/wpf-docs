---
layout: post
title: Watermark | SfTextBoxExt | wpf | Syncfusion
description: watermark
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Watermark

The control will prompt the user with some information, when it is not in focus and contains an empty string.

## Using the Watermark

Watermark property allows the users to specify some information, when the text is empty. For illustration let us create a simple textbox, where the user is asked to enter names separated by a comma,

{% tabs %}
{% highlight xaml %}

<Window x:Class="AutoCompleteSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:AutoCompleteSample"
        mc:Ignorable="d"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        Title="MainWindow" Height="450" Width="800">
    <Window.Content>
        <Grid>
           <editors:SfTextBoxExt HorizontalAlignment="Center" 
                                 VerticalAlignment="Center" 
                                 Width="400" 
                                 Watermark="Enter names separated by comma (Ex : John, Kate)"/>

        </Grid>
    </Window.Content>
</Window>

{% endhighlight %}
{% highlight c# %}

using Syncfusion.Windows.Controls.Input;
using System.Collections.Generic;
using System.Windows;

namespace AutoCompleteSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                Wateramrk = "Enter names separated by comma (Ex : John, Kate)"
            };

            this.Content = textBoxExt;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![](Watermark_images/Watermark_img1.png)

N> The Watermark property is of the object type so any Framework elements can be hosted as Watermark content. Below example shows how to host an image and text as Watermark content.

{% highlight xaml %}

<Window x:Class="AutoCompleteSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:AutoCompleteSample"
        mc:Ignorable="d"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        Title="MainWindow" Height="450" Width="800">
    <Window.Content>
            <editors:SfTextBoxExt HorizontalAlignment="Center"
                                  VerticalAlignment="Center" 
                                  Width="400">
                <editors:SfTextBoxExt.Watermark>
                        <StackPanel Orientation="Horizontal">
                          <Image Source="Windows 8.png" Stretch="None" Margin="2"/>
                          <TextBlock Text="Search Windows" Opacity="0.5" Margin="5 2"/>
                        </StackPanel>
                </editors:SfTextBoxExt.Watermark>
            </editors:SfTextBoxExt>
    </Window.Content>
</Window>

{% endhighlight %}

![](Watermark_images/Watermark_img2.png)

## Using the Watermark template

Any business object can be bound to the Watermark property and that object can be decorated by applying the WatermarkTemplate property.

{% highlight xaml %}

<Window x:Class="AutoCompleteSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:AutoCompleteSample"
        mc:Ignorable="d"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        Title="MainWindow" Height="450" Width="800">
    <Window.Content>
               <editors:SfTextBoxExt HorizontalAlignment="Center" 
                                     VerticalAlignment="Center"
                                     Width="400"
                                     Watermark="{Binding Person}">
                    <editors:SfTextBoxExt.WatermarkTemplate>
                        <DataTemplate>
                               <TextBlock Text="{Binding PromptText}" Opacity="0.5"/>
                        </DataTemplate>
                    </editors:SfTextBoxExt.WatermarkTemplate>
                </editors:SfTextBoxExt>
    </Window.Content>
</Window>

{% endhighlight %}