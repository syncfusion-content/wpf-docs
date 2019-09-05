---
layout: post
title: MatchHighlighting of AutoComplete in Syncfusion SfTextBoxExt.
description: Learn how to highlight the matched text in AutoComplete
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Highlighting matched text

You can highlight matching characters in a suggestion list to pick an item with more clarity. The matching text can be highlighted in the following two ways:

* First occurrence
* Multiple occurrence

The text highlight can be indicated with various customizing styles by enabling the following properties:

* HighlightedTextColor: Sets the color of the highlighted text for differentiating the highlighted characters.
* HighlightTextFontAttributes: Sets the FontAttributes of the highlighted text.

## First occurrence

It highlights the first position of the matching characters in the suggestion list.

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
                              SuggestionMode="StartsWith"
                              HighlightedTextColor="Red"
                              TextHighlightMode="FirstOccurence"
                              HighlightedTextFontWeight="Bold"
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
                SuggestionMode = SuggestionMode.StartsWith,
                TextHighlightMode = OccurenceMode.FirstOccurence,
                HighlightedTextColor = new SolidColorBrush(Colors.Red),
                HighlightedTextFontWeight = FontWeights.Bold
            };

            List<string> list = new List<string>()
            {
                 "India",
                 "Uganda",
                 "Ukraine",
                 "Canada",
                 "United Arab Emirates"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}

{% endtabs %}

![First Occurrance](Auto-Complete_images/FirstOccurrance.png)

## Multiple occurrence

It highlights the matching character that presents everywhere in the suggestion list for Contains case in SuggestionMode.

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
                              HighlightedTextColor="Red"
                              HighlightedTextFontWeight="Bold"
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
                HighlightedTextFontWeight = FontWeights.Bold
            };

            List<string> list = new List<string>()
            {
                 "India",
                 "Uganda",
                 "Ukraine",
                 "Canada",
                 "United Arab Emirates"
            };

            textBoxExt.AutoCompleteSource = list;
            this.Content = textBoxExt;
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Multiple Occurrance](Auto-Complete_images/MultipleOccurrance.png)
