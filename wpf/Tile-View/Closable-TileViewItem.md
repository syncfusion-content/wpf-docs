---
layout: post
title: Closing TileView item in WPF TileViewControl | Syncfusion
description: This section explains how to control CloseButton behavior available in TileViewItem in Syncfusion TileViewControl
platform: wpf
control: TileViewControl
documentation: ug
---

# Closing or hiding TileViewItem

This section explains how to closing the [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html) and its functionalities in the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl.html).

## Show close button

By default, the close button is not displayed in the `TileViewItem`. If you want to display the close button on specific `TileViewItem`, use the [TileViewItem.CloseButtonVisibility](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseButtonVisibility.html) property value as `Visible`. The default value of `TileViewItem.CloseButtonVisibility` property is `Collapsed`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item 1" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 2" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 3" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 4" 
                             CloseButtonVisibility="Collapsed"/>
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1",
    CloseButtonVisibility= Visibility.Visible});
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2",
    CloseButtonVisibility = Visibility.Visible });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3",
    CloseButtonVisibility = Visibility.Visible });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 4",
    CloseButtonVisibility = Visibility.Collapsed });

{% endhighlight %}
{% endtabs %}

![Showing the close button on TileViewItem](Closing_images/CloseButton.png)

## Closing TileViewItem item 

You can close the `TileViewItem` by clicking the close button which is placed top-right corner of the header panel.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item 1" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 2" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 3" 
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 4" 
                             CloseButtonVisibility="Visible"/>
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1",
    CloseButtonVisibility= Visibility.Visible});
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2",
    CloseButtonVisibility = Visibility.Visible });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3",
    CloseButtonVisibility = Visibility.Visible });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 4",
    CloseButtonVisibility = Visibility.Visible });

{% endhighlight %}
{% endtabs %}

![TileViewItems closing by close button click](Closing_images/CloseButtonClick.gif)

## Closing TileViewItem programmatically

If you want to close the `TileViewItem` programmatically, pass that items into the [CloseTileViewItem()](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~CloseTileViewItem.html) method.

{% tabs %}
{% highlight XAML %}

 <Button Content="Close Item" 
         Click="CloseItem_Click"/>
         
<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item 1" />
    <syncfusion:TileViewItem Header="Item 2" />
    <syncfusion:TileViewItem Header="Item 3" />
    <syncfusion:TileViewItem />
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2" });
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3" });
tileViewControl.Items.Add(new TileViewItem());
Button button= new Button();
button.Click += CloseItem_Click

{% endhighlight %}
{% endtabs %}


You can handle the CloseItem_Click event as follows:

{% tabs %}
{% highlight C# %}

private void CloseItem_Click(object sender, RoutedEventArgs e) {
    //First item in the Items collection will be removed
    tileViewControl.CloseTileViewItem(tileViewControl.Items[0] as TileViewItem);
}

{% endhighlight %}
{% endtabs %}

![TileViewItems closed by programmatically](Closing_images/CloseTileView.gif)

## Hide or delete TileViewItem when closing a item

You can decide whether the `TileViewItem` can be only hidden from the view or removed from the items collection of `TileViewControl` by using the [CloseMode](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseMode.html) property while closing it. If you set `CloseMode` property as `Hide`, the `TileViewItem` will be hidden and the selection will be moved to previous index while hiding it. Also, if the property `CloseMode` is `Delete`, the `TileViewItem` will be removed from the items collection and the selection will be retained in the same index while removing it. The default value of the `CloseMode` property is `Hide`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Header="Item 1" CloseMode="Delete"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 2" CloseMode="Delete"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 3" CloseMode="Delete"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Header="Item 4" CloseMode="Delete"
                             CloseButtonVisibility="Visible"/>
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 1",
    CloseButtonVisibility= Visibility.Visible, CloseMode= CloseMode.Delete});
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 2", 
    CloseButtonVisibility = Visibility.Visible, CloseMode= CloseMode.Delete});
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 3", 
    CloseButtonVisibility = Visibility.Visible, CloseMode= CloseMode.Delete});
tileViewControl.Items.Add(new TileViewItem() { Header = "Item 4",
    CloseButtonVisibility = Visibility.Visible, CloseMode= CloseMode.Delete});

{% endhighlight %}
{% endtabs %}

![TileViewItems will delete from items collection](Closing_images/CloseMode.png)

## Custom UI of close button

You can customize the appearance of particular `TileViewItem`'s close button by using the [CloseButtonStyle](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseButtonStyle.html) property. You can also change the margin of the `TileViewItem` close button by using the [CloseButtonMargin](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~CloseButtonMargin.html) property. The `DataContext` of the `CloseButtonStyle` property is [TileViewItemCloseButton](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItemCloseButton.html).

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <Style x:Key="closeButtonStyle"
       TargetType="syncfusion:TileViewItemCloseButton">
        <Setter Property="Background" Value="Yellow"/>
    </Style>
</Window.Resources>
<Grid>
    <syncfusion:TileViewControl CloseButtonMargin="3"
                                Name="tileViewControl">
        <syncfusion:TileViewItem CloseButtonStyle="{StaticResource closeButtonStyle}"
                                 Header="Item 1" CloseButtonVisibility="Visible"/>
        <syncfusion:TileViewItem Header="Item 2" CloseButtonVisibility="Visible"/>
        <syncfusion:TileViewItem Header="Item 3" CloseButtonVisibility="Visible"/>
        <syncfusion:TileViewItem Header="Item 4" CloseButtonVisibility="Visible"/>
    </syncfusion:TileViewControl>
</Grid>

{% endhighlight %}
{% endtabs %}

![TileViewItems close button UI changed](Closing_images/CloseButtonStyle.png)

## TileViewItem closing notification

When the `TileViewItem` is closing, it will be notified by using the [TileViewItem.Closing](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~Closing_EV.html) event. You can restrict the closing of `TileViewItem` by using the [CloseEventArgs.Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem+CloseEventArgs~Cancel.html) property value as `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl">
    <syncfusion:TileViewItem Closing="TileViewItem_Closing" 
                             Header="Item 1"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Closing="TileViewItem_Closing" 
                             Header="Item 2"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Closing="TileViewItem_Closing"
                             Header="Item 3"
                             CloseButtonVisibility="Visible"/>
    <syncfusion:TileViewItem Closing="TileViewItem_Closing"
                             Header="Item 4"
                             CloseButtonVisibility="Visible"/>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void TileViewItem_Closing(object sender, TileViewItem.CloseEventArgs args) {
    //Restrict closing
    args.Cancel = true;
}

{% endhighlight %}
{% endtabs %}

