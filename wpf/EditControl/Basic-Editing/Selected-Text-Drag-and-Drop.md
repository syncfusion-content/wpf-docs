---
layout: post
title: Deals with how to drag and drop selected text in the Edit control
description: Deals with how to drag and drop selected text in the Edit control
platform: wpf
control: Edit Control
documentation: ug
---

## Selected Text Drag and Drop

It is possible to drag and drop selected text in a paragraph by setting the **AllowDragDrop** property to **True**. Dragging selected text by default will perform a move operation, while dragging using the **Ctrl** key will perform a copy operation.

{% highlight xaml %}

<sfedit:EditControl Name="editControl" AllowDrop="True" EnableOutlining="False"  AllowDragDrop="True">

</sfedit:EditControl>


{% endhighlight %}

{% highlight c# %}

editControl.AllowDragDrop = true;

editControl.AllowDrop = true;

{% endhighlight %}

