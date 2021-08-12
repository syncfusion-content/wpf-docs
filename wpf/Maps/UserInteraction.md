---
layout: post
title: User interaction in WPF Maps control | Syncfusion
description: Learn here all about user interaction support such as tooltip, zooming and panning in Syncfusion WPF Maps (SfMap) control, its elements.
platform: wpf
control: SfMap
documentation: ug
---

# Tooltip in WPF Maps (SfMap)

Tooltip provides additional information about the shapes in the maps. To enable tooltip, set the [`ToolTipSettings`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_ToolTipSettings) property in the [`ShapeFileLayer`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html) and set the [`ValuePath`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_ValuePath) property of [`ToolTipSetting`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html).

Tooltip is displayed by tapping the following elements:
• Shapes
• Bubbles
• Markers

## Tooltip for Shapes

{% tabs %}

{% highlight xaml %}

        <maps:SfMap >
            <maps:SfMap.Layers>
                <maps:ShapeFileLayer Uri="/WpfUG;component/Assets/ShapeFiles/usa_state.shp" 
                                     ItemsSource="{Binding Data}" ShapeIDPath="State" 
                                     ShapeIDTableField="STATE_NAME" EnableSelection="False"
                                     LabelPath="State" >
                    <maps:ShapeFileLayer.ShapeSettings>
                        <maps:ShapeSetting   ShapeStrokeThickness="1" ></maps:ShapeSetting>
                    </maps:ShapeFileLayer.ShapeSettings>
                    <maps:ShapeFileLayer.ToolTipSettings>
                        <maps:ToolTipSetting  ValuePath="Candidate" x:Name="shapeTooltipSettings" >
                        </maps:ToolTipSetting>
                    </maps:ShapeFileLayer.ToolTipSettings>
                    <maps:ShapeFileLayer.ItemsTemplate>
                        <DataTemplate>
                            <Border >
                                <TextBlock FontFamily="Segoe UI" FontSize="12" Foreground="#FF333333" Text=""/>
                            </Border>
                        </DataTemplate>
                    </maps:ShapeFileLayer.ItemsTemplate>
                </maps:ShapeFileLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

     public class ElectionData
    {
        public ElectionData(string state, string candidate, int electors)
        {
            State = state;
            Candidate = candidate;
            Electors = electors;
        }

        public string State
        {
            get;
            set;
        }

        public string Candidate
        {
            get;
            set;
        }

        public int Electors
        {
            get;
            set;
        }
    }
	
	 public class ViewModel
    { 
        public ObservableCollection<ElectionData> Data { get; set; }
        public ViewModel()
        {
            Data = new ObservableCollection<ElectionData>();
            Data.Add(new ElectionData("Alabama", "Romney", 9));
            Data.Add(new ElectionData("Alaska", "Romney", 3));
            Data.Add(new ElectionData("Arizona", "Romney", 11));
            Data.Add(new ElectionData("Arkansas", "Romney", 6));
            Data.Add(new ElectionData("California", "Romney", 55));
            Data.Add(new ElectionData("Colorado", "Obama", 9));
            Data.Add(new ElectionData("Connecticut", "Obama", 7));
            Data.Add(new ElectionData("Delaware", "Obama", 3));
            Data.Add(new ElectionData("District of Columbia", "Obama", 3));
            Data.Add(new ElectionData("Florida", "Obama", 29));
            Data.Add(new ElectionData("Georgia", "Obama", 16));
            Data.Add(new ElectionData("Hawaii", "Romney", 4));
            Data.Add(new ElectionData("Idaho", "Obama", 4));
            Data.Add(new ElectionData("Illinois", "Romney", 20));
            Data.Add(new ElectionData("Indiana", "Obama", 11));
            Data.Add(new ElectionData("Iowa", "Romney", 6));
            Data.Add(new ElectionData("Kansas", "Obama", 6));
            Data.Add(new ElectionData("Kentucky", "Romney", 8));
            Data.Add(new ElectionData("Louisiana", "Romney", 8));
            Data.Add(new ElectionData("Maine", "Romney", 4));
            Data.Add(new ElectionData("Maryland", "Obama", 10));
        }
    }

{% endhighlight %}

{% endtabs %}

![WPF SfMaps marker tooltip image](Tooltip_images/Shapes_Tooltip.png)

### Tooltip customization

The appearance of the tooltip can be customized using the following properties:

[`Foreground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_Foreground) : Customizes the text color of tooltip.
[`Background`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_Background) : Customizes the background color of tooltip.
[`Stroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_Stroke) : Customizes the stroke color of tooltip.
[`StrokeThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_StrokeThickness) : Customizes the stroke width of tooltip.
[`ShowDuration`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_ShowDuration) : Specifies the duration of tooltip to be displayed.
[`Margin`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_Margin) : Sets the margin for tooltip.
[`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_FontFamily) : Customizes the text font family of tooltip.
[`FontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_FontStyle) : Customizes the font style of tooltip text.
[`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_FontSize) : Customizes the font size of tooltip text.
[`PointerLength`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ToolTipSetting.html#Syncfusion_UI_Xaml_Maps_ToolTipSetting_PointerLength) : Customizes the tooltip pointer length.

The following code sample shows all the above customizations.

{% tabs %}

{% highlight xaml %}

     <maps:ShapeFileLayer.ToolTipSettings>
         <maps:ToolTipSetting ValuePath="State" PointerLength="18" FontFamily="Segoe UI" FontStyle="Italic" FontSize="20" Foreground="White" Margin="10" Background="Green"  Stroke="Black" StrokeThickness="2" ShowDuration="2000" />
     </maps:ShapeFileLayer.ToolTipSettings>

{% endhighlight %}

{% highlight c# %}

            shapeFileLayer.ToolTipSettings.Background = new SolidColorBrush(Colors.White);
            shapeFileLayer.ToolTipSettings.Background = new SolidColorBrush(Colors.Green);
            shapeFileLayer.ToolTipSettings.Stroke = new SolidColorBrush(Colors.Black);
            shapeFileLayer.ToolTipSettings.StrokeThickness = 2;
            shapeFileLayer.ToolTipSettings.Margin = new Thickness(10);
            shapeFileLayer.ToolTipSettings.ShowDuration = 2000;
            shapeFileLayer.ToolTipSettings.FontSize = 20;
            shapeFileLayer.ToolTipSettings.FontStyle = FontStyles.Italic;
            shapeFileLayer.ToolTipSettings.FontFamily = new FontFamily("Segoe UI");
			shapeFileLayer.ToolTipSettings.PointerLength = 18;

{% endhighlight %}

{% endtabs %}

N> Similarly we can customize the bubble and marker tooltip also.

![WPF SfMaps marker tooltip image](Tooltip_images/Tooltip_Customization.png)

### Custom template for tooltip

The maps control provides options to design your own template for tooltip using the TooltipTemplate property.

{% tabs %}

{% highlight xaml %}

        <Grid x:Name="grid">
            <Grid.Resources>
                <DataTemplate x:Key="toolTipTemplate">
                    <TextBlock Foreground="Yellow" Text="{Binding Data.Candidate}"/>
                </DataTemplate>
            </Grid.Resources>
			
            <maps:ShapeFileLayer.ToolTipSettings>
                <maps:ToolTipSetting ShowDuration="3000" ToolTipTemplate="{StaticResource ResourceKey=toolTipTemplate}"/>
            </maps:ShapeFileLayer.ToolTipSettings>
	    </Grid>

{% endhighlight %}

{% highlight c# %}

            ToolTipSetting toolTipSetting = new ToolTipSetting();
            toolTipSetting.ShowDuration = 3000;
            DataTemplate template = this.grid.Resources["toolTipTemplate"] as DataTemplate;
            toolTipSetting.ToolTipTemplate = template;
            shapeFile.ToolTipSettings = toolTipSetting;

{% endhighlight %}

{% endtabs %}

![Tooltip Custom Template Image](Tooltip_images/Custom_Template.png)

## Tooltip for Bubbles

{% tabs %}

{% highlight xaml %}

       <maps:SfMap x:Name="map">
            <maps:SfMap.Layers>
                <maps:ShapeFileLayer Uri="/WpfUG;component/Assets/ShapeFiles/usa_state.shp"  ItemsSource="{Binding Data}" ShapeIDPath="State" ShapeIDTableField="STATE_NAME" EnableSelection="False" LabelPath="State">
                    <maps:ShapeFileLayer.ItemsTemplate>
                        <DataTemplate>
                            <Border >
                                <TextBlock FontFamily="Segoe UI" FontSize="12" Foreground="#FF333333"  Text=""/>
                            </Border>
                        </DataTemplate>
                    </maps:ShapeFileLayer.ItemsTemplate>

                    <maps:ShapeFileLayer.BubbleMarkerSetting>
                        <maps:BubbleMarkerSetting  MinSize="20" MaxSize="50" ValuePath="Electors"  ColorValuePath="Electors" Stroke="Black" StrokeThickness="3">
                            <maps:BubbleMarkerSetting.ToolTipSettings >
                                <maps:ToolTipSetting  ValuePath="Electors">
                                </maps:ToolTipSetting>
                            </maps:BubbleMarkerSetting.ToolTipSettings>
                            <maps:BubbleMarkerSetting.ColorMappings>
                                <maps:RangeColorMapping Color="#7F20BCEE" To="0" From="10"/>
                                <maps:RangeColorMapping Color="#7FA7CE38" To="10" From="20"/>
                                <maps:RangeColorMapping Color="#7FF1B21A" To="20" From="30"/>
                                <maps:RangeColorMapping Color="#7F1DA249" To="30" From="40"/>
                                <maps:RangeColorMapping Color="#7FEB737C" To="40" From="50"/>
                                <maps:RangeColorMapping Color="#7FED2D95" To="50" From="60"/>
                            </maps:BubbleMarkerSetting.ColorMappings>
                        </maps:BubbleMarkerSetting>
                    </maps:ShapeFileLayer.BubbleMarkerSetting>
                </maps:ShapeFileLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

     public class ElectionData
    {
        public ElectionData(string state, string candidate, int electors)
        {
            State = state;
            Candidate = candidate;
            Electors = electors;
        }

        public string State
        {
            get;
            set;
        }

        public string Candidate
        {
            get;
            set;
        }

        public int Electors
        {
            get;
            set;
        }
    }
	
	 public class ViewModel
    { 
        public ObservableCollection<ElectionData> Data { get; set; }
        public ViewModel()
        {
            Data = new ObservableCollection<ElectionData>();
            Data.Add(new ElectionData("Alabama", "Romney", 9));
            Data.Add(new ElectionData("Alaska", "Romney", 3));
            Data.Add(new ElectionData("Arizona", "Romney", 11));
            Data.Add(new ElectionData("Arkansas", "Romney", 6));
            Data.Add(new ElectionData("California", "Romney", 55));
            Data.Add(new ElectionData("Colorado", "Obama", 9));
            Data.Add(new ElectionData("Connecticut", "Obama", 7));
            Data.Add(new ElectionData("Delaware", "Obama", 3));
            Data.Add(new ElectionData("District of Columbia", "Obama", 3));
            Data.Add(new ElectionData("Florida", "Obama", 29));
            Data.Add(new ElectionData("Georgia", "Obama", 16));
            Data.Add(new ElectionData("Hawaii", "Romney", 4));
            Data.Add(new ElectionData("Idaho", "Obama", 4));
            Data.Add(new ElectionData("Illinois", "Romney", 20));
            Data.Add(new ElectionData("Indiana", "Obama", 11));
            Data.Add(new ElectionData("Iowa", "Romney", 6));
            Data.Add(new ElectionData("Kansas", "Obama", 6));
            Data.Add(new ElectionData("Kentucky", "Romney", 8));
            Data.Add(new ElectionData("Louisiana", "Romney", 8));
            Data.Add(new ElectionData("Maine", "Romney", 4));
            Data.Add(new ElectionData("Maryland", "Obama", 10));
        }
    }

{% endhighlight %}

{% endtabs %}

![WPF SfMaps marker tooltip image](Tooltip_images/Bubble_Tooltip.png)

## Tooltip for Markers
{% tabs %}

{% highlight xaml %}

    <maps:SfMap>
        <maps:SfMap.Layers>
            <maps:ShapeFileLayer Uri="MapsZoom.ShapeFiles.usa_state.shp" Markers="{Binding Models}" >
                <maps:ShapeFileLayer.ItemsTemplate>
                    <DataTemplate>
                        <Border >
                            <TextBlock FontFamily="Segoe UI" FontSize="12" Foreground="#FF333333"  Text=""/>
                        </Border>
                    </DataTemplate>
                </maps:ShapeFileLayer.ItemsTemplate>
                <maps:ShapeFileLayer.MarkerToolTipSettings>
                    <maps:ToolTipSetting  ValuePath="Name"></maps:ToolTipSetting>
                </maps:ShapeFileLayer.MarkerToolTipSettings>
                <maps:ShapeFileLayer.MarkerTemplate>
                    <DataTemplate>
                        <Grid Margin="-12,-30,0,0">
                            <Canvas>
                                <Image Source="pin.png" Height="30"/>
                            </Canvas>
                        </Grid>
                    </DataTemplate>
                </maps:ShapeFileLayer.MarkerTemplate>
            </maps:ShapeFileLayer>
        </maps:SfMap.Layers>
    </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

   public class ViewModel
    { 
        public ObservableCollection<Model> Models { get; set; }
        public ViewModel()
        {
            this.Models = new ObservableCollection<Model>();
            this.Models.Add(new Model() { Name = "USA ", Latitude = "38.8833N", Longitude = "77.0167W" });
            this.Models.Add(new Model() { Name = "Texas ", Latitude = "31.9686N", Longitude = "99.9018W" });
            this.Models.Add(new Model() { Name = "Colorado ", Latitude = "39.5501N", Longitude = "105.7821W" });
            this.Models.Add(new Model() { Name = "New York ", Latitude = "40.7128N", Longitude = "74.0060W" });
            this.Models.Add(new Model() { Name = "Alabama ", Latitude = "32.3182N", Longitude = "86.9023W" });
            this.Models.Add(new Model() { Name = "Nevada ", Latitude = "36.8797N", Longitude = " 115.3626W" });
        }
    }
	
	public class Model
    {
        public string Name { get; set; }
        public string Longitude { get; set; }
        public string Latitude { get; set; }
    }

{% endhighlight %}

{% endtabs %}

![WPF SfMaps marker tooltip image](Tooltip_images/MarkerTooltip.png)

## Tooltip for Markers in imagery layer

{% tabs %}

{% highlight xaml %}

     <maps:SfMap>
            <maps:SfMap.Layers>               
                 <maps:ImageryLayer LayerType="OSM" Markers="{Binding Models}" >
                    <maps:ImageryLayer.MarkerToolTipSettings>
                        <maps:ToolTipSetting ValuePath="Name" PointerLength="18" FontFamily="Segoe UI" FontStyle="Italic" FontSize="20" Foreground="White" Margin="10" Background="Green"  Stroke="Black" StrokeThickness="2" ShowDuration="2000">
                            <maps:ToolTipSetting.ToolTipTemplate>
                                <DataTemplate>
                                    <TextBlock  Foreground="White" Text="{Binding Value}"></TextBlock>
                                </DataTemplate>
                            </maps:ToolTipSetting.ToolTipTemplate>
                        </maps:ToolTipSetting>
                    </maps:ImageryLayer.MarkerToolTipSettings>
                    <maps:ImageryLayer.MarkerTemplate>
                        <DataTemplate>
                            <Grid Margin="-12,-30,0,0">
                                <Canvas>
                                    <Image Source="pin.png" Height="30"/>
                                </Canvas>
                            </Grid>
                        </DataTemplate>
                    </maps:ImageryLayer.MarkerTemplate>
                </maps:ImageryLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

   public class ViewModel
    { 
        public ObservableCollection<Model> Models { get; set; }
        public ViewModel()
        {
            this.Models = new ObservableCollection<Model>();
            this.Models.Add(new Model() { Name = "USA ", Latitude = "38.8833N", Longitude = "77.0167W" });
            this.Models.Add(new Model() { Name = "Brazil ", Latitude = "15.7833S", Longitude = "47.8667W" });
            this.Models.Add(new Model() { Name = "India ", Latitude = "21.0000N", Longitude = "78.0000E" });
            this.Models.Add(new Model() { Name = "China ", Latitude = "35.0000N", Longitude = "103.0000E" });
            this.Models.Add(new Model() { Name = "Indonesia ", Latitude = "6.1750S", Longitude = "106.8283E" });
       }
    }
	
	public class Model
    {
        public string Name { get; set; }
        public string Longitude { get; set; }
        public string Latitude { get; set; }
    }

{% endhighlight %}

{% endtabs %}

![WPF SfMaps marker tooltip image](Tooltip_images/ImageryLayer_Tooltip.png)

# Zooming and Panning

The Zooming and Panning feature of the Maps control allows you to zoom in and out and navigate the map.

## Zooming

The zooming feature enables you to zoom in and out of the map to show in-depth information. It is controlled by the [`ZoomLevel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_ZoomLevel) property of the map. When the zoom level of the Map control is increased, the map is zoomed in. When the zoom level is decreased, then the map is zoomed out.

### Properties Related to Zooming

The following properties are related to the zooming feature of the Maps control:

1. ZoomLevel
2. EnableZoom
3. MinZoom
4. MaxZoom

#### ZoomLevel

[`ZoomLevel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_ZoomLevel) is the primary property of the zooming feature. It controls the map’s scale size while zooming. Initially, the zoom level is 1. ZoomLevel cannot be less than 1.

#### EnableZoom

The [`EnableZoom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_EnableZoom) property enables or disables the zooming feature. A `True` value of this property enables the zooming feature and `False` disables the zooming feature.

#### MinZoom

The [`MinZoom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_MinZoom) property is used to set the minimum zoom level of the map. 

####  MaxZoom

The [`MaxZoom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_MaxZoom) property is used to set the maximum zoom level of the Map control.

Sample code for setting zooming feature properties:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfMap ZoomLevel="3" MinZoom="1" MaxZoom="20" EnableZoom="True">                

</syncfusion:SfMap >

{% endhighlight %}

{% highlight c# %}

            SfMap maps = new SfMap();
            maps.ZoomLevel = 3;
            maps.MinZoom = 1;
            maps.MaxZoom = 20;
            maps.EnableZoom = true;
            this.Content = maps;

{% endhighlight %}

{% endtabs %}

## Zooming in ShapeFileLayer 

### Methods to Zoom the Map

Maps can be zoomed by using the following methods:

1. By changing the ZoomLevel.
2. Through the Zoom method.
3. Through the mouse scroll.

#### Changing the ZoomLevel

A map can be zoomed by changing the zoom level of the Map control. Incrementing the ZoomLevel, zooms in the map and decrementing the ZoomLevel, zooms out the map.

#### Through the Zoom method

Maps can be zoomed through the [`Zoom`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_Zoom_System_Double_) method. The Zoom method has the parameter zoom value. The map can be zoomed or scaled with the zoom value parameter.

{% highlight C# %}

   SfMap syncMap = new SfMap();

   ShapeFileLayer shapeLayer = new ShapeFileLayer();

   shapeLayer.Uri = "MapApp.ShapeFiles.world1.shp";

   syncMap.Layers.Add(shapeLayer);

   syncMap.Zoom(5);

{% endhighlight %}

#### Through a mouse wheel event

In addition to the pinching event, the map can be zoomed with mouse events.  When the mouse is scrolled up, the map is zoomed in. When the mouse is scrolled down, the map is zoomed out.

![Maps controls Zooming and Padding](Zooming-and-Panning_images/Zooming-and-Panning_img1.png)

## Panning the map

The panning feature enables navigation through the map.

Properties related to Panning are:

* EnablePan

#### Enable and disable pan

The [`EnablePan`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_EnablePan) property enables or disables the panning feature of the map. A `True` value enables the panning feature. A `False` value disables the panning feature of the map.

{% highlight xaml %}

       <syncfusion:SfMap ShowCoords="True" LatitudeLongitudeType="Decimal" EnablePan="True">         
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer   Uri="MapApp.world1.shp">                    
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap >

{% endhighlight %}

### Ways to pan the map

There are two methods for panning the map. They are:

1. Through the Pan method.
2. By dragging the map.

#### Through the Pan method

The map can be panned with the [`Pan`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.SfMap.html#Syncfusion_UI_Xaml_Maps_SfMap_Pan_System_Double_System_Double_) method in the Maps control. The Pan method has two parameters: x and y.  The map is translated with respect to the x and y parameters.

##### Code sample for the Pan method:

{% highlight C# %}

           SfMap syncMap = new SfMap();

            syncMap.EnablePan = true;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "App2.world1.shp";

            syncMap.Layers.Add(layer);

            syncMap.Pan(200, 200);
{% endhighlight %}


#### Dragging the map

The map can be panned by dragging the map through mouse interactions. This works automatically for touch events.

N> The map can be panned only when some parts of the map are outside the view of the control.

![Maps controls Zooming and Panning](Zooming-and-Panning_images/Zooming-and-Panning_img2.png)

## Zooming in ImageryLayer

### Calculate a zoom level

This feature allows you to set the initial zoom level automatically in two ways:

* Distance Radius(KM/miles)
* Geo-bounds(Northeast, Southwest)

### Distance Radius 

N> DistanceType default value is KiloMeter.

Calculate the initial zoom level automatically based on the [`Radius`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ImageryLayer.html#Syncfusion_UI_Xaml_Maps_ImageryLayer_Radius) and [`DistanceType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ImageryLayer.html#Syncfusion_UI_Xaml_Maps_ImageryLayer_DistanceType) properties of ImageryLayer.

* [`Center`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ImageryLayer.html#Syncfusion_UI_Xaml_Maps_ImageryLayer_Center) - Represents center point of ImageryLayer.  

{% tabs %}

{% highlight xaml %}

      <Window.Resources>
        <ResourceDictionary >
            <DataTemplate x:Key="markerTemplate">
                <Grid Margin="-12,-30,0,0">
                    <Canvas>
                        <Image Source="pin.png" Height="30"/>
                    </Canvas>
                </Grid>
            </DataTemplate>
        </ResourceDictionary>
    </Window.Resources>
	
    <Grid>
        <maps:SfMap>
            <maps:SfMap.Layers>
                <maps:ImageryLayer MarkerTemplate="{StaticResource ResourceKey=markerTemplate}" Markers="{Binding Models}" Center="38.909804, -77.043442" Radius="5" DistanceType="KiloMeter" >
                </maps:ImageryLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>
    </Grid>

{% endhighlight %}

{% highlight c# %}

            SfMap maps = new SfMap();
            ImageryLayer layer = new ImageryLayer();
            layer.Center = new Point(38.909804, -77.043442);
            layer.Radius = 5;
            layer.DistanceType = DistanceType.KiloMeter;
            layer.Markers = obj.Models;
            layer.MarkerTemplate = this.Resources["markerTemplate"] as DataTemplate;
            maps.Layers.Add(layer);
			
	  public class Model
      {
        public string Longitude { get; set; }
        public string Latitude { get; set; }
      }
			
	   public class ViewModel
       {
          public ObservableCollection<Model> Models { get; set; }
          public ViewModel()
          {
            this.Models = new ObservableCollection<Model>();
            this.Models.Add(new Model() { Latitude = "38.909804", Longitude = "-77.043442" });
         }
      }

{% endhighlight %}

{% endtabs %}

### Geo-bounds

Calculate the initial zoom level automatically based on the [`LatLngBounds`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ImageryLayer.html#Syncfusion_UI_Xaml_Maps_ImageryLayer_LatLngBounds) of ImageryLayer.

{% tabs %}

{% highlight xaml %}

        <Window.Resources>
        <ResourceDictionary >
            <DataTemplate x:Key="markerTemplate">
                <Grid Margin="-12,-30,0,0">
                    <Canvas>
                        <Image Source="pin.png" Height="30"/>
                    </Canvas>
                </Grid>
            </DataTemplate>
        </ResourceDictionary>
    </Window.Resources>
    <Grid>
        <maps:SfMap>
            <maps:SfMap.Layers>
                <maps:ImageryLayer LayerType="OSM" MarkerTemplate="{StaticResource ResourceKey=markerTemplate}"  Markers="{Binding Models}"  >
                    <maps:ImageryLayer.LatLngBounds>
                        <maps:LatLngBounds Northeast="38.909804, -77.043442" Southwest="38.909804, -77.043442" >
                        </maps:LatLngBounds>
                    </maps:ImageryLayer.LatLngBounds>
                </maps:ImageryLayer>
            </maps:SfMap.Layers>
        </maps:SfMap>
    </Grid>

{% endhighlight %}

{% highlight c# %}

            SfMap maps = new SfMap();
            ImageryLayer layer = new ImageryLayer();
            LatLngBounds bounds = new LatLngBounds();
            bounds.Northeast = new Point(38.909804, -77.043442);
            bounds.Southwest = new Point(38.909804, -77.043442);
            layer.LatLngBounds = bounds;
            layer.Markers = obj.Models;
            layer.MarkerTemplate = this.Resources["markerTemplate"] as DataTemplate;
            maps.Layers.Add(layer);
			
	  public class Model
      {
        public string Longitude { get; set; }
        public string Latitude { get; set; }
      }
			
	   public class ViewModel
       {
          public ObservableCollection<Model> Models { get; set; }
          public ViewModel()
          {
            this.Models = new ObservableCollection<Model>();
            this.Models.Add(new Model() { Latitude = "38.909804", Longitude = "-77.043442" });
         }
      }

{% endhighlight %}

{% endtabs %}

N> When setting LatLngBounds and DistanceRadius at the same time, the priority is DistanceRadius, and calculate zoom level based on Radius value.

![WPF SfMaps zoom level changed image](Map-Providers_images/Zoom_Level.jpg)

### Calculate the map tile layer bounds

Calculate the imagery layer pixel bounds while zooming, panning, and Geo-Coordinate value changing.

{% tabs %}

{% highlight xaml %}

      <maps:SfMap>
            <maps:SfMap.Layers>
                <maps:ImageryLayer x:Name="layer"  Center="30.9709225, -100.2187212" CenterChanged="layer_CenterChanged">
                </maps:ImageryLayer>
            </maps:SfMap.Layers>
      </maps:SfMap>

{% endhighlight %}

{% highlight c# %}

    public partial class MapBound : ContentPage
    {
        ImageryLayer layer = new ImageryLayer();
        public MapBound()
        {
            InitializeComponent();
            SfMap maps = new SfMap();
            layer.Center = new Point(30.9709225, -100.2187212);
            layer.CenterChanged += layer_CenterChanged;
            maps.Layers.Add(layer);
            this.Content = maps;
        }
        private void layer_CenterChanged(object sender, CenterChangedEventArgs e)
        {
            var pixelbounds = layer.MapBounds;
        }
    }

{% endhighlight %}

{% endtabs %}

### Pinch zooming in ImageryLayer

If you want to zoom the imagery layer using fingers by touch, then you have to enable `EnableZoom` and `IsManipulationEnabled` property of map control.

{% tabs %}

{% highlight xaml %}

    <Window.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="markerTemplate">
                <Grid>
                    <Canvas Margin="-12,-30,0,0">
                        <Image Source="pin.png" Height="30" />
                        <TextBlock HorizontalAlignment="Center" Margin="0,30,0,0" FontSize="20" FontFamily="Segoe UI" Text="{Binding Label}"/>
                    </Canvas>
                </Grid>
            </DataTemplate>
        </ResourceDictionary>
    </Window.Resources>
    <Grid>
        <Grid>
            <syncfusion:SfMap ZoomLevel="3" IsManipulationEnabled="True" EnableZoom="True">
                <syncfusion:SfMap.Layers>
                    <syncfusion:ImageryLayer  Markers="{Binding Models}" MarkerTemplate="{StaticResource markerTemplate}">
                    </syncfusion:ImageryLayer>
                </syncfusion:SfMap.Layers>
            </syncfusion:SfMap>
        </Grid>

{% endhighlight %}

{% highlight c# %}

            SfMap maps = new SfMap();
            ImageryLayer layer = new ImageryLayer();
            layer.Markers = view.Models;
            maps.ZoomLevel = 3;
            layer.MarkerTemplate = Resources["markerTemplate"] as DataTemplate;
            maps.IsManipulationEnabled = true;
            maps.EnableZoom = true;
            maps.Layers.Add(layer);
            this.Content = maps;
			
    public class ViewModel
    {
        public ObservableCollection<Model> Models { get; set; }
        public ViewModel()
        {
            this.Models = new ObservableCollection<Model>();
            this.Models.Add(new Model() { Label = "USA", Latitude = "38.8833N", Longitude = "77.0167W" });
            this.Models.Add(new Model() { Label = "Brazil ", Latitude = "15.7833S", Longitude = "47.8667W" });
            this.Models.Add(new Model() { Label = "India ", Latitude = "21.0000N", Longitude = "78.0000E" });
            this.Models.Add(new Model() { Label = "China ", Latitude = "35.0000N", Longitude = "103.0000E" });
            this.Models.Add(new Model() { Label = "Indonesia ", Latitude = "6.1750S", Longitude = "106.8283E" });
        }
    }

    public class Model
    {
        public string Label { get; set; }
        public string Longitude { get; set; }
        public string Latitude { get; set; }
    }

{% endhighlight %}

{% endtabs %}

![WPF SfMaps pinch zoom image](Map-Providers_images/Marker_PinchZooming.gif)

You can able to cancel the pinch zooming in ImageryLayer by setting [`Cancel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ZoomLevelChangingEventArgs.html#Syncfusion_UI_Xaml_Maps_ZoomLevelChangingEventArgs_Cancel) property as true in [`ZoomLevelChanging`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ImageryLayer.html) event argument as per the below code snippet. 

{% tabs %}

{% highlight xaml %}

       <syncfusion:SfMap EnableZoom="True" IsManipulationEnabled="True">
            <syncfusion:SfMap.Layers>
                <syncfusion:ImageryLayer Markers="{Binding Models}"
                                        ZoomLevelChanging="ImageryLayer_ZoomLevelChanging"/>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

{% highlight c# %}

        private void ImageryLayer_ZoomLevelChanging(object sender, ZoomLevelChangingEventArgs e)
        {
            e.Cancel = true;
        }
          
{% endhighlight %}

{% endtabs %}

N> You can refer to our [WPF Map](https://www.syncfusion.com/wpf-controls/map) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Map example](https://github.com/syncfusion/wpf-demos/tree/master/map) to know how to render and configure the map.
