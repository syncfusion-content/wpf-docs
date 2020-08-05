---
layout: post
title: Minimize the TileViewItem in WPF TileView control | Syncfusion
description: Learn about how to minimizing the TileViewItems in Syncfusion WPF TileView control and more details about the control features.
platform: wpf
control: TileViewControl
documentation: ug
---

# Minimizing TileViewItem

You can minimize the [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html) and change its appearance in the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl.html).

## Minimize the TileViewItem

You can minimize the maximized `TileViewItem` by click on the minimize button.

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

## Direction for minimized items 

If you want to change direction of placing the minimized items, use the [MinimizedItemsOrientation](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~MinimizedItemsOrientation.html) property. The default value of `MinimizedItemsOrientation` property is `Right`.

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

tileViewControl.MinimizedItemsOrientation = MinimizedItemsOrientation.Bottom;

{% endhighlight %}
{% endtabs %}

![Minimized TileViewItem direction is changed as bottom](Minimize_images/MinimizedItemsOrientation.png)

## Allocate size for minimized TileViewItem

If you want to allocate a certain percentage of the total size to the minimized items, use the [MinimizedItemsPercentage](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~MinimizedItemsPercentage.html) property. The default value of `MinimizedItemsPercentage` property is `20`.

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

## Change minimized TileViewItem content

By default, `TileViewItem.Content` property values displayed as `TileViewItem` content on minimized state. If you want to change the content of the `TileViewItem` on minimized state, use the [MinimizedItemContent](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~MinimizedItemContent.html) property. The default value of `MinimizedItemContent` property is `null`.

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

## Custom UI of minimized TileViewItem content

You can customize the appearance of minimized `TileViewItem` content by using the [MinimizedItemTemplate](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~MinimizedItemTemplate.html) property. The `DataContext` of the `MinimizedItemTemplate` property is `TileViewItem.MinimizedItemContent`.

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

## Minimized state changed notification

The `TileViewControl` notifies that the minimized state changed in the `TileViewItem` by using [Minimized](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~Minimized_EV.html) event. You can get the minimized items by using the [Source](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewEventArgs~Source.html) property. You can also use the [OldState](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewEventArgs~OldState.html) and [NewState](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewEventArgs~NewState.html) properties to get the old and new state of `TileViewItem`.

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
