---
layout: post
title: Data Binding in WPF Tile View control | Syncfusion
description: Learn about Data Binding support in Syncfusion Essential Studio WPF Tile View control, its elements and more.
platform: wpf
control: TileViewControl
documentation: ug
---

# Data Binding in WPF Tile View

You can add a [TileViewItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewItem.html) using data binding in the WPF [TileViewControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html).

## Data binding to Objects

The `TileViewControl` can bound to an external source to auto create `TileViewItem` and display the data using `ItemsSource` property. When you are auto generating `TileViewItem` using `ItemsSource`, you need to set `Header` property or `HeaderTemplate` in `ItemContainerStyle` to define header and use `Content` property or `ContentTemplate` in `ItemContainerStyle` to display the content of the `TileViewItem` item.  

N> To bind `ItemsSource` to `TileViewControl`, you need to have collection with data object which holds header and content details.

Here, `TileItem` class defined with `Header` and `Content` properties and `ViewModel` class has `ItemsSource` property of type `ObservableCollection<TileItem>`.

{% tabs %}
{% highlight C# %}

// Model.cs
public class TileItem {
    public string Header { get; set; }
    public string Content { get; set; }
    public TileItem() {
    }
}

//ViewModel.cs
public class ViewModel : NotificationObject {
    private ObservableCollection<TileItem> tileViewItems;
    public ObservableCollection<TileItem> TileViewItems {
        get { return tileViewItems; }
        set {
            tileViewItems = value;
            this.RaisePropertyChanged(nameof(TileViewItems));
        }
    }

    public ViewModel() {
        tileViewItems = new ObservableCollection<TileItem>();
        PopulateCollection();
    }

    public void PopulateCollection() {
        //Adding the tileview items into the collection
        TileViewItems.Add(new TileItem() { Header = "Item 1", Content = "Content 1" });
        TileViewItems.Add(new TileItem() { Header = "Item 2", Content = "Content 2" });
        TileViewItems.Add(new TileItem() { Header = "Item 3", Content = "Content 3" });
        TileViewItems.Add(new TileItem() { Header = "Item 4", Content = "Content 4" });   
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl ItemsSource="{Binding TileViewItems}" 
                            Name="tileViewControl">
    <syncfusion:TileViewControl.ItemContainerStyle>
        <Style TargetType="{x:Type syncfusion:TileViewItem}">
            <Setter Property="Header" Value="{Binding Header}" />
            <Setter Property="Content" Value="{Binding Content}"/>
        </Style>
    </syncfusion:TileViewControl.ItemContainerStyle>
    
    <syncfusion:TileViewControl.DataContext>
        <local:ViewModel/>
    </syncfusion:TileViewControl.DataContext>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

![TileViewControl auto creates tileview item from objects using data binding](Data-binding_images/Data-Binding_img1.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/Binding-Object)

## Data binding with XML

You can bind the `XML` file as `ItemsSource` for creating the `TileViewItem` in the `TileViewControl`. You can easily populates the items from the `XML` files using the `ItemTemplate` and `ContentTemplate` or `ItemContainerStyle` properties. 

1.Create an `XML` file with the required details and name it as `Data.xml`.

{% tabs %}
{% highlight XAML %}


<?xml version="1.0" encoding="utf-8" ?>
<Books>
  <Book Name="Programming C# 4.0" 
        Description="Learn C# fundamentals, such as variables,
                     flow control, loops, and methods"/>
  <Book Name="Programming WPF" 
        Description="A tutorial on XAML, the new HTML-like markup
                     language for declaring Windows UI"/>
  <Book Name="Essential WPF" 
        Description="Visuals and media, including 2D, 3D, video,
                     and animation"/>
  <Book Name="WPF Unleashed" 
        Description="Examines the WPF feature areas in incredible 
                     depth: controls, layout, resources, data binding,
                     styling, graphics, animation, and more"/>
</Books>

{% endhighlight %}
{% endtabs %}

2.Add `XmlDataProvider` for the above `Data.xml` document and bind the data to `ItemsSource` property for the `TileViewControl`.

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <XmlDataProvider Source="Data.xml" x:Key="xmlSource" XPath="Books"/>
</Window.Resources>
<Grid>
    <syncfusion:TileViewControl Name="tileViewControl"
                                ItemsSource="{Binding Source={StaticResource xmlSource},
                                                      XPath=Book}">
        <syncfusion:TileViewControl.ItemContainerStyle>
            <Style TargetType="{x:Type syncfusion:TileViewItem}">
                <Setter Property="Header" Value="{Binding XPath=@Name}" />
                <Setter Property="ContentTemplate">
                    <Setter.Value>
                        <DataTemplate>
                            <TextBlock Text="{Binding XPath=@Description}"/>
                        </DataTemplate>
                    </Setter.Value>
                </Setter>
            </Style>
        </syncfusion:TileViewControl.ItemContainerStyle>
    </syncfusion:TileViewControl>
</Grid>

{% endhighlight %}
{% endtabs %}

![TileViewControl auto creates tileview item from XML using data binding](Data-binding_images/Data-Binding_img2.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/Binding-XML)

## Virtualization support

You can enable the UI virtualization support in `TileViewControl`, which allows the users to load large sets of data without affecting loading or scrolling performance by setting the [IsVirtualizing](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.TileViewControl.html#Syncfusion_Windows_Shared_TileViewControl_IsVirtualizing) property value as `true`. This feature allows users to reduce the loading time of `TileView` items regardless of items count. The default value of `IsVirtualizing` property is `false`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl IsVirtualizing="True"
                            Name="tileViewControl"/>

{% endhighlight %}
{% highlight C# %}

TileViewControl tileViewControl = new TileViewControl();
tileViewControl.IsVirtualizing = true;

{% endhighlight %}
{% endtabs %}


## TileViewItem header

You can define the `TileViewItem` header using `HeaderTemplate` or `TileViewItem.ItemContainerStyle` property. Otherwise, `TileViewItem` header will display the data object class name which is associated with `TileViewItem`. The `DataContext` of the `HeaderTemplate` property is `TileViewItem.Header`.

{% tabs %}
{% highlight C# %}

// Model.cs
public class TileItem {
    public string Header { get; set; }
    public string Content { get; set; }
    public TileItem() {
    }
}

//ViewModel.cs
public class ViewModel : NotificationObject {
    private ObservableCollection<TileItem> tileViewItems;
    public ObservableCollection<TileItem> TileViewItems {
        get { return tileViewItems; }
        set {
            tileViewItems = value;
            this.RaisePropertyChanged(nameof(TileViewItems));
        }
    }

    public ViewModel() {
        tileViewItems = new ObservableCollection<TileItem>();
        PopulateCollection();
    }

    public void PopulateCollection() {
        //Adding the tileview items into the collection
        TileViewItems.Add(new TileItem() { Header = "Item 1", Content = "Content 1" });
        TileViewItems.Add(new TileItem() { Header = "Item 2", Content = "Content 2" });
        TileViewItems.Add(new TileItem() { Header = "Item 3", Content = "Content 3" });
        TileViewItems.Add(new TileItem() { Header = "Item 4", Content = "Content 4" });   
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl"
                            ItemsSource="{Binding TileViewItems}"> 
    <syncfusion:TileViewControl.HeaderTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Header}"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center" />
        </DataTemplate>
    </syncfusion:TileViewControl.HeaderTemplate>
    
    <syncfusion:TileViewControl.ItemContainerStyle>
        <Style TargetType="syncfusion:TileViewItem">
            <Setter Property="Content" Value="{Binding Content}"/>
        </Style>
    </syncfusion:TileViewControl.ItemContainerStyle>

    <syncfusion:TileViewControl.DataContext>
        <viewmodel:ViewModel/>
    </syncfusion:TileViewControl.DataContext>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

![TileViewItem header assigned by using the HeaderTemplate](Data-binding_images/header.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/Binding-Object)

## TileViewItem content

You can define the `TileViewItem` content using `ItemTemplate` or `TileViewItem.ItemContainerStyle` property. Otherwise, `TileViewItem` content will display the data object class name which is associated with `TileViewItem`. The `DataContext` of the `ItemTemplate` property is `TileViewItem.Content`.

{% tabs %}
{% highlight XAML %}

<syncfusion:TileViewControl Name="tileViewControl"
                            ItemsSource="{Binding TileViewItems}">  
    <syncfusion:TileViewControl.ItemTemplate>
        <DataTemplate>
            <TextBlock Text="{Binding Content}"
                       HorizontalAlignment="Center" 
                       VerticalAlignment="Center" />
        </DataTemplate>
    </syncfusion:TileViewControl.ItemTemplate>
    
    <syncfusion:TileViewControl.ItemContainerStyle>
        <Style TargetType="syncfusion:TileViewItem">
            <Setter Property="Header" Value="{Binding Header}"/>
        </Style>
    </syncfusion:TileViewControl.ItemContainerStyle>

    <syncfusion:TileViewControl.DataContext>
        <viewmodel:ViewModel/>
    </syncfusion:TileViewControl.DataContext>
</syncfusion:TileViewControl>

{% endhighlight %}
{% endtabs %}

![TileViewItem content assigned by using the ItemTemplate](Data-binding_images/content.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/Binding-Object)

## Different UI for TileViewItem content

You can change the various UI for the content of `TileViewItem` based on the provided logic by using the `ItemTemplateSelector`. You can also use the `ItemContainerStyleSelector` property to apply the different UI for the `TileViewItem` content.  The `DataContext` of the `ItemTemplate` property is `TileViewItem.Content`.

{% tabs %}
{% highlight C# %}

//ItemTemplateSelector class for select a DataTemplate
public class MyTemplateSelector : DataTemplateSelector {
    public DataTemplate Template1 { get; set; }
    public DataTemplate Template2 { get; set; }
    public DataTemplate Template3 { get; set; }

    public override DataTemplate SelectTemplate(object item, DependencyObject container) {
        if (item is TileItem && (item as TileItem).Header == "Item 1")
            return Template1;
        else if (item is TileItem && (item as TileItem).Header == "Item 4")
            return Template2;
        else
            return Template3;
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight XAML %}

<Window.Resources>
    <local:MyTemplateSelector x:Key="Mytemplate">
        <local:MyTemplateSelector.Template1>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Red"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template1>
        <local:MyTemplateSelector.Template2>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Blue"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template2>
        <local:MyTemplateSelector.Template3>
            <DataTemplate>
                <TextBlock Text="{Binding Content}" Foreground="Goldenrod"/>
            </DataTemplate>
        </local:MyTemplateSelector.Template3>
    </local:MyTemplateSelector>
</Window.Resources>

<Grid>
    <syncfusion:TileViewControl ItemTemplateSelector="{StaticResource Mytemplate}" 
                                ItemsSource="{Binding TileViewItems}"
                                Name="tileViewControl">
        <syncfusion:TileViewControl.ItemContainerStyle>
            <Style TargetType="syncfusion:TileViewItem">
                <Setter Property="Header" Value="{Binding Header}"/>
            </Style>
        </syncfusion:TileViewControl.ItemContainerStyle>
        <syncfusion:TileViewControl.DataContext>
            <viewmodel:ViewModel/>
        </syncfusion:TileViewControl.DataContext>
    </syncfusion:TileViewControl>
</Grid>

{% endhighlight %}
{% endtabs %}

![TileViewItem with various content UI](Data-binding_images/ItemTemplateSelector.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-tileview-control-examples/blob/master/Samples/ItemTemplate-Selector)
