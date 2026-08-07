---
layout: post
title: How to detect closing of a DockingManager child in in WPF Button
description: Learn How to detect closing of a DockingManager child in in WPF Button using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to detect closing of a DockingManager child in in WPF Button

DockStateChanged and CloseButtonClick are the two events, which can be used to detect whether the child is closed. DockStateChanged event is raised whenever a child changes its State. CloseButtonClick event is raised only when close button of the Document child is clicked. The following code describes how to handle the closing of a child using DockStateChanged event.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager DockStateChanged="DockingManager_DockStateChanged">

	<Grid/>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

private void DockingManager_DockStateChanged(FrameworkElement sender,DockStateEventArgs e)
{     
   if (e.NewState == DockState.Hidden)     
   {        
   //TODO:your code here to handle the closed state.     
   }
}      

{% endhighlight  %}

{% endtabs %}

