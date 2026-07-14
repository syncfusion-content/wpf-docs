---
layout: post
title: Commands in AI-Powered Text Editor control | Syncfusion®
description: Learn here all about commands support in Syncfusion® WPF AI-Powered Text Editor (SfSmartTextEditor) control and more.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# TextChangedCommand in WPF Smart Text Editor (SfSmartTextEditor)

The WPF Smart Text Editor provides the `TextChangedCommand` command, which is triggered whenever the text in the editor changes. This page documents the `TextChangedCommand` and the set of supported commands; refer to the [SfSmartTextEditor API reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SmartComponents.html) for the complete and version-specific list.

### TextChangedCommand

The `SfSmartTextEditor` includes a built-in command called `TextChangedCommand`, which is triggered whenever the text in the editor changes. You can invoke this command through the `TextChangedCommand` property.

N> The exact parameter passed to the command's `Execute` and `CanExecute` methods (for example, the new text, the old text, or a `TextChangedEventArgs`-like object) depends on the installed Syncfusion version. Refer to the `SfSmartTextEditor` API reference for the precise `ICommand` contract.

## Supported commands

The following command is documented on this page:

- `TextChangedCommand` — Raised whenever the text in the editor changes.

N> The set of commands supported by the control, including the parameter types and any additional commands such as suggestion-accepted events, depends on the installed Syncfusion version. Refer to the [SfSmartTextEditor API reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SmartComponents.html) for the complete and version-specific list.

## Version compatibility

The command infrastructure described in this page is available in the `Syncfusion.SfSmartComponents.WPF` package. The specific command names, parameter types, and available members may differ between Syncfusion versions. Refer to the release notes for your installed version.

## Setting up the project to use `TextChangedCommand`

Before you wire up `TextChangedCommand` in your view, complete the following steps:

1. Add a reference to the `Syncfusion.SfSmartComponents.WPF` assembly in your WPF project (the same NuGet package installed in the Getting Started walkthrough).
2. In your XAML page, declare the `Syncfusion.UI.Xaml.SmartComponents` namespace.so the `SfSmartTextEditor` element and its `TextChangedCommand` property resolve.
3. If you bind `TextChangedCommand` to a property on a view model or code-behind class, make sure the binding source (the `DataContext`) exposes a property of type `System.Windows.Input.ICommand` named `TextChangedCommand` (or matching the binding path you use in XAML). Add the `using System.Windows.Input;` directive in the C# file that defines the command property.
4. If you are using a third-party `ICommand` implementation such as `RelayCommand` or `DelegateCommand`, install the corresponding NuGet package (for example, `CommunityToolkit.Mvvm`) and add the required `using` directive for that namespace. The `Command` type referenced in the sample below is a placeholder — substitute it with the `ICommand` implementation available in your project.

{% tabs %}
{% highlight xaml tabtitle="MainPage.xaml" hl_lines="8" %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:smarttexteditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf"
        xmlns:local="clr-namespace:WpfApplication1">
    <Window.DataContext>
        <local:MainWindow/>
    </Window.DataContext>
    <Grid>
        <smarttexteditor:SfSmartTextEditor x:Name="smartTextEditor"
                                           TextChangedCommand="{Binding TextChangedCommand}"/>
    </Grid>
</Window>

{% endhighlight %}
{% highlight c# tabtitle="MainPage.xaml.cs" %}

using System.Windows;
using System.Windows.Input;
using Syncfusion.UI.Xaml.SmartComponents;

namespace WpfApplication1
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            // Use a concrete ICommand implementation such as RelayCommand.
            // Substitute "RelayCommand" with the ICommand implementation available in your project
            // (for example, CommunityToolkit.Mvvm's RelayCommand, Prism's DelegateCommand, or your own).
            TextChangedCommand = new RelayCommand(OnTextChanged);
        }

        public ICommand TextChangedCommand { get; set; }

        private void OnTextChanged(object parameter)
        {
            // To do your requirement here.
        }
    }
}

{% endhighlight %}
{% endtabs %}