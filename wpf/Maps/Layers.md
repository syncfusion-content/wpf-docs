---
layout: post
title:  Layers in Syncfusion Map control in WPF
description: This section describes the Sfmap control shapefile layer, imagery layer and shapefile layer customization in WPF platform.
platform: wpf
control: SfMap
documentation: ug
---

# Layers in syncfusion SfMap control

The maps control is maintained through [`Layers`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.MapLayer.html), a map can accommodate one or more layers.

The maps control consists the following two layers:

* Imagery layer

* Shape file layer

## Imagery layer

The [`MapsProvider`](https://help.syncfusion.com/wpf/maps/map-providers) section explains about the imagery layer.

## Shape file layer

Using shape file layer, custom shape files can be rendered and the shapes can be customized.

### Shape settings

This section defines how to customize the shapes in a map.

You can customize a shape's fill, stroke, and stroke thickness using the [`ShapeFill`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~ShapeFill.html), [`ShapeStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~ShapeStroke.html),[`ShapeStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~ShapeStrokeThickness.html) properties.

Refer to the following code sample for customizing shapes.

{% tabs %}

{% highlight xml %}

		<maps:SfMap>
            <maps:SfMap.Layers >
                <maps:ShapeFileLayer Uri="GettingStarted.ShapeFiles.usa_state.shp" >
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting  ShapeFill="LightBlue" ShapeStroke="Black" ShapeStrokeThickness="1" >
                        </maps:ShapeSetting>
                    </maps:ShapeFileLayer.ShapeSettings>
                </maps:ShapeFileLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

			SfMap maps = new SfMap();
            ShapeFileLayer shapeLayer = new ShapeFileLayer();
            shapeLayer.Uri = "GettingStarted.ShapeFiles.usa_state.shp";
            ShapeSetting shapeSetting = new ShapeSetting();
            shapeSetting.ShapeFill = new SolidColorBrush(Colors.LightBlue);
            shapeSetting.ShapeStroke = new SolidColorBrush(Colors.Black);
            shapeSetting.ShapeStrokeThickness = 1;
            shapeLayer.ShapeSettings = shapeSetting;
            maps.Layers.Add(shapeLayer);
            this.Content = maps;

{% endhighlight %}

{% endtabs %}

![Shape setting image](Layers_images/ShapeSetting_image.png)

### Customize selected shapes

The shape selection is enabled when the [`EnableSelection`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeFileLayer~EnableSelection.html) property is set to true. To customize the selected shapes alone, use the following properties:

[`SelectedShapeColor`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~SelectedShapeColor.html): Sets the color for selected shapes in a map.

[`SelectedShapeStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~SelectedShapeStroke.html): Sets the border color for selected shapes in a map.

[`SelectedShapeStrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeSetting~SelectedShapeStrokeThickness.html): Sets the border thickness for selected shapes in a map.


{% tabs %}

{% highlight xml %}

        <syncfusion:SfMap >
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer EnableSelection="True"  Uri="GettingStarted.ShapeFiles.usa_state.shp">
                    <syncfusion:ShapeFileLayer.ShapeSettings>
                        <syncfusion:ShapeSetting  SelectedShapeColor="Green" SelectedShapeStroke="Black" ShapeStrokeThickness="1" >
                        </syncfusion:ShapeSetting>
                    </syncfusion:ShapeFileLayer.ShapeSettings>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

{% highlight c# %}

            SfMap maps = new SfMap();
            ShapeFileLayer shapeLayer = new ShapeFileLayer();
            shapeLayer.EnableSelection = true;
            shapeLayer.Uri = "GettingStarted.ShapeFiles.usa_state.shp";
            ShapeSetting shapeSetting = new ShapeSetting();
            shapeSetting.SelectedShapeColor = new SolidColorBrush(Colors.Green);
            shapeSetting.SelectedShapeStroke = new SolidColorBrush(Colors.Black);
            shapeSetting.SelectedShapeStrokeThickness = 1;
            shapeLayer.ShapeSettings = shapeSetting;
            maps.Layers.Add(shapeLayer);

{% endhighlight %}

{% endtabs %}

![Selected shape setting image](Layers_images/SelectedShapeSetting_image.png)

## Appearance customization

ItemsTemplate is a type of DataTemplate that is used to override the default template for map items. “Data” is the property that holds the object for a map item.

{% tabs %}

{% highlight xaml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer Background="White" ItemsSource="{Binding Countries}" 
                                           ShapeIDPath="Name" ShapeIDTableField="NAME" 
                                           Uri="DataMarkers.ShapeFiles.world1.shp">
                    <syncfusion:ShapeFileLayer.ItemsTemplate>
                        <DataTemplate>
                            <Grid Background="#332D2D2D">
                                <TextBlock Margin="5" Foreground="White" Opacity="1" FontSize="12" 
                                           FontWeight="SemiBold" FontFamily="Segoe UI" 
                                           Text="{Binding Data.Name}"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:ShapeFileLayer.ItemsTemplate>
                    <syncfusion:ShapeFileLayer.ShapeSettings>
                        <syncfusion:ShapeSetting ShapeFill="#E5E5E5" ShapeStroke="#C1C1C1" 
                                                 ShapeStrokeThickness="0.5" ShapeValuePath="Population" 
                                                 ShapeColorValuePath="Population" >
                            <syncfusion:ShapeSetting.FillSetting>
                                <syncfusion:ShapeFillSetting AutoFillColors="False">
                                    <syncfusion:ShapeFillSetting.ColorMappings>
                                        <syncfusion:RangeColorMapping To="1500000000" From="750000000" Color="#2A91CF"/>
                                        <syncfusion:RangeColorMapping To="750000000" From="1000" Color="#3D9FD8"/>
                                        <syncfusion:RangeColorMapping From="0" To="1000" Color="#C7E9FA"/>
                                    </syncfusion:ShapeFillSetting.ColorMappings>
                                </syncfusion:ShapeFillSetting>
                            </syncfusion:ShapeSetting.FillSetting>
                        </syncfusion:ShapeSetting>
                    </syncfusion:ShapeFileLayer.ShapeSettings>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

{% highlight c# %}

    public class Country
    {
        private string name;
        public string Name
        {
            get { return name; }
            set { name = value; }
        }

        private double population;

        public double Population
        {
            get { return population; }
            set { population = value; }
        }

    }

    public class ViewModel
    {
        private ObservableCollection<Country> countries;
        public ObservableCollection<Country> Countries
        {
            get { return countries; }
            set { countries = value; }
        }

        public ViewModel()
        {
            Countries = new ObservableCollection<Country>
            {
                new Country { Name = "Russia", Population = 143228300},
                new Country { Name = "China",  Population = 1347350000 },
                new Country { Name = "Australia", Population = 22789701  },
                new Country { Name = "South Africa", Population = 50586757},
                new Country { Name = "United States", Population = 314623000 },
                new Country { Name = "Egypt", Population = 82724000},
            };
        }
    }

{% endhighlight %}

{% endtabs %}

![](Displaying-Items-on-a-Map_images/Displaying-Items-on-a-Map_img1.png)

## BaseMapIndex

[`BaseMapIndex`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.SfMap~BaseMapIndex.html) property is used to set the front layer of multiple layer defined in maps controls

{% highlight xml %}

     <syncfusion:SfMap x:Name="Map" BaseMapIndex="0">
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer  Uri="DataMarkers.ShapeFiles.world1.shp"/>
                <syncfusion:ShapeFileLayer   Uri="DataMarkers.ShapeFiles.usa_state.shp"/>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >
		
{% endhighlight %}

## Events

The [`ShapeSelected`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeFileLayer~ShapesSelected_EV.html) event will be triggered when a map shape is selected. A corresponding model data is passed as an argument.

The [`ShapesUnSelected`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeFileLayer~ShapesUnSelected_EV.html) event will be triggered when a map shape is un selected. A corresponding model data is passed as an argument.
{% tabs %}

{% highlight xml %}

		<syncfusion:SfMap >
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer EnableSelection="True"  Uri="GettingStarted.ShapeFiles.usa_state.shp"  ShapesSelected="ShapeFileLayer_ShapesSelected" ShapesUnSelected="ShapeFileLayer_ShapesUnSelected">
                 </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>
		
{% endhighlight %}

{% highlight c# %}

    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfMap maps = new SfMap();
            ShapeFileLayer shapeLayer = new ShapeFileLayer();
            shapeLayer.ShapesUnSelected += ShapeFileLayer_ShapesUnSelected;
            shapeLayer.ShapesSelected += ShapeFileLayer_ShapesSelected;
            shapeLayer.EnableSelection = true;
            shapeLayer.Uri = "GettingStarted.ShapeFiles.usa_state.shp";
            maps.Layers.Add(shapeLayer);
            this.Content = maps;
        }

        private void ShapeFileLayer_ShapesSelected(object sender, SelectionEventArgs args)
        {
            var data = args.Items;
        }

        private void ShapeFileLayer_ShapesUnSelected(object sender, SelectionEventArgs args)
        {
            var data = args.Items;
        }
    }
{% endhighlight %}

{% endtabs %}