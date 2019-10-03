---
layout: post
title: Undo, Redo support in syncfusion SfImageEditor WPF.
description: Undo and Redo support.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Undo Redo support

Undo Redo support helps in performing the edited image transition from current state to previous state or from current state to next state.

All the editing operation related to the shapes will be stored hence you can easily go to the previous state or next state. This can be done both via toolbar and also programmatically.

N> Currently, Undo and Redo functionality supports only for shapes and text.

Undo and Redo can perform the following operation.

* Add or delete shapes/text.
* Change positions.
* Fill/Stroke changes.

## Undo

In the left side of the toolbar you can find the Undo and Redo icon. Both the icon will be disabled state by default. This will get enabled only when the changes are in done in the images. 

Undo will clear the last performed change on the image. Hence by continuous Undo you can reach the initial state. (i.e. before changes related to shapes and text were done).

Programmatically, Undo can be performed using the Undo method as in the below snippet.

{% tabs %} 

{% highlight C# %} 

editor.Undo();

{% endhighlight %}

{% endtabs %} 


## Redo

Redo icon will get enabled only when an Undo operation is performed. Redo will bring the changes that is excluded using Undo operation.

Programmatically, Redo can be performed using the Undo method as in the below snippet.

{% tabs %} 

{% highlight C# %} 

editor.Redo();

{% endhighlight %}

{% endtabs %} 
