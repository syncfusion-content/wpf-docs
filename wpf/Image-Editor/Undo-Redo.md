---
layout: post
title: Undo Redo in WPF Image Editor control | Syncfusion
description: Learn here all about Undo Redo support in Syncfusion WPF Image Editor (SfImageEditor) control and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Undo Redo in WPF Image Editor (SfImageEditor)

The undo and redo supports help in performing the edited image transition from current state to previous state or from current state to next state.

All the editing operation related to the shapes will be stored, hence you can easily go to the previous state or next state. This can be done using toolbar or programmatically.

N> Currently, the undo and redo support only for shapes and text.

The undo and redo supports perform the following operations:

* Add or delete shapes/text
* Change positions
* Fill/Stroke changes

## Undo

In the left side of the toolbar, you can find the undo and redo icons. Both these icons will be in disabled state by default. These icons will be enabled only when the changes are done in the images. 

Undo clears the last performed change on the image. By performing undo continuously, you can reach the initial state (i.e., before changes related to shapes and text were done).

Programmatically, undo can be performed using the undo method as demonstrated in following code snippet.

{% tabs %} 

{% highlight C# %} 

editor.Undo();

{% endhighlight %}

{% endtabs %} 

## Redo

The redo icon is enabled only when an undo operation is performed. Redo will bring the changes excluded using the undo operation.

Programmatically, redo can be performed using the undo method as demonstrated in the following code snippet.

{% tabs %} 

{% highlight C# %} 

editor.Redo();

{% endhighlight %}

{% endtabs %} 
