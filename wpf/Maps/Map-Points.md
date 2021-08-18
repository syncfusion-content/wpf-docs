---
layout: post
title: Map Points in WPF Maps control | Syncfusion
description: Learn here all about Map Points support in Syncfusion WPF Maps (SfMap) control, its elements and more details.
platform: wpf
control: SfMap
documentation: ug
---

# Map Points in WPF Maps (SfMap)

Points are one of the record type in shape file layer. Points are used to specify the specific point in the map. For example, used to specify the capital of countries. Points in the shape file is given as latitude and longitude coordinates in the shapes file. Those points should be converted as MapPoints.

## Customizing the MapPoint

The default appearance of the MapPoint can be customized by using the [`MapPointTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointTemplate) property. The MapPointTemplate property is available in the ShapeFileLayer.

## About MapPointTemplate Property

`MapPointTemplate` is a DataTemplate type, used to customize or override the default template of MapPoints.

{% tabs %}
{% highlight xaml %}

     <Grid.Resources>
            <DataTemplate x:Key="itemtemplate">
                <Ellipse Height="10" Width="10" Stroke="White"      
                                                 Fill="#8AC63C"/>
            </DataTemplate>
        </Grid.Resources>

       <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer ShapeIDPath="NAME"  ShapeIDTableField="Continent"         
                                    EnableSelection="True"    
                                    Uri="DataMarkers.ShapeFiles.continent.shp" MapPointTemplate="{StaticResource itemtemplate}">
                   
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>                 

{% endhighlight %}

{% highlight c# %}

SfMap map = new SfMap();

            ShapeFileLayer shapeFileLayer = new ShapeFileLayer();
            shapeFileLayer.ShapeIDPath = "NAME";
            shapeFileLayer.ShapeIDTableField = "Continent";
            shapeFileLayer.EnableSelection = true;
            shapeFileLayer.FontSize = 14;
            shapeFileLayer.Uri = "DataMarkers.ShapeFiles.continent.shp";
            shapeFileLayer.MapPointTemplate = grid.Resources["itemTemplate"] as DataTemplate;
            map.Layers.Add(shapeFileLayer);
            this.Content = map;

{% endhighlight %}

{% endtabs %}

## MapPointIcon

[`MapPointIcon`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointIcon) is used for customizing points shapes.It can be customized by following shapes:

* Rectangle

* Circle

* Square

* Diamond

* Star

{% tabs %}

{% highlight xaml %}

  <Grid.Resources>
            <DataTemplate x:Key="pointTemplate">
                <Ellipse
                                        Width="10"
                                        Height="10"
                                        Margin="-10,-10,0,0"
                                        Fill="#8AC63C"
                                        Stroke="White" />
            </DataTemplate>
        </Grid.Resources>

     <syncfusion:SfMap x:Name="maps" Margin="10">
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer
                    EnableSelection="True"
                    Uri="WpfUG.Assets.ShapeFiles.states.shp">
                    <syncfusion:ShapeFileLayer.ShapeSettings>
                        <syncfusion:ShapeSetting 
                            ShapeStrokeThickness="1"/>
                    </syncfusion:ShapeFileLayer.ShapeSettings>
                    <syncfusion:ShapeFileLayer.SubShapeFileLayers>
                        <syncfusion:SubShapeFileLayer EnableSelection="True" Uri="WpfUG.Assets.ShapeFiles.landslide.shp"
                                                      MapPointTemplate="{StaticResource pointTemplate}">
                          
                          
                        </syncfusion:SubShapeFileLayer>
                    </syncfusion:ShapeFileLayer.SubShapeFileLayers>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>


{% endhighlight %}

{% highlight c# %}

 SfMap map = new SfMap();

            ShapeFileLayer shapeFileLayer = new ShapeFileLayer();
            
            shapeFileLayer.EnableSelection = true;
            shapeFileLayer.Uri = "WpfUG.Assets.ShapeFiles.states.shp";
            map.Layers.Add(shapeFileLayer);

            ShapeSetting setting = new ShapeSetting();
            setting.ShapeStrokeThickness = 1;
            shapeFileLayer.ShapeSettings = setting;

            SubShapeFileLayer subShapeFileLayer = new SubShapeFileLayer();
            subShapeFileLayer.EnableSelection = true;
            subShapeFileLayer.Uri = "WpfUG.Assets.ShapeFiles.landslide.shp";
            subShapeFileLayer.MapPointTemplate= grid.Resources["pointTemplate"] as DataTemplate;

            shapeFileLayer.SubShapeFileLayers.Add(subShapeFileLayer);
             this.Content = map;

{% endhighlight %}

{% endtabs %}

![Map Points icon image in WPF SfMap](Map-Points_images/Map_Points_Icon_image.png)

## MapPointPopup

MapPointPopup is a popup, displayed when the point is moved to MapPoint. It shows additional information from the object bounded with the MapPoint. You can get the object from dbf file.

### MapPointPopupTemplate

[`MapPointPopupTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointPopupTemplate) is a DataTemplate, used to expose the template for the MapPoint. 

{% tabs %}
{% highlight xaml %}

 <Grid.Resources>

         <DataTemplate x:Key="pointTemplate">
                <Ellipse
                                        Width="10"
                                        Height="10"
                                        Margin="-10,-10,0,0"
                                        Fill="#8AC63C"
                                        Stroke="White" />
            </DataTemplate>
            <DataTemplate x:Key="popupTemplate">
                <Border
                                        Height="110"
                                        Background="#FF252525"
                                        BorderThickness="0.5"
                                        Opacity="0.9">
                    <StackPanel Margin="10,5,20,0">
                        <StackPanel>
                            <TextBlock
                                                    Margin="10,5,0,0"
                                                    FontFamily="Segoe UI"
                                                    FontSize="20"
                                                    Foreground="White"
                                                    Text="Landslide Event in USA" />
                        </StackPanel>
                        <Grid Margin="10,5,10,0">
                            <Rectangle
                                                    Height="2"
                                                    VerticalAlignment="Center"
                                                    Stroke="#FF505050"
                                                    StrokeDashArray="6 2" />
                        </Grid>
                        <Grid Margin="10,5,0,0">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="0.41*" />
                                <ColumnDefinition Width="0.1*" />
                                <ColumnDefinition Width="0.49*" />
                            </Grid.ColumnDefinitions>
                            <Grid.RowDefinitions>
                                <RowDefinition />
                                <RowDefinition />
                            </Grid.RowDefinitions>
                            <TextBlock
                                                    Grid.Row="0"
                                                    Grid.Column="0"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text="Location" />
                            <TextBlock
                                                    Grid.Row="0"
                                                    Grid.Column="1"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text=" : " />
                            <TextBlock
                                                    Grid.Row="0"
                                                    Grid.Column="2"
                                                    Margin="5,0,0,0"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text="{Binding [LOCALITY]}" />
                            <TextBlock
                                                    Grid.Row="1"
                                                    Grid.Column="0"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text="Year" />
                            <TextBlock
                                                    Grid.Row="1"
                                                    Grid.Column="1"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text=" : " />
                            <TextBlock
                                                    Grid.Row="1"
                                                    Grid.Column="2"
                                                    Margin="5,0,0,0"
                                                    FontFamily="Segoe UI"
                                                    FontSize="18"
                                                    FontWeight="Normal"
                                                    Foreground="#FFACACAC"
                                                    Text="{Binding [YEAR]}" />
                        </Grid>
                    </StackPanel>
                </Border>
            </DataTemplate>
           
        </Grid.Resources>

     <syncfusion:SfMap x:Name="maps" Margin="10">
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer
                    EnableSelection="True"
                    Uri="WpfUG.Assets.ShapeFiles.states.shp">
                    <syncfusion:ShapeFileLayer.ShapeSettings>
                        <syncfusion:ShapeSetting 
                            ShapeStrokeThickness="1"/>
                    </syncfusion:ShapeFileLayer.ShapeSettings>
                    <syncfusion:ShapeFileLayer.SubShapeFileLayers>
                        <syncfusion:SubShapeFileLayer EnableSelection="True" Uri="WpfUG.Assets.ShapeFiles.landslide.shp"  MapPointTemplate="{StaticResource pointTemplate}"
                        MapPointPopupTemplate ="{StaticResource popupTemplate}">
                           
                                                   </syncfusion:SubShapeFileLayer>
                    </syncfusion:ShapeFileLayer.SubShapeFileLayers>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

{% highlight c# %}

 SfMap map = new SfMap();

            ShapeFileLayer shapeFileLayer = new ShapeFileLayer();
            
            shapeFileLayer.EnableSelection = true;
            shapeFileLayer.Uri = "WpfUG.Assets.ShapeFiles.states.shp";
            map.Layers.Add(shapeFileLayer);

            ShapeSetting setting = new ShapeSetting();
            setting.ShapeStrokeThickness = 1;
            shapeFileLayer.ShapeSettings = setting;

            SubShapeFileLayer subShapeFileLayer = new SubShapeFileLayer();
            subShapeFileLayer.EnableSelection = true;
            subShapeFileLayer.Uri = "WpfUG.Assets.ShapeFiles.landslide.shp";
            subShapeFileLayer.MapPointTemplate= grid.Resources["pointTemplate"] as DataTemplate;
            subShapeFileLayer.MapPointPopupTemplate = grid.Resources["popupTemplate"] as DataTemplate;

            shapeFileLayer.SubShapeFileLayers.Add(subShapeFileLayer);
             this.Content = map;

{% endhighlight %}

{% endtabs %}

![Map Points and popup image in WPF SfMap](Map-Points_images/Map_Points_Popup_image.png)

N> You can refer to our [WPF Map](https://www.syncfusion.com/wpf-controls/map) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Map example](https://github.com/syncfusion/wpf-demos/tree/master/map) to know how to render and configure the map.
