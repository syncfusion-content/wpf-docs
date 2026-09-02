---
layout: post
title: Item Navigation in WPF Carousel | Syncfusion®
description: Navigate WPF Carousel items using keyboard shortcuts, mouse wheel scrolling, scroll bars, commands, and looping support.
platform: wpf
control: Carousel 
documentation: ug
---

# Items Navigation in WPF Carousel

You can navigate to WPF Carousel items by using the mouse or keyboard navigation in the [WPF Carousel](https://www.syncfusion.com/wpf-controls/carousel) control.

## Navigate WPF CarouselItem using keyboard navigation

You can navigate to the previous or next WPF Carousel items one at a time in either direction by pressing the keyboard keys.

{% tabs %}
{% highlight C# %}

//Model.cs
public class Model {
    private string header;
    public string Header {
        get { return header; }
        set { header = value; }
    }
}

//Viewmodel.cs
public class ViewModel {
    private ObservableCollection<Model> carouselItem;
    public ObservableCollection<Model> CarouselItem {
        get { return carouselItem; }
        set { carouselItem = value; }
    }
    public ViewModel() {
        CarouselItem = new ObservableCollection<Model>();
        CarouselItem.Add(new Model() { Header = "Item1" });
        CarouselItem.Add(new Model() { Header = "Item2" });
        CarouselItem.Add(new Model() { Header = "Item3" });
        CarouselItem.Add(new Model() { Header = "Item4" });
        CarouselItem.Add(new Model() { Header = "Item5" });
        CarouselItem.Add(new Model() { Header = "Item6" });
        CarouselItem.Add(new Model() { Header = "Item7" });
        CarouselItem.Add(new Model() { Header = "Item8" });
        CarouselItem.Add(new Model() { Header = "Item9" });
        CarouselItem.Add(new Model() { Header = "Item10" });
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:Carousel Name="Carousel"
                     ItemsSource="{Binding CarouselItem}">
    <syncfusion:Carousel.DataContext>
        <local:ViewModel/>
    </syncfusion:Carousel.DataContext>
    <syncfusion:Carousel.ItemTemplate>
        <DataTemplate>
            <Border Height="40"
                    Width="60"
                    BorderBrush="Purple"
                    BorderThickness="5"
                    Background="LightBlue">
                <TextBlock Text="{Binding Header}" 
                           HorizontalAlignment="Center"
                           VerticalAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:Carousel.ItemTemplate>
</syncfusion:Carousel>

{% endhighlight %}
{% endtabs %}

The following table explains how to navigate the WPF CarouselItem using the keyboard:

<table>
<tr>
<th> S.No </th>
<th> Key </th>
<th> Description </th>
<th> Image </th>
</tr>
<tr>
<td>1</td>
<td>Up, Left</td>
<td>Navigate to the previous item from the currently selected item.</td>
<td>
<img src="Scrolling_images/Up.png" alt="Navigate to the next item from the currently selected item"/></td>
</tr>
<tr>
<td>2</td>
<td>Down, Right</td>
<td>Navigate to the next item from the currently selected item.</td>
<td>
<img src="Scrolling_images/Down.png" alt="Navigate to the previous item from the currently selected item"/></td>
</tr>
<tr>
<td>3</td>
<td>Home, Ctrl+Up, Ctrl+Left</td>
<td>Navigate to the first item from the currently selected item.</td>
<td>
<img src="Scrolling_images/Home.png" alt="Navigate to the first item from the currently selected item"/></td>
</tr>
<tr>
<td>4</td>
<td>End, Ctrl+Down, Ctrl+Right</td>
<td>Navigate to the last item from the currently selected item.</td>
<td>
<img src="Scrolling_images/End.png" alt="Navigate to the last item from the currently selected item"/></td>
</tr>
<tr>
<td>5</td>
<td>Page Up</td>
<td>Navigate to the previous page item from the current page item based on the `ItemsPerPage` property value. Here, the `ItemsPerPage` value is 5.</td>
<td>
<img src="Scrolling_images/PageUp.png" alt="Navigate to the previous page item from the current page item"/></td>
</tr>
<tr>
<td>6</td>
<td>Page Down</td>
<td>Navigate to the next page item from the current page item based on the `ItemsPerPage` property value. Here, the `ItemsPerPage` value is 5.</td>
<td>
<img src="Scrolling_images/PageDown.png" alt="Navigate to the next page item from the current page item"/></td>
</tr>
</table>

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling)

## Navigate WPF CarouselItem using scroll bar

By default, scroll bars are collapsed. To navigate to the previous or next item from the currently selected item by using scroll bars, enable the vertical or horizontal scroll bars by setting the `ScrollViewer.VerticalScrollBarVisibility` or `ScrollViewer.HorizontalScrollBarVisibility` properties to `Visible` or `auto`.

N> If you set the `ScrollViewer.VerticalScrollBarVisibility` or `ScrollViewer.HorizontalScrollBarVisibility` properties to `Auto`, the scroll bar is automatically visible based on the items.

{% tabs %}
{% highlight xaml %}

<syncfusion:Carousel ScrollViewer.VerticalScrollBarVisibility="Visible" 
                     ScrollViewer.HorizontalScrollBarVisibility="Visible"
                     VisualMode="CustomPath"
                     Name="carousel"
                     ItemsSource="{Binding CarouselItem}">
    <syncfusion:Carousel.Path>
        <Path Data="M0,0 L100,0" />
    </syncfusion:Carousel.Path>

    <syncfusion:Carousel.DataContext>
        <local:ViewModel/>
    </syncfusion:Carousel.DataContext>
    <syncfusion:Carousel.ItemTemplate>
        <DataTemplate>
            <Border Height="100"
                    Width="100"
                    BorderBrush="Purple"
                    BorderThickness="5"
                    Background="LightBlue">
                <TextBlock Text="{Binding Header}" 
                           HorizontalAlignment="Center"
                           VerticalAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:Carousel.ItemTemplate>
</syncfusion:Carousel>

{% endhighlight %}
{% highlight C# %}

ScrollViewer.SetHorizontalScrollBarVisibility(carousel, ScrollBarVisibility.Visible);
ScrollViewer.SetVerticalScrollBarVisibility(carousel, ScrollBarVisibility.Visible);

{% endhighlight %}
{% endtabs %}

![Navigate WPF CarouselItem using scroll bars](Scrolling_images/scrollbar.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling)

## Navigate WPF CarouselItem using mouse wheel

You can navigate to the previous or next item one by one from the currently selected item by using the mouse wheel on forward and backward direction.

![Navigate WPF CarouselItem using mouse wheel](Scrolling_images/Mousewheel.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling)

## Navigate using commands

You can navigate to the first, last, previous, or next items, as well as the previous or next page, by using the built-in commands in the `Carousel` control.

<table>
<tr>
<th> S.No </th>
<th> Command </th>
<th> Description </th>
<th> Keyboard shortcut </th>
</tr>
<tr>
<td>1</td>
<td>SelectFirstItemCommand</td>
<td>This command selects the first item in WPF Carousel control. It is executed when home key is pressed.</td>
<td>Home</td>
</tr>
<tr>
<td>2</td>
<td>SelectLastItemCommand</td>
<td>This command selects the last item in WPF Carousel control. It is executed when end key is pressed.</td>
<td>End</td>
</tr>
<tr>
<td>3</td>
<td>SelectNextItemCommand</td>
<td>This command selects the next item in WPF Carousel control. It is executed when right or down arrow key is pressed.</td>
<td>Right and Down arrow</td>
</tr>
<tr>
<td>4</td>
<td>SelectPreviousItemCommand</td>
<td>This command selects the previous item in WPF Carousel control. It is executed when left or top arrow key is pressed.</td>
<td>Left and Top arrow</td>
</tr>
<tr>
<td>5</td>
<td>SelectNextPageCommand</td>
<td>This command selects the item in next page of WPF Carousel control. It is executed when page down key is pressed.</td>
<td>PageDown</td>
</tr>
<tr>
<td>6</td>
<td>SelectPreviousPageCommand</td>
<td>This command selects the item in previous page of WPF Carousel control. It is executed when page up key is pressed.</td>
<td>PageUp</td>
</tr>
</table>

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling)

## Looping items in Custom path view

The WPF Carousel supports looping, which allows items to loop after the last item is reached. In `Standard` visual mode, Carousel items can be scrolled in a circular manner. In `CustomPath` visual mode, Carousel items are scrolled linearly, and the first or last item can be hidden from view. To bring the first or last item into view in a circular manner, set the [EnableLooping](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_EnableLooping) property to `true`. The default value of the `EnableLooping` property is `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:Carousel EnableLooping="True"
                     VisualMode="CustomPath"
                     Name="Carousel"
                     ItemsSource="{Binding CarouselItem}">
    <syncfusion:Carousel.Path>
        <Path Data="M0,0 L100,0" />
    </syncfusion:Carousel.Path>

    <syncfusion:Carousel.DataContext>
        <local:ViewModel/>
    </syncfusion:Carousel.DataContext>
    <syncfusion:Carousel.ItemTemplate>
        <DataTemplate>
            <Border Height="40"
                    Width="60"
                    BorderBrush="Purple"
                    BorderThickness="5"
                    Background="LightBlue">
                <TextBlock Text="{Binding Header}" 
                           HorizontalAlignment="Center"
                           VerticalAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:Carousel.ItemTemplate>
</syncfusion:Carousel>

{% endhighlight %}
{% highlight C# %}

Carousel.EnableLooping = true;
Carousel.VisualMode = VisualMode.CustomPath;

{% endhighlight %}
{% endtabs %}

![Circular scroll WPF CarouselItem](Scrolling_images/EnableLooping.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling) 


