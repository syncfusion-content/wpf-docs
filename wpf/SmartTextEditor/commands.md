---
layout: post
title: Commands in AI-Powered Text Editor control | Syncfusion®
description: Discover the basic features of Syncfusion<sup>&reg;</sup> WPF AI-Powered Text Editor (SfSmartTextEditor) control.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Commands in WPF AI-Powered Text Editor (SfSmartTextEditor)

The AI-Powered Text Editor provides the `TextChangedCommand` command, is triggered whenever the text in the smart text editor changes.

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