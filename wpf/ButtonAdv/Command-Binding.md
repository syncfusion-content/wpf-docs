---
layout: post
title: Command-Binding
description: command binding
platform: wpf
control: ButtonAdv
documentation: ug
---

# Command Binding

The ButtonAdv control supports Commanding. The Command and Command Parameter properties, enables the user to execute any action on clicking the instance.

The Command can be binded as follows:

{% highlight html %}


<sync:ButtonAdv SizeMode="Normal" Command="{Binding CustomCommand}" CommandParameter="CUSTOM"/>

{% endhighlight %}

