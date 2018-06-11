---
layout: post
title: Deals with how to drag and drop selected text in the Edit control
description: Deals with how to drag and drop selected text in the Edit control
platform: wpf
control: Syntax Editor
documentation: ug
---

## Selected Text Drag and Drop

It is possible to drag and drop selected text in a paragraph by setting the `AllowDragDrop` property to `true`. Dragging selected text by default will perform a move operation, while dragging using the <kbd>Ctrl</kbd> key will perform a copy operation.

{% tabs %}

{% highlight XAML %}

<sfedit:EditControl Name="editControl" AllowDrop="True" EnableOutlining="False"  AllowDragDrop="True">

</sfedit:EditControl>


{% endhighlight %}

{% highlight C# %}

editControl.AllowDragDrop = true;

editControl.AllowDrop = true;

{% endhighlight %}

{% endtabs %}