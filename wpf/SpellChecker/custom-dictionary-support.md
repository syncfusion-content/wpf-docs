---
layout: post
title: Custom Dictionary Support for SfSpellChecker control in WPF
description: Custom Dictionary Support for SfSpellChecker control in WPF
platform: WPF
control: SfSpellChecker
documentation: ug
---

# Custom Dictionary

`SfSpellChecker` provides predefined dictionary for English language and also supports to custom dictionary based on Application requirement. `SfSpellChecker` provides suggestions based on custom dictionary.

`CustomDictionaryPath` property is used to passing the file path of the user defined custom dictionary.

## Setting CustomDictionaryPath

Create a `SfSpellChecker` instance and set the `CustomDictionaryPath` as given in the below code.

{% tabs %}

{% highlight C# %}

SfSpellChecker SpellCheck = new SfSpellChecker(); 

SpellCheck.CustomDictionaryPath = "custom.txt";

{% endhighlight %}

{% endtabs %}

