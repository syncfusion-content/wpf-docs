---
layout: post
title: Themes
description: common supports
platform: wpf
control: Themes
documentation: ug
---
## Applying theme globally in the application

By Default SfSkinManager merges the required resource files from the Theme assembly to the applied control. To apply the theme globally in the application, set the **ApplyStylesOnApplication** property to **True.** It merges all the resource files to the Application’s Resource Dictionary.

{% highlight c# %}

SfSkinManager.ApplyStylesOnApplication = true;


{% endhighlight %}

