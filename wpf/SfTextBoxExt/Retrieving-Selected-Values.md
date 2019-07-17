---
layout: post
title: Retrieving selected values of Auto Complete | SfTextBoxExt | wpf | Syncfusion
description: auto complete
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Handling Selected values

AutoComplete provides a way to handle the selected item using the `SelectedItem` property.

## SelectedItem

The `SelectedItem` property is used to select the particular item from the suggestion list. You can either get or set the SelectedItem.

### How to set the SelectedItem

The following code snippet demonstrates the way to set `SelectedItem`.

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
            <editors:SfTextBoxExt x:Name="textBoxExt" 
                                  HorizontalAlignment="Center" 
                                  VerticalAlignment="Center" 
                                  AutoCompleteMode="Suggest"
                                  SelectedItem="India"
                                  Width="200">
            </editors:SfTextBoxExt>
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
                SelectedItem = "India"
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

### Retrieving Selected items

AutoComplete provides a way to get the selected item using `SelectionChanged` event.

The following code example demonstrates the way to retrieve SelectedItem.

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
            <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              ShowSuggestionsOnFocus="True"
                              SelectedItemChanged="TextBoxExt_SelectedItemChanged"
                              Width="200">
            </editors:SfTextBoxExt>
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
        string selectedItem;
        public MainWindow()
        {
            InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                ShowSuggestionsOnFocus = true
            };

            textBoxExt.SelectedItemChanged += TextBoxExt_SelectedItemChanged;

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

        private void TextBoxExt_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
        {
            if ((d as SfTextBoxExt).SelectedItem != null)
            {
                selectedItem = ((d as SfTextBoxExt).SelectedItem).ToString();
            }

            MessageBoxResult messageBoxResult = MessageBox.Show(selectedItem, "SelectedItem");
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Retrieving Selected value

AutoComplete provides a way to get the selected values using SuggestionIndex property.

### Retrieving the Index of Selected Item

When an item is selected from suggestion list, its index can be retrieved using `SuggestionIndex` property. 

SuggestionIndex property holds the index of selected item in suggestion list. 

The following code example demonstrates the way to retrieve SuggestionIndex.

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
            <editors:SfTextBoxExt x:Name="textBoxExt" 
                              HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              AutoCompleteMode="Suggest"
                              ShowSuggestionsOnFocus="True"
                              SelectedItemChanged="TextBoxExt_SelectedItemChanged"
                              Width="200">
            </editors:SfTextBoxExt>
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
        string suggestionIndex;
        public MainWindow()
        {
            InitializeComponent();
            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                AutoCompleteMode = AutoCompleteMode.Suggest,
                ShowSuggestionsOnFocus = true
            };

            textBoxExt.SelectedItemChanged += TextBoxExt_SelectedItemChanged;

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

        private void TextBoxExt_SelectedItemChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
        {
            suggestionIndex = ((d as SfTextBoxExt).SuggestionIndex).ToString();
            MessageBoxResult messageBoxResult = MessageBox.Show(suggestionIndex, "SuggestionIndex");
        }
    }
}

{% endhighlight %}

{% endtabs %}

