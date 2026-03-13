---
layout: post
title: Customization in AI-Powered Text Editor control | Syncfusion®
description: Discover the basic features of Syncfusion<sup>&reg;</sup> WPF AI-Powered Text Editor (SfSmartTextEditor) control.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Customization in WPF AI-Powered Text Editor (SfSmartTextEditor)
This section explains how to change the AI-Powered Text Editor’s appearance and suggestion behavior. You can set text styles, placeholder options, and customize how suggestions are shown.

## Text customization
Set or bind the smart text editor’s text using the `Text` property. You can use this to preloaded content or bind it to a field in your view model for data binding.

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
    xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
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

![Placeholder in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-placeholdercolor.gif)

## Suggestion text color

Customize the color of the suggestion text using the `SuggestionInlineStyle` property to match your theme and improves readability.

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
Change the background color of the suggestion popup using the `SuggestionPopupStyle` property in Popup mode to align with your app's design.

{% tabs %}
{% highlight xaml tabtitle="XAML" %}

<smartTextEditor:SfSmartTextEditor SuggestionDisplayMode="Popup">
    <smartTextEditor:SfSmartTextEditor.SuggestionPopupStyle>
        <Style TargetType="smartTextEditor:SuggestionPopup">
            <Setter Property="Foreground" Value="White" />
            <Setter Property="Background" Value="#0078D4" />
            <Setter Property="FontSize" Value="16"/>
        </Style>
    </smartTextEditor:SfSmartTextEditor.SuggestionPopupStyle>
</smartTextEditor:SfSmartTextEditor>

{% endhighlight %}
{% endtabs %}

![Customization in WPF Smart Text Editor.](images/customization/wpf-smarttexteditor-customization.gif)

## Maximum input length
Set a limit on the number of characters the user can enter in the smart text editor using the `MaxLength` property.

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