---
layout: post
title: Highlighting Matched Text in WPF Autocomplete control | Syncfusion
description: Learn here all about Highlighting Matched Text support in Syncfusion WPF Autocomplete (SfTextBoxExt) control and more.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Highlighting Matched Text in WPF Autocomplete (SfTextBoxExt)

By using the [TextHighlightMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_TextHighlightMode) property, highlight matching and unmatched characters in a suggestion list to pick an item with more clarity. The default value is None. The matching text can be highlighted in the following two ways:

* First occurrence
* Multiple occurrence
* Unmatched

The text highlight can be indicated by customizing the color of the characters using [HighlightedTextColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextColor) property and style of the characters using [HighlightedTextStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextStyle) property.

N> The [HighlightedTextStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_HighlightedTextStyle) property style target type is [Run](https://docs.microsoft.com/en-us/dotnet/api/system.windows.documents.run?view=net-5.0).

## First occurrence

It highlights the first position of the matching characters in the suggestion list.

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

## Multiple occurrence

It highlights the matching character that presents everywhere in the suggestion list for "Contains" case in SuggestionMode.

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

It highlights unmatched characters in the suggestion list.

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

![Multiple Occurrance](Highlighting_matched_text_images/Unmatched.png)


N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/TextHighlightMode) in GitHub
