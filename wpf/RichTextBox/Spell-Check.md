---
title: Spell Check in WPF RichTextBox control | Syncfusion
description: Learn here all about Spell Check support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: spell-check
---
# Spell Check in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv provides support for checking spelling mistakes in the rich text document content. It also supports enabling the following spell checking options.

* Ignore words in UPPERCASE.

* Ignore words that contain numbers.

* Ignore URIs.


The following sample code demonstrates how to enable spell checker in SfRichTextBoxAdv.

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv"  xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf">
    <RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
        <RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true"/>
    </RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
</RichTextBoxAdv:SfRichTextBoxAdv>


{% endhighlight %}
{% highlight c# %}
// Enables spell checker in RichTextBoxAdv.
richTextBoxAdv.SpellChecker.IsEnabled = true;

// Ignores alpha numeric words while spell check.
richTextBoxAdv.SpellChecker.IgnoreAlphaNumericWords = true;

// Ignores upper case words while spell check.
richTextBoxAdv.SpellChecker.IgnoreUppercaseWords = true;

// Ignores URIs while spell check.
richTextBoxAdv.SpellChecker.IgnoreURIs = true;


{% endhighlight %}
{% highlight VB %}
' Enables spell checker in RichTextBoxAdv.
richTextBoxAdv.SpellChecker.IsEnabled = True

' Ignores alpha numeric words while spell check.
richTextBoxAdv.SpellChecker.IgnoreAlphaNumericWords = True

' Ignores upper case words while spell check.
richTextBoxAdv.SpellChecker.IgnoreUppercaseWords = True

' Ignores URIs while spell check.
richTextBoxAdv.SpellChecker.IgnoreURIs = True


{% endhighlight %}

{% endtabs %}

## Adding Custom Dictionaries

The SfRichTextBoxAdv also supports defining custom dictionaries that can be referred while check spelling mistakes. The SfRichTextBoxAdv ignores words that are defined in the referenced custom dictionaries. The SfRichTextBoxAdv supports option for adding misspelled word to dictionary. This option will be enabled only when at least one custom dictionary is defined. The misspelled words will be added to first item in the custom dictionary collection.
The following code example demonstrates how to define custom dictionaries for spell checking.
{% tabs %}
{% highlight xaml %}
<!-- xmlns:System="clr-namespace:System;assembly=mscorlib" -->
<!-- xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" -->

<RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true">
    <RichTextBoxAdv:SpellChecker.CustomDictionaries>
        <System:String>../../Assets/DefaultDictionary.dic</System:String>
        <System:String>../../Assets/CustomDictionary.dic</System:String>
    </RichTextBoxAdv:SpellChecker.CustomDictionaries>
</RichTextBoxAdv:SpellChecker>

{% endhighlight %}

{% endtabs %}

You can download a complete working sample from [GitHub]. (https://github.com/SyncfusionExamples/WPF-RichTextBox-Samples/tree/main/How-to-add-custom-dictionaries-in-richtextbox)


## Multilingual Spell Check Support

The SfRichTextBoxAdv provides support for check spelling mistakes based on multi languages. You can do it so by defining language property for SfRichTextBoxAdv control.
The following code example demonstrates how to enable spell checking based on language.
{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv"  xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" Language="fr">
    <RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
        <RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true"/>
    </RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
</RichTextBoxAdv:SfRichTextBoxAdv>



{% endhighlight %}

{% endtabs %}

## Spelling Pane

The SfRichTextBoxAdv provides built-in spelling pane support for checking spelling mistakes and rectifying error words, similar to the Microsoft Word application.
The following code example demonstrates how to show the spelling pane in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binding Button to UI Command that shows the spelling pane  -->
<Button Content="Show Spelling Pane" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowSpellingPaneCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}
![WPF RichTextBox displays spellcheck option](SpellCheck_images/wpf-richtextbox-spellcheck-option.PNG)

N> In order to enable spell checking functionality based on particular language, language pack for .NET Framework should be installed in the machine.
You can refer to our [WPF RichTextBox](https://www.syncfusion.com/wpf-controls/richtextbox) feature tour page for its groundbreaking feature representations.You can also explore our [WPF RichTextBox example](https://github.com/syncfusion/wpf-demos/tree/master/richtextbox) to knows how to render and configure the editing tools.
