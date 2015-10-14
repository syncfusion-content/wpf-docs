---
layout: post
title: User Dictionary | SpellChecker | wpf | Syncfusion
description: user dictionary
platform: wpf
control: SpellChecker
documentation: ug
---

# User Dictionary

Spell Checker can also look into the specified user dictionary for spell checking.

### Methods

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
SetUserDictionary</td><td>
SetUserDictionary(string dicName),SetUserDictionary(UserDictionary userDic)</td><td>
SetUserDictionary is an overloaded method. You can set the UserDictionary by passing the file name of the dictionary to this method or you can pass UserDictionary instance to this method</td></tr>
<tr>
<td>
SetIncludeUserDictionaryInSuggestions</td><td>
SetIncludeUserDictionaryInSuggestions(bool include)</td><td>
The UserDictionary will be taken into account only if we pass true to this method. If we pass false as its argument, the SpellChecker will not look into the UserDictionary while checking spellings.</td></tr>
</table>


### Setting User Dictionary  

Create a SpellChecker instance and set the user dictionary as given in the below code.

{% highlight c# %}

SpellChecker SpellCheck = new SpellChecker();

SpellCheck.SetUserDictionary(“D:\custom”);

SpellCheck.SetIncludeUserDiction-aryInSuggestions(true);

{% endhighlight %}

#### Sample Link

To access the sample link:

1. Open the Synfusion Dashboard.
2. Select User Interface.
3. Click the WPF drop-down list and select Explore Samples.
4. Navigate to Tools -> SpellChecker -> SpellCheckerDemo.