---
layout: post
title: Diacritic sensitivity of AutoComplete in Syncfusion SfTextBoxExt.
description: Learn how to enable and disable Diacritic sensitivity in AutoComplete
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity using the `IgnoreDiacritic` property. The following code example demonstrates how to enable the diacritic sensitivity. The items in the suggestion list will be populated by entering any diacritic character of that alphabet.

{% tabs %}

{% highlight xaml %}

<Window x:Class="AutoComplete_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"
        xmlns:local="clr-namespace:AutoComplete_WPF"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Window.Content>
        <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              SuggestionMode="Contains"
                              IgnoreDiacritic="False"
                              HighlightedTextColor="Red"
                              TextHighlightMode="MultipleOccurence"
                              Width="200">
        </editors:SfTextBoxExt>
    </Window.Content>
</Window>


{% endhighlight %}

{% highlight c# %}

using Syncfusion.Windows.Controls.Input;
using System.Collections.Generic;
using System.Windows;
using System.Windows.Media;

namespace AutoComplete_WPF
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
                SuggestionMode = SuggestionMode.Contains,
                TextHighlightMode = OccurenceMode.MultipleOccurence,
                HighlightedTextColor = new SolidColorBrush(Colors.Red),
                IgnoreDiacritic = false
            };

            List<string> list = new List<string>()
            {
                "Hów tó gâin wéight?",
                "Hów tó drâw ân éléphânt?",
                "Whéré cân I buy â câmérâ?",
                "Guidé mé âll thé wây",
                "Hów tó mâké â câké?",
                "Sây, Hélló Wórld!",
                "Hów tó mâké â róbót?",
                "Whât timé nów in Indiâ?"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Diacritic](Auto-Complete_images/Diacritic.png)

