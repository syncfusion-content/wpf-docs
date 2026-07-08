---
layout: post
title: Customization in AI-Powered Text Editor control | Syncfusion®
description: Learn here all about how to customize behavior and features of Syncfusion® WPF AI-Powered Text Editor (SfSmartTextEditor) control and more.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Customization in WPF AI-Powered Text Editor (SfSmartTextEditor)
This section explains how to change the AI-Powered Text Editor’s appearance and suggestion behavior. You can set text styles, placeholder options, and customize how suggestions are shown.

## Text customization
Set or bind the WPF Smart Text Editor’s text using the `Text` property. You can use this to set preloaded content or bind it to a field in your view model for data binding.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<smarttexteditor:SfSmartTextEditor Text="Thank you for contacting us." />

{% endhighlight %}
{% highlight c# tabtitle="C#" %}

var smarttexteditor = new SfSmartTextEditor
{
    Text = "Thank you for contacting us."
};

{% endhighlight %}
{% endtabs %}

## Text style customization

You can change the text style and font using the `Style` property to make the editor look the way you want.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:smarttexteditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf">

    <smarttexteditor:SfSmartTextEditor>
        <smarttexteditor:SfSmartTextEditor.Style>
            <Style TargetType="{x:Type smarttexteditor:SfSmartTextEditor}">
                <Setter Property="FontSize" Value="16"/>
                <Setter Property="Foreground" Value="Blue"/>
            </Style>
        </smarttexteditor:SfSmartTextEditor.Style>
    </smarttexteditor:SfSmartTextEditor>
</Window>

{% endhighlight %}
{% endtabs %}

![Text Style in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-textcolor.gif)

## Placeholder text and color customization

Add a helpful placeholder to guide users and use `PlaceholderStyle` to make the placeholder look the way you want.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<smartTextEditor:SfSmartTextEditor x:Name="smartTextEditor" 
                                   Placeholder="Write your message...">
    <smartTextEditor:SfSmartTextEditor.PlaceholderStyle>
        <Style TargetType="{x:Type ContentControl}">
            <Setter Property="FontSize" Value="16"/>
            <Setter Property="Foreground" Value="#7E57C2"/>
        </Style>
    </smartTextEditor:SfSmartTextEditor.PlaceholderStyle>
</smartTextEditor:SfSmartTextEditor>

{% endhighlight %}
{% endtabs %}

![Placeholder in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-placeholdercolor.gif)

## Suggestion text color

Customize the color of the suggestion text using the `SuggestionInlineStyle` property to match your theme and improve readability.

N> The `SuggestionInlineStyle` property accepts a `Style` whose `TargetType` is the suggestion text element (commonly `TextBlock`). The settable properties depend on the target element. Common setters include `FontSize`, `FontFamily`, `FontWeight`, `Foreground`, and `Background`. The full list of supported style setters depends on the installed Syncfusion version; refer to the API reference for the complete contract.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<smartTextEditor:SfSmartTextEditor>
    <smartTextEditor:SfSmartTextEditor.SuggestionInlineStyle>
        <Style TargetType="{x:Type TextBlock}">
            <Setter Property="FontSize" Value="16"/>
            <Setter Property="Foreground" Value="SkyBlue"/>
        </Style>
    </smartTextEditor:SfSmartTextEditor.SuggestionInlineStyle>
</smartTextEditor:SfSmartTextEditor>

{% endhighlight %}
{% endtabs %}

![Suggestion Text Color in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-inline-textcolor.gif)

## Suggestion popup background
Change the background color of the suggestion popup using the `SuggestionPopupStyle` property in Popup mode. This helps the suggestion align with your app's design.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:smartTextEditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf">
    <smartTextEditor:SfSmartTextEditor SuggestionDisplayMode="Popup">
        <smartTextEditor:SfSmartTextEditor.SuggestionPopupStyle>
            <Style TargetType="smartTextEditor:SuggestionPopup">
                <Setter Property="Foreground" Value="White" />
                <Setter Property="Background" Value="#0078D4" />
                <Setter Property="FontSize" Value="16"/>
            </Style>
        </smartTextEditor:SfSmartTextEditor.SuggestionPopupStyle>
    </smartTextEditor:SfSmartTextEditor>
</Window>

{% endhighlight %}
{% endtabs %}

![Customization in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-customization.gif)

## Maximum input length
Set a limit on the number of characters the user can enter in the WPF Smart Text Editor using the `MaxLength` property.

N> The default value, the behavior when the limit is reached (for example, prevents further input versus silently truncates), and the minimum allowed value of `MaxLength` depend on the installed Syncfusion version. Refer to the API reference for the exact contract, and choose a positive integer appropriate for your scenario.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<smarttexteditor:SfSmartTextEditor
    MaxLength="500" />

{% endhighlight %}
{% highlight c# tabtitle="C#" %}

var smarttexteditor = new SfSmartTextEditor
{
    MaxLength = 500
};

{% endhighlight %}
{% endtabs %}

## Version compatibility

The properties documented on this page (`Text`, `Style`, `Placeholder`, `PlaceholderStyle`, `SuggestionInlineStyle`, `SuggestionPopupStyle`, `SuggestionDisplayMode`, `MaxLength`, and related members) are available in the `Syncfusion.SfSmartComponents.WPF` package. The exact property names, types, and supported values may differ between Syncfusion versions. Refer to the release notes for your installed version.