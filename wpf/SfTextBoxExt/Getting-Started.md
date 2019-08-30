---
layout: post
title: Getting Started | SfTextBoxExt | wpf | Syncfusion
description: getting started
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Getting Started

Namespace:  Syncfusion.Windows.Controls.Input

Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll) 

The following code sample shows how to create the TextBoxExt from code-behind and XAML:

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
                                 Width="200" 
                                 Text="Hello! World..."/>

        </Grid>
    </Window.Content>
</Window>

{% endhighlight %}

{% highlight c# %}

SfTextBoxExt textBox = new SfTextBoxExt();

{% endhighlight %}

{% endtabs %}