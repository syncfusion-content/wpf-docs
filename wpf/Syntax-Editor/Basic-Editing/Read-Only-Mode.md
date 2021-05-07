---
layout: post
title: Read Only Mode in WPF Syntax Editor control | Syncfusion
description: Learn about Read Only Mode support in Syncfusion WPF Syntax Editor control and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

## Read Only Mode

Edit WPF can also be used as a static control in order to view only the contents of the file. ReadOnly mode is enabled/disabled by using the `IsReadOnly` property of the EditControl class. The following code is used to set the ReadOnly mode for EditControl.

{% tabs %}

{% highlight XAML %}


<sfedit:EditControl Name="editControl" IsReadOnly="True">

</sfedit:EditControl>



{% endhighlight %}

{% highlight C# %}

editControl.IsReadOnly = true;

{% endhighlight %}

{% endtabs %}