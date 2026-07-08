---
layout: post
title: Suggestion Mode in AI-Powered Text Editor | Syncfusion®
description: Learn about suggestion mode with Syncfusion® WPF AI-Powered Text Editor (SfSmartTextEditor) control.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Choose how suggestions are displayed

The AI-Powered Text Editor supports two display modes for showing completions as you type: `Inline` and `Popup`.
- `Inline`: Renders the predicted text in place after the caret, matching your text style.
- `Popup`: Shows a compact hint near the caret that you can tap the suggestion to accept it or accept it via a key press.

N> `SuggestionDisplayMode` is an enum defined in the `Syncfusion.UI.Xaml.SmartComponents` namespace. The supported values shown above (`Inline` and `Popup`) reflect the values used in the samples on this page. The full enum, the default value, and any additional values depend on the installed Syncfusion version. Refer to the [SfSmartTextEditor API reference](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SmartComponents.html) for the version-specific list.

N>
- On Windows, the default display mode is **Inline**.
- Suggestions can be applied using the **Tab** or **Right Arrow** keys in both modes.

## Inline suggestion mode
Inline mode displays the suggested text directly within the editor, seamlessly continuing your typing flow. This approach is ideal for desktop environments where uninterrupted input feels natural and efficient.

{% tabs %}
{% highlight xaml tabtitle="XAML" hl_lines="9" %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:smarttexteditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf">

    <smarttexteditor:SfSmartTextEditor
        Placeholder="Start typing..."
        UserRole="Email author responding to inquiries"
        SuggestionDisplayMode="Inline" />
</Window>

{% endhighlight %}
{% highlight c# tabtitle="C#" hl_lines="7" %}

using Syncfusion.UI.Xaml.SmartComponents;

var smarttexteditor = new SfSmartTextEditor
{
    Placeholder = "Start typing...",
    UserRole = "Email author responding to inquiries",
    SuggestionDisplayMode = SuggestionDisplayMode.Inline
};

{% endhighlight %}
{% endtabs %}

![Inline Suggestion in WPF Smart Text Editor.](images/suggestion-display-mode/wpf-smarttexteditor-inline-mode.gif)

## Popup suggestion mode
Popup mode displays the suggested text in a small overlay near the caret, making it easy to review and accept without interrupting your typing. This mode is especially useful on touch based devices where tapping the suggestion feels natural and convenient.

{% tabs %}
{% highlight xaml tabtitle="XAML" hl_lines="9" %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:smarttexteditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf">

    <smarttexteditor:SfSmartTextEditor
        Placeholder="Start typing..."
        UserRole="Email author responding to inquiries"
        SuggestionDisplayMode="Popup" />
</Window>

{% endhighlight %}
{% highlight c# tabtitle="C#" hl_lines="7" %}

using Syncfusion.UI.Xaml.SmartComponents;

var smarttexteditor = new SfSmartTextEditor
{
    Placeholder = "Start typing...",
    UserRole = "Email author responding to inquiries",
    SuggestionDisplayMode = SuggestionDisplayMode.Popup
};

{% endhighlight %}
{% endtabs %}

![Popup Suggestion in WPF Smart Text Editor.](images/suggestion-display-mode/wpf-smarttexteditor-popup-mode.gif)

## Switching the suggestion display mode at runtime

The `SuggestionDisplayMode` property is a regular dependency property, so you can change it at runtime either from code or through data binding. The two examples below show the simplest approach for each.

### Change the mode from code-behind

1. Give the editor an `x:Name` in XAML (for example, `x:Name="smartTextEditor"`).
2. In the code-behind file, set the `SuggestionDisplayMode` property to a different `SuggestionDisplayMode` enum value when your application needs to (for example, in a button click handler, in response to a settings change, or when the user toggles a preference).

{% tabs %}
{% highlight c# tabtitle="C#" hl_lines="6" %}

using Syncfusion.UI.Xaml.SmartComponents;

// Toggle between Inline and Popup suggestion display at runtime.
smartTextEditor.SuggestionDisplayMode =
    smartTextEditor.SuggestionDisplayMode == SuggestionDisplayMode.Inline
        ? SuggestionDisplayMode.Popup
        : SuggestionDisplayMode.Inline;

{% endhighlight %}
{% endtabs %}

### Change the mode through data binding

1. Expose a property of type `SuggestionDisplayMode` on your view model (or other binding source) and raise `PropertyChanged` when its value changes so the editor updates automatically.
2. Bind the `SuggestionDisplayMode` property of `SfSmartTextEditor` to that property.

N> The exact `SuggestionDisplayMode` enum values available for binding depend on the installed Syncfusion version. Refer to the API reference for the version-specific enum.

## Version compatibility

The `SuggestionDisplayMode` property and the `Inline` / `Popup` values are available in the `Syncfusion.SfSmartComponents.WPF` package. The default value, supported enum members, and behavior between versions may differ. Refer to the release notes for your installed version.