---
layout: post
title: Highlighting Matched Text in WPF Autocomplete Control | Syncfusion®
description: Learn about highlighting matched text support in the Syncfusion® WPF Autocomplete (SfTextBoxExt) control and more.
platform: WPF
control: SfTextBoxExt
documentation: ug
---

# Highlighting Matched Text in WPF Autocomplete (SfTextBoxExt)

The [TextHighlightMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_TextHighlightMode) property allows highlighting of matching and unmatched characters in a suggestion list for greater clarity. The default value is None. Text can be highlighted in the following ways:

- First occurrence
- Multiple occurrences
- Unmatched characters
Text highlights can be customized by adjusting the color using the [HighlightedTextColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextColor) property and the style using the [HighlightedTextStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextStyle) property.

> **Note:** The [HighlightedTextStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextStyle) property style target type is [Run](https://docs.microsoft.com/en-us/dotnet/api/system.windows.documents.run?view=net-5.0).

## First Occurrence

Highlights the first position of the matching characters in the suggestion list.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      HighlightedTextColor="Red"
                      TextHighlightMode="FirstOccurrence"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.TextHighlightMode = OccurrenceMode.FirstOccurrence;

{% endhighlight %}

{% endtabs %}

![First Occurrance](Highlighting_matched_text_images/FirstOccurrance.png)

## Multiple Occurrences

Highlights matching characters that are present everywhere in the suggestion list for the "Contains" case in SuggestionMode.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Width="300"
                      Height="40"
                      SearchItemPath="Name"
                      AutoCompleteMode="Suggest"
                      SuggestionMode="Contains"
                      HighlightedTextColor="Red"
                      TextHighlightMode="MultipleOccurrence"
                      AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.TextHighlightMode = OccurrenceMode.MultipleOccurrence;

{% endhighlight %}

{% endtabs %}

![Multiple Occurrance](Highlighting_matched_text_images/MultipleOccurrance.png)


## Unmatched

Highlights unmatched characters in the suggestion list.

{% tabs %}

{% highlight xaml %}

    <Window.Resources>
        <Style x:Key="highlightedTextStyle" TargetType="Run">
            <Setter Property="FontWeight" Value="Bold" />
        </Style>
    </Window.Resources>

    <editors:SfTextBoxExt
            Width="300"
            Height="40"
            HorizontalAlignment="Center"
            VerticalAlignment="Center"
            AutoCompleteMode="Suggest"
            AutoCompleteSource="{Binding Employees}"
            HighlightedTextColor="Red"
            HighlightedTextStyle="{StaticResource highlightedTextStyle}"
            SearchItemPath="Name"
            SuggestionMode="StartsWith"
            TextHighlightMode="Unmatched" />

{% endhighlight %}
{% highlight c# %}

textBoxExt.TextHighlightMode = OccurrenceMode.Unmatched;

{% endhighlight %}

{% endtabs %}

![Unmatched](Highlighting_matched_text_images/Unmatched.png)

> **Note:** View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples) on GitHub
