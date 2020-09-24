---
layout: post
title: Appearance of the WPF SfSpellChecker control | Syncfusion
description: Learn about styling, theme support in Syncfusion WPF SfSpellChecker control and more details about the control features.
platform: wpf
control: SfSpellChecker
documentation: ug
---

# Appearance in WPF SfSpellChecker

This section explains different theming options available in [SfSpellChecker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.SfSpellChecker.html) control.

## Theme

You can customize the appearance of the `SfSpellChecker` control by using the [SfSkinManager.SetVisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfSkinmanager.SfSkinmanager.html#Syncfusion_SfSkinManager_SfSkinManager_SetVisualStyle_System_Windows_DependencyObject_Syncfusion_SfSkinManager_VisualStyles_) method. The following are the various built-in visual styles for `SfSpellChecker` control.

* Blend
* Lime
* MaterialDark
* MaterialDarkBlue
* MaterialLight
* MaterialLightBlue
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office2019Black
* Office2019Colorful
* Office365
* Saffron
* VisualStudio2013
* VisualStudio2015

{% tabs %}
{% highlight C# %}

//Namespace for the SfSkinManager.
using Syncfusion.SfSkinManager;

SfSpellChecker sfSpellChecker = new SfSpellChecker();
SfSkinManager.SetVisualStyle(sfSpellChecker, VisualStyles.Office2019Black);

{% endhighlight %}
{% endtabs %}

![SfSpellChecker with Office2019Black visual style](gettingstarted-images/Theme.png)

Here, the `Office2019Black` style is applied to the `SfSpellChecker`.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-SpellChecker-examples/tree/master/Samples/Themes)
