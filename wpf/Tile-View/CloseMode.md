---
layout: post
title: CloseMode | TileView | wpf | Syncfusion
description: closemode 
platform: wpf
control: TileView Control
documentation: ug
---

# CloseMode 

The [CloseMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseMode.html) is an enum which includes values Hidden and Delete, which resides in the TileViewItem. If you click on the CloseButton when the CloseMode is set to be hidden, then the TileViewItem moves to the Hidden state. If the [CloseMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseMode.html) is set to Delete, then the TileViewItem will be removed from the TileViewControl. 

## Use Case Scenarios

This feature can be used when you want to move the TileViewItems state to Hidden or Delete from the Control.



The [CloseMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseMode.html) feature can be added to an application by using either XAML or C# code.

The following code example illustrates how to add the [CloseMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseMode.html) feature to an application through XAML and C#.


{% tabs %}

{% highlight xaml %}



<syncfusion:TileViewControl x:Name="TileView1" Width="500" Height="400" 

Background="White">

   <syncfusion:TileViewItem CloseMode="Hide" BorderThickness="2" 

          Header="TileViewItem 1" Content="TileViewItem Content 1" 

          CloseButtonVisibility="Visible" Background="LightGray" 

          HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

   <syncfusion:TileViewItem CloseMode="Hide" BorderThickness="2" 

          Header="TileViewItem 2" Content="TileViewItem Content 2" 

          CloseButtonVisibility="Visible" Background="LightGray" 

          HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

   <syncfusion:TileViewItem CloseMode="Hide" BorderThickness="2" 

          Header="TileViewItem 3" Content="TileViewItem Content 3" 

          CloseButtonVisibility="Visible" Background="LightGray" 

          HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

   <syncfusion:TileViewItem CloseMode="Hide" BorderThickness="2" 

          Header="TileViewItem 4" Content="TileViewItem Content 4" 

          CloseButtonVisibility="Visible" Background="LightGray" 

          HeaderBackground="Gray" Margin="2" CornerRadius="3"/>         

</syncfusion:TileViewControl>
{% endhighlight %}





{% highlight c# %}



      TileViewControl Tile = new TileViewControl();

      Tile.Width = 500;

      Tile.Height = 400;

      Tile.Background = new SolidColorBrush(Colors.White);

      for (int i = 1; i <= 4; i++)

      {

          TileViewItem item1 = new TileViewItem();

          item1.Name = "item" + i;

          item1.Header = "TileViewItem " + i;

          item1.Content = "TileViewItem Content " + i;

          item1.Background = new SolidColorBrush(Colors.LightGray);

          item1.BorderThickness = new Thickness(2d);

          item1.CornerRadius = new CornerRadius(2);

          item1.Margin = new Thickness(2d);

          item1.HeaderBackground = new SolidColorBrush(Colors.Gray);

          item1.CloseMode = CloseMode.Hide;

          item1.CloseButtonVisibility = System.Windows.Visibility.Visible;

          Tile.Items.Add(item1);

      }

      this.LayoutRoot.Children.Add(Tile);
{% endhighlight %}

{% endtabs %}

## Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio XX.X.X.XX -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



