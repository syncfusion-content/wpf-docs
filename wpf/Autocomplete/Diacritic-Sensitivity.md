---
layout: post
title: Diacritic Sensitivity in WPF Autocomplete Control | Syncfusion®
description: Learn about diacritic sensitivity support in the Syncfusion® WPF Autocomplete (SfTextBoxExt) control and more.
platform: WPF
control: SfTextBoxExt
documentation: ug
---

# Diacritic Sensitivity in WPF Autocomplete (SfTextBoxExt)

The control supports multiple keyboard types, allowing it to be populated with items from languages containing letters with diacritics, while searching for them using English characters from an en-US keyboard. The diacritic sensitivity can be enabled or disabled using the [IgnoreDiacritic](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTextBoxExt.html#Syncfusion_Windows_Controls_Input_SfTextBoxExt_IgnoreDiacritic) property. The following code example demonstrates how to enable diacritic sensitivity.

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

> **Note:** View [sample](https://github.com/SyncfusionExamples/wpf-textboxext-examples/tree/master/Samples/Diacritic-sensitivity) on GitHub
