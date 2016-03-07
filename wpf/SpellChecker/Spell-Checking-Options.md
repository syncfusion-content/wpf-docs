---
layout: post
title: Spell Checking Options | SpellChecker | wpf | Syncfusion
description: spell checking options
platform: wpf
control: SpellChecker
documentation: ug
---

# Spell Checking Options

The Spell Checking engine can also be customized to ignore certain text or words from being spell checked. By setting the respective properties, these words will be overlooked and will not indicate them as misspelled words. This option will be effective when there are a number of  email id's and addresses, filenames, html tags, combination of words and numbers, combination of upper and lower case words that are used frequently in the document.

### Properties

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
ExcludeEmailAddress</td><td>
Specifies whether or not to ignore email address during Spell Check. Default value is True.</td></tr>
<tr>
<td>
ExcludeFilenames</td><td>
Specifies whether or not to ignore file names during Spell Check. Default value is True.</td></tr>
<tr>
<td>
ExcludeHtmlTags</td><td>
Specifies whether or not to ignore html tags during Spell Check. Default value is True.</td></tr>
<tr>
<td>
ExcludeInternetAddress</td><td>
Specifies whether or not to ignore internet address during Spell Check. Default value is True.</td></tr>
<tr>
<td>
ExcludeWordsInMixedCase</td><td>
Specifies whether or not to ignore mixed case words during Spell Check.  Default value is False.</td></tr>
<tr>
<td>
ExcludeWordsInUpperCase</td><td>
Specifies whether or not to ignore uppercase words during Spell Check. Default value is True.</td></tr>
<tr>
<td>
ExcludeWordsWithNumbers</td><td>
Specifies whether or not to Spell Check numbers or words with numbers during Spell Check. Default value is True.</td></tr>
</table>


### Setting Spell Checking options  

Create a spell checker instance and set the spell checking options as given below:

{%highlight c# %}

SpellChecker SpellCheck = new SpellChecker();

SpellCheck.ExcludeEmailAddress = true;

SpellCheck.ExcludeFileNames = true;

SpellCheck.ExcludeHtmlTags = true;

SpellCheck.ExcludeInternetAddresses = true;

SpellCheck.ExcludeWordsInMixedCase = true;

SpellCheck.ExcludeWordsInUpperCase = true;

SpellCheck.ExcludeWordsWithNumbers = true;

{%endhighlight%}

### Sample Link

To access the sample link:

1. Open the Syncfusion Dashboard.
2. Select User Interface.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to Tools -> SpellChecker -> SpellCheckerDemo.