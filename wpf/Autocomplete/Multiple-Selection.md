---
layout: post
title: Token support in AutoComplete | SfTextBoxExt | wpf | Syncfusion
description: This section provides details about how to enable multi selection in AutoComplete (SfTextBoxExt).
platform: WPF
control: SfTextBoxExt
documentation: ug
---

## Multiple Selection in Xamarin SfAutoComplete
Select multiple items from a suggestion list. There are two ways to perform multi selection in autocomplete.

* Token Representation

*  Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight xaml %}

<Window x:Class="Demo_Sample.Token"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Demo_Sample"
        mc:Ignorable="d"
        Title="Token" Height="450" Width="800">
    <StackPanel VerticalAlignment="Center">
            <TextBlock Text="None:"/>
            <editors:SfTextBoxExt HorizontalAlignment="Left" 
                                  x:Name="autoComplete1" 
                                  MultiSelectMode="Token"
                                  TokensWrapMode="None"
                                  AutoCompleteMode="Suggest"
                                  VerticalAlignment="Center"
                                  Height="40" Width="200"/>

            <TextBlock Text="Wrap:"/>
            <editors:SfTextBoxExt HorizontalAlignment="Left" 
                                  x:Name="autoComplete2" 
                                  MultiSelectMode="Token"
                                  TokensWrapMode="Wrap"
                                  AutoCompleteMode="Suggest"
                                  VerticalAlignment="Center"
                                  Height="40" Width="200"/>
    </StackPanel>
</Window>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.Windows.Controls.Input;
using System.Collections.Generic;
using System.Windows;

namespace Demo_Sample
{
    /// <summary>
    /// Interaction logic for Token.xaml
    /// </summary>
    public partial class Token : Window
    {
        public Token()
        {
            InitializeComponent();
            List<string> list = new List<string>()
            {
                    "Lucas",
                    "James",
                    "Jacob",
                    "Alan",
                    "Alex",
            };

            autoComplete1.AutoCompleteSource = list;
            autoComplete2.AutoCompleteSource = list;
        }
    }
}

![Token Representation](Auto-Complete_images/Token.png)
