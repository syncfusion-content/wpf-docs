---
layout: post
title: Diacritic Sensitivity in WPF Autocomplete control | Syncfusion
description: Learn here all about Diacritic Sensitivity support in Syncfusion WPF Autocomplete (SfTextBoxExt) control and more.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Diacritic Sensitivity in WPF Autocomplete (SfTextBoxExt)

The control does not stick with one type of keyboard, so it can be populated with the items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Enable or disable the diacritic sensitivity using the [IgnoreDiacritic](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_IgnoreDiacritic) property. The following code example demonstrates how to enable the diacritic sensitivity.

{% tabs %}

{% highlight xaml %}

<editors:SfTextBoxExt HorizontalAlignment="Center" 
                      VerticalAlignment="Center" 
                      Height="40"
                      Width="200"
                      AutoCompleteMode="Suggest"
                      SuggestionMode="Contains"
                      IgnoreDiacritic="False"
                      HighlightedTextColor="Red"
                      TextHighlightMode="MultipleOccurrence"
                      SearchItemPath="Item"
                      AutoCompleteSource="{Binding DiacriticCollenction}"/>

{% endhighlight %}
{% highlight c# %}

textBoxExt.IgnoreDiacritic = false;

{% endhighlight %}

{% endtabs %}

![Diacritic](Diacritic_Sensitivity_images/Diacritic.png)

N> View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Diacritic-sensitivity) in GitHub
