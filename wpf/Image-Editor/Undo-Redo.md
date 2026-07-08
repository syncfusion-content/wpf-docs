---
layout: post
title: Undo and Redo Support in Syncfusion SfImageEditor WPF
description: Undo and Redo support in Syncfusion Essential Studio WPF ImageEditor (SfImageEditor) control, its elements, and more.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Undo and Redo Support

The undo and redo support helps in transitioning the edited image from its current state to the previous state or from the current state to the next state.

All the editing operations related to the shapes will be stored, hence you can easily go to the previous state or the next state. This can be done using the toolbar or programmatically.

> N Currently, the undo and redo support is available only for shapes and text.

The undo and redo support perform the following operations:

* Add or delete shapes/text
* Change positions
* Fill/Stroke changes

## Undo

On the left side of the toolbar, you can find the undo and redo icons. Both these icons will be in the disabled state by default. These icons will be enabled only when changes are made to the images.

Undo clears the last performed change on the image. By performing undo continuously, you can reach the initial state (i.e., before changes related to shapes and text were done).

Programmatically, undo can be performed using the `Undo` method as demonstrated in the following code snippet.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.Undo();

{% endhighlight %}

{% endtabs %}

## Redo

The redo icon is enabled only when an undo operation is performed. Redo will restore the changes that were excluded by the undo operation.

Programmatically, redo can be performed using the `Redo` method as demonstrated in the following code snippet.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.ImageEditor;

editor.Redo();

{% endhighlight %}

{% endtabs %}
