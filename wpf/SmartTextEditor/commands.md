---
layout: post
title: Commands in AI-Powered Text Editor control | Syncfusion®
description: Learn here all about commands support in Syncfusion® WPF AI-Powered Text Editor (SfSmartTextEditor) control and more.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Commands in WPF AI-Powered Text Editor (SfSmartTextEditor)

The AI-Powered Text Editor provides the `TextChangedCommand`, which is triggered whenever the text in the smart text editor changes.

## Prerequisites

Before wiring up commands, make sure the control is added to your project as described in [Getting started with WPF Smart Text Editor](https://help.syncfusion.com/wpf/smarttexteditor/getting-started). The examples below assume the `Syncfusion.UI.Xaml.SmartComponents` namespace and a simple `RelayCommand` implementation (such as the one shipped with `CommunityToolkit.Mvvm` or `Prism.Core`).

### TextChangedCommand

The `SfSmartTextEditor` includes a built-in property called `TextChangedCommand`, which is triggered whenever the text in the smart text editor changes. This event can be invoked through the `TextChangedCommand`.

{% tabs %}
{% highlight xaml tabtitle="MainPage.xaml" hl_lines="2" %}

<smarttexteditor:SfSmartTextEditor x:Name="smarttexteditor"
                                   TextChangedCommand="TextChangedCommand">
    <Window.DataContext>
        <local:SmartTextEditorViewModel/>
    </Window.DataContext>
</smarttexteditor:SfSmartTextEditor>

{% endhighlight %}
{% highlight c# tabtitle="MainPage.xaml.cs" hl_lines="3,6,8" %}

public class SmartTextEditorViewModel
{
    public ICommand TextChangedCommand { get; set; }
    public SmartTextEditorViewModel()
    {
        TextChangedCommand = new Command(TextChangedCommand);
    }
    private void TextChangedCommand()
    {
        // To do your requirement here.
    }
}

{% endhighlight %}
{% endtabs %}
## See Also

* [Getting started with WPF Smart Text Editor](https://help.syncfusion.com/wpf/smarttexteditor/getting-started): Add the control to your application and configure AI services.
* [Customization in WPF Smart Text Editor](https://help.syncfusion.com/wpf/smarttexteditor/customization): Customize the text, placeholder, suggestion styles, and input limits.
* [Suggestion display mode](https://help.syncfusion.com/wpf/smarttexteditor/suggestion-display-mode): Switch between inline and popup suggestion modes.