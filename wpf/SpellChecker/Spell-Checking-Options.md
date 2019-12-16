---
layout: post
title: Spell-Checking-Options | SfSpellChecker | wpf | Syncfusion
description: This section describes about various Spell Checking Options available in SpellChecker control and how it can be assigned to the control.
platform: WPF
control: SfSpellChecker
documentation: ug
---

# Spell Check

The Spell Checking engine can also be customized to ignore certain text or words from being spell checked. By setting the respective properties, these words will be overlooked and will not indicate them as misspelled words. This option will be effective when there are a number of email id’s and addresses, HTML tags, combination of words and numbers, combination of upper and lower case words that are used frequently in the document.

## Ignore Spell Check

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
IgnoreEmailAddress<br/><br/></td><td>
Specifies whether or not to ignore email address during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreHtmlTags<br/><br/></td><td>
Specifies whether or not to ignore HTML tags during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreUrl<br/><br/></td><td>
Specifies whether or not to ignore Internet address during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreMixedCaseWords<br/><br/></td><td>
Specifies whether or not to ignore mixed case words during Spell Check.  Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreUpperCaseWords<br/><br/></td><td>
Specifies whether or not to ignore uppercase words during Spell Check. Default value is False.<br/><br/></td></tr>
<tr>
<td>
IgnoreAlphaNumericWords<br/><br/></td><td>
Specifies whether or not to Spell Check numbers or words with numbers during Spell Check. Default value is False.<br/><br/></td></tr>
</table>


## Setting Spell Check Options

Create a spell checker instance and set the spell checking options as given below:

{% tabs %}

{% highlight C# %}

        TextSpellEditor SpellEditor;

        public MainWindow()
        {
            SpellChecker = new SfSpellChecker();
            InitializeComponent();
            SpellEditor = new TextSpellEditor(txtbx);
            Editor = SpellEditor;
            SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
            SpellChecker.IgnoreUrl = true;
            SpellChecker.IgnoreUpperCaseWords = true;
            SpellChecker.IgnoreAlphaNumericWords = true;
            SpellChecker.IgnoreEmailAddress = true;
            SpellChecker.IgnoreMixedCaseWords = true;
            SpellChecker.IgnoreHtmlTags = true;
        }

        public IEditorProperties Editor
        {
            get;
            set;
        }

        public SfSpellChecker SpellChecker
        {
            get;
            set;
        }

{% endhighlight %}

{% endtabs %}


## Getting Suggestions for Error Word

`SfSpellChecker` provides support to get suggestion list by passing the error word in the below methods.

* GetSuggestions
* GetPhoneticWords
* GetAnagrams

{% tabs %}

{% highlight C# %}

        TextSpellEditor SpellEditor;

        public MainWindow()
        {
            SpellChecker = new SfSpellChecker();
            InitializeComponent();
            SpellEditor = new TextSpellEditor(txtbx);
            Editor = SpellEditor;
            SpellChecker.PerformSpellCheckUsingContextMenu(Editor);
        }

        public IEditorProperties Editor
        {
            get;
            set;
        }

        public SfSpellChecker SpellChecker
        {
            get;
            set;
        }

SpellChecker.GetSuggestions("offce");
SpellChecker.GetPhoneticWords("offce");
SpellChecker.GetAnagrams("offce");

{% endhighlight %}

{% endtabs %}



