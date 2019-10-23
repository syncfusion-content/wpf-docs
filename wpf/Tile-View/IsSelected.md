---
layout: post
title: IsSelected | TileView | wpf | Syncfusion
description: isselected
platform: wpf
control: TileView Control
documentation: ug
---

# IsSelected

[IsSelected](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~IsSelected.html) is a boolean property in the TileViewItem which is used to select a particular TileViewItem. If the [IsSelected](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~IsSelected.html) property of a TileViewItem is set to True, the set TileViewItems opacity is set to 1 and the remaining TileViewItems opacity will be reduced to show the difference.

## Use Case Scenarios

This feature will be very useful when you who want to select a particular TileViewItem.



## Adding IsSelected to an Application 

[IsSelected](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~IsSelected.html) can be added to an application by using either XAML or C# code.

The following code example illustrates how to add the IsSelected to an application.


{% tabs %}

{% highlight xaml %}

<syncfusion:TileViewControl x:Name="TileView" Height="600" Width="800">

      <syncfusion:TileViewItem x:Name="Tile1" Header="TileViewItem 1" />

      <syncfusion:TileViewItem x:Name="Tile2" Header="TileViewItem 2" />

      <syncfusion:TileViewItem x:Name="Tile3" Header="TileViewItem 3" />

      <syncfusion:TileViewItem x:Name="Tile4" Header="TileViewItem 4" 

                               IsSelected="True" /> 

</syncfusion:TileViewControl>

{% endhighlight %}


{% highlight c# %}

      TileViewControl Tile = new TileViewControl();

      TileViewItem item1 = new TileViewItem();

      item1.IsSelected = true;
{% endhighlight %}

{% endtabs %}

## Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 





