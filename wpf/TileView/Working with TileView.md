---
layout: post
title: Working with TileView | TileViewControl | WPF | Syncfusion
description: This section deals with essential features of TileViewControl. 
platform: WPF
control: TileViewControl
documentation: ug
---

# Working with TileView

This section deals with essential features of TileViewControl, which are listed below:

* Row count and column count
* Setting the TileViewItem Size in Normal State
* Setting the Size of TileViewItem in Minimized State


## Row count and column count

The TileViewControl has [RowCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~RowCount.html) and [ColumnCount](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~ColumnCount.html) properties. These can be set to change the number of rows and columns in the TileViewControl, as shown below:


{% tabs %}

{% highlight XAML %}

 <!-- TileViewControl -->

 <syncfusion:TileViewControl x:Name="tile"  RowCount="3" ColumnCount="3">

 <syncfusion:TileViewItem Header="Item1"/>

 <syncfusion:TileViewItem Header="Item2"/>

 <syncfusion:TileViewItem Header="Item3" />

 <syncfusion:TileViewItem Header="Item4"/>
			
 <syncfusion:TileViewItem Header="Item5"/>

 <syncfusion:TileViewItem Header="Item6"/>

 <syncfusion:TileViewItem Header="Item7" />

 <syncfusion:TileViewItem Header="Item8"/>

 <syncfusion:TileViewItem Header="Item9"/>
					
 </syncfusion:TileViewControl>

{% endhighlight  %}

{% highlight C# %}

// Set Row count

tile.RowCount = 3;

// Set Column count

tile.ColumnCount = 3;

{% endhighlight  %}

{% endtabs %}


![TileViewControl has three rows and columns](Working-with-TileView_images/Row-Column-Count_img1.png)


## Setting the TileViewItem Size in Normal State

You can change TileViewItem size in normal state by setting [RowHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~RowHeight.html) and [ColumnWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~ColumnWidth.html) properties.


{% tabs %}

{% highlight XAML %}

 <!-- TileViewControl -->

 <syncfusion:TileViewControl x:Name="tile" RowHeight="100" ColumnWidth="150">

 <syncfusion:TileViewItem Header="Item1"/>

 <syncfusion:TileViewItem Header="Item2"/>

 <syncfusion:TileViewItem Header="Item3" />

 <syncfusion:TileViewItem Header="Item4"/>
			
 </syncfusion:TileViewControl>

{% endhighlight  %}

{% highlight C# %}

 //Set the height 

 tile.RowHeight = new GridLength(100);

 //Set the width
 
 tile.ColumnWidth = new GridLength(150);

{% endhighlight  %}

{% endtabs %}


![TileviewItem size customized in normal state](Working-with-TileView_images/Normal-State_img1.png)


## Setting the Size of TileViewItem in Minimized State

You can change TileViewItem size in minimized state by setting [OnMinimizedHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~OnMinimizedHeight.html) and [OnMinimizedWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~OnMinimizedWidth.html) properties.


{% tabs %}

{% highlight XAML %}

 <syncfusion:TileViewControl x:Name="tile"  RowHeight="200" ColumnWidth="200" MinimizedItemsOrientation="Top" >

 <syncfusion:TileViewItem Header="Item1" Content="Content" OnMinimizedHeight="150" OnMinimizedWidth="300"/>

 <syncfusion:TileViewItem Header="Item2" Content="Content" OnMinimizedHeight="150" OnMinimizedWidth="300"/>

 <syncfusion:TileViewItem Header="Item3" Content="Content" OnMinimizedHeight="150" OnMinimizedWidth="300" />

 <syncfusion:TileViewItem Header="Item4" Content="Content" OnMinimizedHeight="150" OnMinimizedWidth="300"/>

 </syncfusion:TileViewControl>

{% endhighlight  %}

{% highlight C# %}

 TileViewItem tile1 = new TileViewItem();

 //Set height

 tile1.OnMinimizedHeight = new GridLength(150);
 
 //Set width

 tile1.OnMinimizedWidth = new GridLength(300);

{% endhighlight  %}

{% endtabs %}


![TileViewItem size customized in minimized state](Working-with-TileView_images/Minimized-State_img1.png)
