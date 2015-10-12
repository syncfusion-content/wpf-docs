---
layout: post
title: Themes
description: common supports
platform: wpf
control: Themes
documentation: ug
---
## Applying theme globally in the application

By Default SfSkinManager will merge the required resource files from the Theme assembly to the applied control. To apply the theme globally in the application, **ApplyStylesOnApplication** property need to turn **true****.** It will merge all resource file to the Application’s Resource Dictionary.

{% highlight c# %}

SfSkinManager.ApplyStylesOnApplication = true;


{% endhighlight %}

