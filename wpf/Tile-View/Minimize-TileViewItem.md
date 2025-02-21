---
layout: post
title: Minimize TileViewItem in WPF Tile View control | Syncfusion®
description: Learn about Minimize TileViewItem support in Syncfusion® Essential Studio® WPF Tile View control, its elements and more.
platform: WPF
control: TileViewControl
documentation: ug
---

# Minimize TileViewItem in WPF Tile View

You can minimize the [TileViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewItem.html) and change its appearance in the [TileViewControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html).

## Minimize the TileViewItem

You can minimize the maximized `TileViewItem` by clicking on the minimize button.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl" >
    <syncfusion:TileViewItem Header="Item 1" />
    <syncfusion:TileViewItem Header="Item 2" />
    <syncfusion:TileViewItem Header="Item 3" />
    <syncfusion:TileViewItem Header="Item 4" />
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 4" });

{% endhighlight %}
{% endtabs %}

![TileViewItem is minimizing](Minimize_images/Minimize.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/MinMax-TileItem)

## Direction for minimized items 

If you want to change direction of placing the minimized items, use the [MinimizedItemsOrientation](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html#Syncfusion_Windows_Shared_TileViewControl_MinimizedItemsOrientation) property. The default value of `MinimizedItemsOrientation` property is `Right`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl MinimizedItemsOrientation="Bottom"
                            Name="tileViewControl" >
    <syncfusion:TileViewItem Header="Item 1" />
    <syncfusion:TileViewItem Header="Item 2" />
    <syncfusion:TileViewItem Header="Item 3" />
    <syncfusion:TileViewItem Header="Item 4" />
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

tileViewControl.MinimizedItemsOrientation = MinimizedItemsOrientation.Bottom;

{% endhighlight %}
{% endtabs %}

![Minimized TileViewItem direction is changed as bottom](Minimize_images/MinimizedItemsOrientation.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/MinMax-TileItem)

## Allocate size for minimized TileViewItem

If you want to allocate a certain percentage of the total size to the minimized items, use the [MinimizedItemsPercentage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html#Syncfusion_Windows_Shared_TileViewControl_MinimizedItemsPercentage) property. The default value of `MinimizedItemsPercentage` property is `20`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl MinimizedItemsPercentage="50"
                            Name="tileViewControl" >
    <syncfusion:TileViewItem Header="Item 1" />
    <syncfusion:TileViewItem Header="Item 2" />
    <syncfusion:TileViewItem Header="Item 3" />
    <syncfusion:TileViewItem Header="Item 4" />
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

tileViewControl.MinimizedItemsPercentage = 50;

{% endhighlight %}
{% endtabs %}

![Allocated certain percentage of the total size to the minimized items](Minimize_images/MinimizedItemsPercentage.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/MinMax-TileItem)

## Change minimized TileViewItem content

By default, `TileViewItem.Content` property values displayed as `TileViewItem` content on minimized state. If you want to change the content of the `TileViewItem` on minimized state, use the [MinimizedItemContent](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewItem.html#Syncfusion_Windows_Shared_TileViewItem_MinimizedItemContent) property. The default value of `MinimizedItemContent` property is `null`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl  Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item1" Content="Content1"
                             MinimizedItemContent="Min Content1" />
    <syncfusion:TileViewItem Header="Item2" Content="Content2"
                             MinimizedItemContent="Min Content2" />
    <syncfusion:TileViewItem Header="Item3" Content="Content3"
                             MinimizedItemContent="Min Content3" />
    <syncfusion:TileViewItem Header="Item4" Content="Content4"
                             MinimizedItemContent="Min Content4" />
</syncfusion:TileViewControl>


{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1", 
    Content = "Content1", MinimizedItemContent = "Min Content1" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2",
    Content = "Content2", MinimizedItemContent = "Min Content2" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3",
    Content = "Content3", MinimizedItemContent = "Min Content3" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 4",
    Content = "Content4", MinimizedItemContent = "Min Content4" });

{% endhighlight %}
{% endtabs %}

![Minimized TileViewItem content changed](Minimize_images/MinimizedItemContent.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/MinMax-TileItem)

## Custom UI of minimized TileViewItem content

You can customize the appearance of minimized `TileViewItem` content by using the [MinimizedItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html#Syncfusion_Windows_Shared_TileViewControl_MinimizedItemTemplate) property. The `DataContext` of the `MinimizedItemTemplate` property is `TileViewItem.MinimizedItemContent`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item1" Content="Content1"
                             MinimizedItemContent="Min Content1" />
    <syncfusion:TileViewItem Header="Item2" Content="Content2"
                             MinimizedItemContent="Min Content2" />
    <syncfusion:TileViewItem Header="Item3" Content="Content3"
                             MinimizedItemContent="Min Content3" />
    <syncfusion:TileViewItem Header="Item4" Content="Content4"
                             MinimizedItemContent="Min Content4" />
    <syncfusion:TileViewControl.MinimizedItemTemplate>
        <DataTemplate x:Name="MinTemplate">
            <Grid>
                <TextBlock HorizontalAlignment="Center"
                           Text="{Binding}" 
                           FontFamily="Verdana"
                           Foreground="Red"/>
            </Grid>
        </DataTemplate>
    </syncfusion:TileViewControl.MinimizedItemTemplate>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

![Minimized TileViewItem content UI changed](Minimize_images/MinimizedItemTemplate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/CustomUI-MinMaxTileItem)

## Change minimized TileViewItem header

If you want to change the header of the `TileViewItem` on minimized state, use the [MinimizedHeader](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewItem.html#Syncfusion_Windows_Shared_TileViewItem_MinimizedHeader) property. The default value of `MinimizedHeader` property is `null`.

N> Please refer [Minimized TileViewItem header](https://help.syncfusion.com/wpf/tile-view/tileviewitem-header#change-minimized-and-maximized-header) topic to know more details about minimized `TileViewItem` header and its customization available in the `TileViewControl`.

## Minimized state changed notification

The `TileViewControl` notifies that the minimized state changed in the `TileViewItem` by using [Minimized](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html) event. You can get the minimized items by using the [Source](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewEventArgs.html#Syncfusion_Windows_Shared_TileViewEventArgs_Source) property. You can also use the [OldState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewEventArgs.html#Syncfusion_Windows_Shared_TileViewEventArgs_OldState) and [NewState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewEventArgs.html#Syncfusion_Windows_Shared_TileViewEventArgs_NewState) properties to get the old and new state of `TileViewItem`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Minimized="TileViewControl_Minimized"
                            Name="tileViewControl" />

{% endhighlight %}
{% highlight C# %}

 tileViewControl.Minimized += TileViewControl_Minimized;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void TileViewControl_Minimized(object sender, TileViewEventArgs args) {
    var minimizedItem = args.Source;
    var oldState = args.OldState;
    var newState = args.NewState;
}

{% endhighlight %}
{% endtabs %}

