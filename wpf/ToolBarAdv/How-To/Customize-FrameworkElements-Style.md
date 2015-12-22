---
layout: post
title: Customize-FrameworkElements-Style
description: customize frameworkelement’s style
platform: wpf
control: ToolBarAdv
documentation: ug
---

### Customize FrameworkElement’s Style

In ToolBarAdv, style for FrameworkElement will be picked from a ResourceDictionary assigned in the _ControlsResourceDictionary_ property.

Following code snippet shows the resource dictionary containing FrameworkElement’s style assigned for ToolBarAdv:



{% highlight xaml %}



<shared:ToolBarAdv ControlsResourceDictionary="ControlsResource.xaml"></shared:ToolBarAdv>
{% endhighlight %}




{% highlight C# %}

ToolBarAdv toolBar = new ToolBarAdv();

            toolBar.ControlsResourceDictionary = new ResourceDictionary()

            {

                Source=new Uri("ControlsResouce.xaml", UriKind.RelativeOrAbsolute)

            }


{% endhighlight %}
                * 



