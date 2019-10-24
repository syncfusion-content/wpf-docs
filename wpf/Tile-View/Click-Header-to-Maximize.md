---
layout: post
title: Click Header to Maximize | TileView | wpf | Syncfusion
description: click header to maximize
platform: wpf
control: TileView Control
documentation: ug
---

# Click Header to Maximize

The TileViewItem moves to maximized state from Normal or minimized state when you click on the header of the TileViewItem. You can enable or disable this feature by using the [ClickHeaderToMaximized](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~ClickHeaderToMaximize.html) property in the TileViewControl. If you click on the header of the TileViewItem in maximized state, then no action will take place, the TileViewItem’s state will remain same.

## Use Case Scenarios

This feature will be useful when you want to maximize a TileViewItem without clicking the MinMax Button.

## Adding Click Header to Maximize to an Application

[ClickHeaderToMaximize](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~ClickHeaderToMaximize.html) can be added to an application by using either XAML or C# code.

The following code example illustrates how to add the Click Header to Maximize to an application.

{% tabs %}

{% highlight xaml %}

<syncfusion:TileViewControl x:Name="TileView" Height="600" Width="800" 

            ClickHeaderToMaximize ="True" >

      <syncfusion:TileViewItem x:Name="Tile1" Header="TileViewItem 1" />

      <syncfusion:TileViewItem x:Name="Tile2" Header="TileViewItem 2" />

      <syncfusion:TileViewItem x:Name="Tile3" Header="TileViewItem 3" />

      <syncfusion:TileViewItem x:Name="Tile4" Header="TileViewItem 4" /> 

</syncfusion:TileViewControl>
{% endhighlight %}

{% highlight c# %}

      TileViewControl Tile = new TileViewControl();

      Tile.ClickHeaderToMaximize = true;      

{% endhighlight %}

{% endtabs %}

## Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio XX.X.X.XX-> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



