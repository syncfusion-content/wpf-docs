---
title: Spell Check
description: spell check
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: spell-check
---
# Spell Check

The SfRichTextBoxAdv provides support for checking spelling mistakes in the rich text document content. It also supports enabling the following spell checking options.
* Ignore words in UPPERCASE.

* Ignore words that contain numbers.

* Ignore URIs.


The following sample code demonstrates how to enable spell checker in SfRichTextBoxAdv.
<table>
<tr>
<td colspan=1 rowspan=1>
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv"  xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf"><br/><RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker><br/><RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true"/><br/></RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker><br/></RichTextBoxAdv:SfRichTextBoxAdv><br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
// Enables spell checker in RichTextBoxAdv.<br/>richTextBoxAdv.SpellChecker.IsEnabled = true;<br/>// Ignores alpha numeric words while spell check.<br/>richTextBoxAdv.SpellChecker.IgnoreAlphaNumericWords = true;<br/>// Ignores upper case words while spell check.<br/>richTextBoxAdv.SpellChecker.IgnoreUppercaseWords = true;<br/>// Ignores URIs while spell check.<br/>richTextBoxAdv.SpellChecker.IgnoreURIs = true;<br/></td></tr>
</table>
## Adding Custom Dictionaries

The SfRichTextBoxAdv also supports defining custom dictionaries that can be referred while check spelling mistakes. The SfRichTextBoxAdv ignores words that are defined in the referenced custom dictionaries. The SfRichTextBoxAdv supports option for adding misspelled word to dictionary. This option will be enabled only when at least one custom dictionary is defined. The misspelled words will be added to first item in the custom dictionary collection.
The following code example demonstrates how to define custom dictionaries for spell checking.
{% tabs %}
{% highlight xml %}
<!-- xmlns:System="clr-namespace:System;assembly=mscorlib" -->
<!-- xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" -->
<RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true">
<RichTextBoxAdv:SpellChecker.CustomDictionaries>
<System:String>../../Assets/DefaultDictionary.dic</System:String>
<System:String>../../Assets/CustomDictionary.dic</System:String>
</RichTextBoxAdv:SpellChecker.CustomDictionaries>
</RichTextBoxAdv:SpellChecker>


{% endhighlight %}

## Multilingual Spell Check Support

The SfRichTextBoxAdv provides support for check spelling mistakes based on multi languages. You can do it so by defining language property for SfRichTextBoxAdv control.
The following code example demonstrates how to enable spell checking based on language.
{% highlight xml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv"  xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" Language="fr">
<RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
<RichTextBoxAdv:SpellChecker IsEnabled="True" IgnoreURIs="true" IgnoreAlphaNumericWords="true" IgnoreUppercaseWords="true"/>
</RichTextBoxAdv:SfRichTextBoxAdv.SpellChecker>
</RichTextBoxAdv:SfRichTextBoxAdv>


{% endhighlight %}

{% endtabs %}
N> In order to enable spell checking functionality based on particular language, language pack for .Net framework should be preinstalled in the machine.
