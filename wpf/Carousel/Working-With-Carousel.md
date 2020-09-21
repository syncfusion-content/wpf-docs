---
layout: post
title: Working with with WPF Carousel control | Syncfusion
description: Learn here about working of Syncfusion WPF Carousel control and more details about the control features.
platform: WPF
control: Carousel
documentation: ug
---

# Working with WPF Carousel

This section explains different UI customization and common features  available in [Carousel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html) control.

## Populating items using CarouselItem

You can add the carousel items inside the control using the [CarouselItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CarouselItem.html) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel x:Name="carousel" 
                     Height="700" Width="500">
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Buchanan.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Callahan.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Davolio-1.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Callahan.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/dodsworth.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Fuller.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/King.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
    <syncfusion:CarouselItem>
        <syncfusion:CarouselItem.Content>
            <Viewbox Height="100" Width="100">
                <Image Source="Images/Leverling.png"/>
            </Viewbox>
        </syncfusion:CarouselItem.Content>
    </syncfusion:CarouselItem>
</syncfusion:Carousel>

{% endhighlight %}
{% highlight C# %}

Carousel carousel = new Carousel()
{ 
	Width=700, 
	Height = 500
};

Image image = new Image();
Image image1 = new Image();
Image image2 = new Image();
Image image3 = new Image();
Image image4 = new Image();
Image image5 = new Image();
Image image6 = new Image();
Image image7 = new Image();

BitmapImage bitimg1 = new BitmapImage(new Uri("/Sample;component/Images/1.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg2 = new BitmapImage(new Uri("/Sample;component/Images/2.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg3 = new BitmapImage(new Uri("/Sample;component/Images/3.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg4 = new BitmapImage(new Uri("/Sample;component/Images/4.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg5 = new BitmapImage(new Uri("/Sample;component/Images/5.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg6 = new BitmapImage(new Uri("/Sample;component/Images/6.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg7 = new BitmapImage(new Uri("/Sample;component/Images/7.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg8 = new BitmapImage(new Uri("/Sample;component/Images/8.png", UriKind.RelativeOrAbsolute));

image.Source = bitimg1 as ImageSource;
image1.Source = bitimg2 as ImageSource;
image2.Source = bitimg3 as ImageSource;
image3.Source = bitimg4 as ImageSource;
image4.Source = bitimg5 as ImageSource;
image5.Source = bitimg6 as ImageSource;
image6.Source = bitimg7 as ImageSource;
image7.Source = bitimg8 as ImageSource;
          
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image1 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image2 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image3 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image4 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image5 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image6 }});
carousel.Items.Add(new CarouselItem() { Content = new Viewbox(){ Child = image7 }});

{% endhighlight %}
{% endtabs %}

![Carousel items are populated to the Carousel control](Getting-Started_images/wpf-carousel-item.jpeg)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/CarouselItem-Selection)

## Populating items using collection binding

You can populate items to the `Carousel` control by setting the collection value to the `ItemsSource` property. 

{% tabs %}
{% highlight C# %}

//Model.cs
public class CarouselModel {
	public string Header { get; set; }
}

//ViewModel.cs
public class ViewModel {
	private ObservableCollection<CarouselModel> collection;
	public ObservableCollection<CarouselModel> HeaderCollection
	{
		get {
			return collection;
		}
		set {
			collection = value;
		}
	}
	public ViewModel() {
		HeaderCollection = new ObservableCollection<CarouselModel>();
		HeaderCollection.Add(new CarouselModel() { Header = "Buchanan" });
		HeaderCollection.Add(new CarouselModel() { Header = "Callahan" });
		HeaderCollection.Add(new CarouselModel() { Header = "Davolio" });
		HeaderCollection.Add(new CarouselModel() { Header = "Dodsworth" });
		HeaderCollection.Add(new CarouselModel() { Header = "Fuller" });
		HeaderCollection.Add(new CarouselModel() { Header = "King" });
		HeaderCollection.Add(new CarouselModel() { Header = "Leverling" });
		HeaderCollection.Add(new CarouselModel() { Header = "Suyama" });
	}
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

<Grid>
    <syncfusion:Carousel Name="Carousel"
                         ItemsSource="{Binding HeaderCollection}">
        <syncfusion:Carousel.ItemTemplate>
            <DataTemplate>
                <Border Height="50" 
                        Width="100" 
                        BorderBrush="Purple" 
                        BorderThickness="5"
                        Background="LightBlue">
                    <TextBlock HorizontalAlignment="Center" 
                               VerticalAlignment="Center" 
                               Text="{Binding Header}"/>
                </Border>
            </DataTemplate>
        </syncfusion:Carousel.ItemTemplate>
    </syncfusion:Carousel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Carousel items populated by using the collection binding](Getting-Started_images/wpf-carousel-item-binding.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Binding)

## Custom view path

By default, carousel items are arranged in a circular path. If you want to customize the view path of carousel item, use the [VisualMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_VisualMode) property value as `CustomPath`. The default value of `VisualMode` property is `Standard`.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel VisualMode="CustomPath"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

carousel.VisualMode = VisualMode.CustomPath;

{% endhighlight %}
{% endtabs %}

![Carousel items visual path customized to U shape](Getting-Started_images/VisualMode.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/CustomPath)

### Change custom view path

You can change the custom view path of the carousel items by using the [Path](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_Path) property. The default value of `Path` property is `null`.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel VisualMode="CustomPath"
                     Name="carousel">
    <syncfusion:Carousel.Path>
        <Path Data="M0,100 L100,20" 
              Stroke="Blue" 
              StrokeThickness="2" 
              HorizontalAlignment="Stretch"
              VerticalAlignment="Stretch"/>
    </syncfusion:Carousel.Path>
</syncfusion:Carousel>

{% endhighlight %}
{% highlight C# %}

carousel.VisualMode = VisualMode.CustomPath;

{% endhighlight %}
{% endtabs %}

![Customized visual path of Carousel items](customization_images/Path.gif)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Binding)

## Change display item count

You can change the number of carousel items displayed per page in the `Carousel` control by using the [ItemsPerPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_ItemsPerPage) property. `ItemsPerPage` is  effective only on `VisualMode.CustomPath` view mode. The default value of `ItemsPerPage` property is `-1`.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel ItemsPerPage="3"
                     VisualMode="CustomPath"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

carousel.ItemsPerPage = 3;
carousel.VisualMode = VisualMode.CustomPath;

{% endhighlight %}
{% endtabs %}

![Number of items displayed in the Carousel control is reduced](Getting-Started_images/ItemsPerPage.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/CustomPath)

## Select carousel item

You can select a carousel item by mouse click on the specific item. You can get the selected item and its value by using the [SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectedItem) and [SelectedValue](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectedValue) properties. You can also get the selected item index by using the [SelectedIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectedIndex) property. You can only select a single item at a time.

### Select carousel item programmatically using property

You can select a particular carousel item programmatically by using the [CarouselItem.IsSelected](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CarouselItem.html#Syncfusion_Windows_Shared_CarouselItem_IsSelected) property.

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <Style x:Key="selecteditemStyle" TargetType="syncfusion:CarouselItem" >
        <Style.Triggers>
            <Trigger Property="IsSelected" Value="True">
                <Setter Property="Foreground" Value="Red"/>
                <Setter Property="FontWeight" Value="Bold"/>
            </Trigger>
        </Style.Triggers>
    </Style>
</Window.Resources>
<Grid>
    <syncfusion:Carousel ItemContainerStyle="{StaticResource selecteditemStyle}" 
                         x:Name="carousel">
        <syncfusion:CarouselItem Content="Item1"/>
        <syncfusion:CarouselItem Content="Item2"/>
        <syncfusion:CarouselItem Content="Item3" IsSelected="True"/>
        <syncfusion:CarouselItem Content="Item4"/>
        <syncfusion:CarouselItem Content="Item5"/>
    </syncfusion:Carousel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Particular carousel item selected using IsSelected property](Getting-Started_images/IsSelected.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/CarouselItem-Selection)

### Select carousel item programmatically using command and methods

You can select a previous, next, first or last carousel items programmatically by using the commands and methods.

* [SelectFirstItemCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectFirstItemCommand) or [SelectFirstItem()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectFirstItem().html) - To select the first item.

* [SelectLastItemCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectLastItemCommand) or [SelectLastItem()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectLastItem().html) - To select the last item.

* [SelectPreviousItemCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectPreviousItemCommand) or [SelectPreviousItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectPreviousItem().html) - To select the previous item from the currently selected item.

* [SelectNextItemCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectNextItemCommand) or [SelectNextItem()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectNextItem().html) - To select the next item from the currently selected item.

* [SelectPreviousPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectPreviousPageCommand) or [SelectPreviousPage()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectPreviousPage().html) - To select the previous page item.

* [SelectNextPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectNextPageCommand) or [SelectNextPage()](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_SelectNextPage().html) - To select the next page item.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/Carousel-Scrolling)

## Selected item changed notification

The selected item changed in `Carousel` can be examined using [SelectionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html) event. The `SelectionChanged` event contains the old and newly selected item in the `OldValue` and `NewValue` properties.

{% tabs %}
{% highlight XAML %}

 <syncfusion:Carousel SelectionChanged="Carousel_SelectionChanged" 
                      Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

Carousel carousel = new Carousel();
carousel.SelectionChanged += Carousel_SelectionChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight C# %}

private void Carousel_SelectionChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {
    //Get old and new selected carousel item
    var oldValue = e.OldValue;
    var newValue = e.NewValue;
}

{% endhighlight %}
{% endtabs %}

## Change radius of carousel item

You can change the radius of the `Carousel` control by setting the value to the [RadiusX](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_RadiusX) and [RadiusY](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_RadiusY) properties. Based on the radius points, items are arranged. This will effective only on `VisualMode.Standard` view mode. The default value of `RadiusX` property is `250` and `RadiusY` property is `150`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel RadiusX="100" 
                     RadiusY="100" 
                     VisualMode="Standard"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

carousel.RadiusX = 100;
carousel.RadiusY = 100;
carousel.VisualMode = VisualMode.Standard;

{% endhighlight %}
{% endtabs %}

![The radius of the carousel control changed](Getting-Started_images/radius.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/StandardPath)

## Setting the background

You can change the background color of `Carousel` by using the `Background` property. The default value of `Background` property is `White`.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel Background="Red"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

carousel.Background = Brushes.Red;

{% endhighlight %}
{% endtabs %}

![Carousel with red background](customization_images/Background.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/StandardPath)

## Change flow direction

You can change the flow direction of the `Carousel` layout from right to left by setting the `FlowDirection` property value as `RightToLeft`. The default value of `FlowDirection` property is `LeftToRight`.

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel FlowDirection="RightToLeft"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

Carousel carousel = new Carousel();
carousel.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![Carousel with RightToLeft flow direction](customization_images/FlowDirection.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/StandardPath)

## Virtualization support

You can enable the UI virtualization support in `Carousel`, which allows the users to load large sets of data without affecting loading or scrolling performance by setting the [EnableVirtualization](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.Carousel.html#Syncfusion_Windows_Shared_Carousel_EnableVirtualization) property value as `true`. This feature allows users to reduce the loading time of `Carousel` items regardless of items count. The default value of `EnableVirtualization` property is `false`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:Carousel EnableVirtualization="True"
                     Name="carousel"/>

{% endhighlight %}
{% highlight C# %}

Carousel carousel = new Carousel();
carousel.EnableVirtualization = true;

{% endhighlight %}
{% endtabs %}

## Custom UI for carousel item using template

You can customize the appearance of each carousel item by using the `ItemTemplate` property. If you want to change the appearance of particular carousel item appearance, use `ItemTemplateSelector` property. The `DataContext` of the `ItemTemplate` property is `CarouselItem`.

{% tabs %}
{% highlight C# %}

//Model.cs
public class CarouselModel {
	public string Header { get; set; }
}

//ViewModel.cs
public class ViewModel {
	private ObservableCollection<CarouselModel> collection;
	public ObservableCollection<CarouselModel> HeaderCollection	{
		get {
			return collection;
		}
		set {
			collection = value;
		}
	}
	public ViewModel() {
		HeaderCollection = new ObservableCollection<CarouselModel>();
		HeaderCollection.Add(new CarouselModel() { Header = "Buchanan" });
		HeaderCollection.Add(new CarouselModel() { Header = "Callahan" });
		HeaderCollection.Add(new CarouselModel() { Header = "Davolio" });
		HeaderCollection.Add(new CarouselModel() { Header = "Dodsworth" });
		HeaderCollection.Add(new CarouselModel() { Header = "Fuller" });
		HeaderCollection.Add(new CarouselModel() { Header = "King" });
		HeaderCollection.Add(new CarouselModel() { Header = "Leverling" });
		HeaderCollection.Add(new CarouselModel() { Header = "Suyama" });
	}
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>

<Grid>
    <syncfusion:Carousel ItemsSource="{Binding HeaderCollection}"
                         ScaleFraction="0.5"
                         Name="carousel" >
        <syncfusion:Carousel.ItemTemplate>
            <DataTemplate>
                <Grid>
                    <Ellipse Width="200" Height="100" 
                             Stroke="Green" 
                             StrokeThickness="4"
                             Fill="Yellow"/>
                    <TextBlock HorizontalAlignment="Center" 
                               VerticalAlignment="Center" 
                               Text="{Binding Header}"/>
                </Grid>
            </DataTemplate>
        </syncfusion:Carousel.ItemTemplate>
    </syncfusion:Carousel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Custom UI of carousel item using ItemTemplate](customization_images/ItemTemplate.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/ItemTemplate)

## Custom UI for carousel item using style

You can change the each carousel item appearance by using the `ItemContainerStyle` which is applied to the container element that generated for each carousel item. The default value of `ItemContainerStyle` is `null`. The `DataContext` of the `ItemContainerStyle` property is `CarouselItem`.

{% tabs %}
{% highlight C# %}

//Model.cs
public class CarouselModel {
	public string Header { get; set; }
	public ImageSource ImageSource { get; set; }

}

//ViewModel.cs
public class ViewModel {
	private ObservableCollection<CarouselModel> persons;
	public ObservableCollection<CarouselModel> Persons
	{
		get {
			return persons;
		}
		set {
			persons = value;
		}
	}
	public ViewModel() {
		Persons = new ObservableCollection<CarouselModel>();
		Persons.Add(new CarouselModel() {
			Header = "Buchanan",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Buchanan.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Callahan",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Callahan.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Davolio",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Davolio-1.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Dodsworth",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/dodsworth.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Fuller",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Fuller.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "King",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/King.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Leverling",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Leverling.png", UriKind.RelativeOrAbsolute))
		});
		Persons.Add(new CarouselModel() {
			Header = "Suyama",
			ImageSource = new BitmapImage
			(new Uri(@"/Images/Suyama.png", UriKind.RelativeOrAbsolute))
		});
	}
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.DataContext>
    <local:ViewModel/>
</Window.DataContext>
<Grid>
    <syncfusion:Carousel ScaleFraction="0.5" 
                         VisualMode="Standard"
                         Name="carousel" 
                         ItemsSource="{Binding Persons}">
        <syncfusion:Carousel.ItemContainerStyle>
            <Style TargetType="syncfusion:CarouselItem">
                <Setter Property="Template">
                    <Setter.Value>
                        <ControlTemplate TargetType="syncfusion:CarouselItem">
                            <Grid>
                                <Grid.RowDefinitions>
                                    <RowDefinition/>
                                    <RowDefinition/>
                                </Grid.RowDefinitions>
                                <Border x:Name="border">
                                    <Grid>
                                        <Ellipse Stroke="Red" 
                                                 StrokeThickness="4"
                                                 Fill="Yellow"/>
                                        <Border Margin="20">
                                            <Grid>
                                                <Grid.RowDefinitions>
                                                    <RowDefinition Height="*"/>
                                                    <RowDefinition Height="Auto"/>
                                                </Grid.RowDefinitions>
                                                <Viewbox  Height="150" Width="150">
                                                    <Image Source="{Binding ImageSource}"/>
                                                </Viewbox>
                                                <TextBlock Text="{Binding Header}"
                                                           FontWeight="Bold" 
                                                           Grid.Row="1"
                                                           HorizontalAlignment="Center" />
                                            </Grid>
                                        </Border>
                                    </Grid>
                                </Border>
                            </Grid>
                        </ControlTemplate>
                    </Setter.Value>
                </Setter>
            </Style>
        </syncfusion:Carousel.ItemContainerStyle>
    </syncfusion:Carousel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Custom UI of carousel item using ItemContainerStyle](customization_images/ItemContainerStyle.jpg)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/ItemContainerStyle)

## Custom UI for specific carousel item using style selector

You can select a various custom appearance for the carousel items by using the `ItemContainerStyleSelector` property. The `DataContext` of the `ItemContainerStyleSelector` property is `CarouselItem`.

{% tabs %}
{% highlight C# %}

//Model.cs
public class CarouselModel {
    public string Name { get; set; }
    public int Age { get; set; }
}   

//ViewModel.cs
public class ViewModel {
    private ObservableCollection<CarouselModel> persons;
    public ObservableCollection<CarouselModel> Persons {
        get {
            return persons;
        }
        set {
            persons = value;
        }
    }
    public ViewModel() {
        Persons = new ObservableCollection<CarouselModel>();
        Persons.Add(new CarouselModel() { Name = "Buchanan", Age = 40 });
        Persons.Add(new CarouselModel() { Name = "Callahan", Age = 53 });
        Persons.Add(new CarouselModel() { Name = "Davolio", Age = 42 });
        Persons.Add(new CarouselModel() { Name = "Dodsworth", Age = 60 });
        Persons.Add(new CarouselModel() { Name = "Fuller", Age = 46 });
        Persons.Add(new CarouselModel() { Name = "King", Age = 65 });
        Persons.Add(new CarouselModel() { Name = "Leverling", Age = 57 });
        Persons.Add(new CarouselModel() { Name = "Suyama", Age = 30 });
    }
}

// A class that choose style for for the items
public class PersonStyleSelector : StyleSelector {
    public Style ElderStyle { get; set; }
    public Style YoungerStyle { get; set; }
    public override Style SelectStyle(object item, DependencyObject container) {
        if ((item as CarouselModel).Age > 50)
            return ElderStyle;
        else
            return YoungerStyle;
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <Style TargetType="syncfusion:CarouselItem" x:Key="elderStyle">
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate>
                    <Grid>
                        <Ellipse Width="100" Height="50" 
                             Stroke="Purple" 
                             StrokeThickness="4"
                             Fill="LightBlue"/>
                        <TextBlock HorizontalAlignment="Center" 
                               VerticalAlignment="Center" 
                               Text="{Binding Name}"/>
                    </Grid>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>

    <Style TargetType="syncfusion:CarouselItem" x:Key="youngerStyle">
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate>
                    <Border Height="50" 
                        Width="100" 
                        BorderBrush="Yellow" 
                        BorderThickness="5"
                        Background="LightBlue">
                        <TextBlock HorizontalAlignment="Center" 
                               VerticalAlignment="Center" 
                               Text="{Binding Name}"/>
                    </Border>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
    <local:PersonStyleSelector x:Key="personStyleSelector"
                               ElderStyle="{StaticResource elderStyle}" 
                               YoungerStyle="{StaticResource youngerStyle}"/>
</Window.Resources>

<Grid>
    <syncfusion:Carousel ItemContainerStyleSelector="{StaticResource personStyleSelector}"
                         ItemsSource="{Binding Persons}"
                         DisplayMemberPath="Name" 
                         ScaleFraction="0.5"
                         VisualMode="Standard"
                         Name="carousel" >
        <syncfusion:Carousel.DataContext>
            <local:ViewModel></local:ViewModel>
        </syncfusion:Carousel.DataContext>          
    </syncfusion:Carousel>
</Grid>

{% endhighlight %}
{% endtabs %}

![Different custom UI of carousel items using ItemContainerStyleSelector](customization_images/ItemContainerStyleSelector.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-carousel-examples/tree/master/Samples/ItemContainerStyleSelector)
