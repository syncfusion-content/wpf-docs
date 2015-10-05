---
layout: post
title: Getting Started | SpellChecker | wpf | Syncfusion
description: getting started
platform: wpf
control: SpellChecker
documentation: ug
---

# Getting Started

## Adding Spell Checker to an Application

Spell Checker is a spell checking engine. Using SpellCheck method, you can check spellings for any text. This method will return the suggestions available for the input text as shown in the following code snippet: 

{% highlight c# %}

SpellChecker SpellCheck = new SpellChecker();

SpellCheck. SpellCheck(“pass the input text that needs to be spell checked”);

{% endhighlight %}