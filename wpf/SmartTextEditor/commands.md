---
layout: post
title: Commands in WPF Smart Text Editor | Syncfusion®
description: Learn about commands in the WPF Smart Text Editor control for handling text changes and user interactions.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Commands in WPF Smart Text Editor

The WPF Smart Text Editor provides the `TextChangedCommand`, which is triggered whenever the text changes.

## TextChangedCommand

The `TextChangedCommand` is a built-in command that is triggered whenever the text changes, allowing user to handle text change notifications in the view model.

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
        // Handle the text change here.
    }
}
{% endhighlight %}
{% endtabs %}
