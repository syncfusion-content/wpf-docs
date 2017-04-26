---
layout: post
title: Read Only options of the Edit Control for WPF
description: Read Only options of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

## Read Only Mode

Edit WPF can also be used as a static control in order to view only the contents of the file. ReadOnly mode is enabled/disabled by using the **IsReadOnly** property of the EditControl class. The following code is used to set the **ReadOnly** mode for EditControl.

{% highlight xaml %}


<sfedit:EditControl Name="editControl" IsReadOnly="True">

</sfedit:EditControl>



{% endhighlight %}

{% highlight c# %}

editControl.IsReadOnly = true;

{% endhighlight %}

