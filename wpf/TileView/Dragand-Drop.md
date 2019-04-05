---
layout: post
title: Dragand Drop | TileView | wpf | Syncfusion
description: drag–and-drop
platform: wpf
control: TileView Control
documentation: ug
---

# Drag–and-Drop

Drag-and-Drop enables you to drag the TileViewItems in TileViewControl in a normal state. Once the TileViewItem is dragged, the other items in the TileViewControl moves to the corresponding positions in accordance to the dragging item. This can be enabled and disabled by using the [AllowItemRepositioning](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~AllowItemRepositioning.html) property.

## Adding Dragging Items to an Application 

The Dragging items can be added to an application by using either XAML or C# code.

## Adding through XAML

The following code example illustrates how to add the Dragging Items to an application through XAML.




{% highlight xaml %}




<syncfusion:TileViewControl Name="tileViewCntrl" 

                            AllowItemRepositioning="True"/>

{% endhighlight %}



## Adding through C#

The following code example illustrates how to add the Dragging Items to an application through C#.




{% highlight c# %}




tileViewCntrl.AllowItemRepositioning = true;   

{% endhighlight %}

## Events

* [AllowItemRepositioningChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~AllowItemRepositioningChanged_EV.html)


## Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio XX.X.X.XX -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



