---
layout: post
title: Detect the closing of a DockingManagerchild | DockingManager | wpf | Syncfusion
description: detect the closing of a dockingmanagerchild
platform: wpf
control: DockingManager
 documentation: ug
---

# Detect the closing of a DockingManagerChild

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

