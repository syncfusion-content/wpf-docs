---
layout: post
title: MatchHighlighting of AutoComplete in Syncfusion SfTextBoxExt.
description: Learn how to highlight the text matched at the first position of the text or anywhere in the AutoComplete suggestion list.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Highlighting matched text

Highlight matching characters in a suggestion list to pick an item with more clarity using the [TextHighlightMode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~TextHighlightMode.html) property. The default value is None. The matching text can be highlighted in the following two ways:

* First occurrence
* Multiple occurrence

The text highlight can be indicated by customizing the color of the characters using [HighlightedTextColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~HighlightedTextColor.html) property.

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

{% endtabs %}

![Multiple Occurrance](Highlighting_matched_text_images/MultipleOccurrance.png)


N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/TextHighlightMode) in GitHub
