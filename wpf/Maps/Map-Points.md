---
layout: post
title: Map Points | SfMap | wpf | Syncfusion
description: This section describes customizing the MapPoint, about MapPointTemplate, MapPointPopupTemplate in WPF SfMaps control
platform: wpf
control: SfMap
documentation: ug
---

# Map Points support in SfMap

Points are one of the record type in shape file layer. Points are used to specify the specific point in the map. For example, used to specify the capital of countries. Points in the shape file is given as latitude and longitude coordinates in the shapes file. Those points should be converted as MapPoints.

## Customizing the MapPoint

The default appearance of the MapPoint can be customized by using the [`MapPointTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointTemplate) property. The MapPointTemplate property is available in the ShapeFileLayer.

## About MapPointTemplate Property

`MapPointTemplate` is a DataTemplate type, used to customize or override the default template of MapPoints.

{% highlight xaml %}

       <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer ShapeIDPath="NAME"  ShapeIDTableField="Continent"                                                         
                                    EnableSelection="True"                                                                                                                  
                                    Uri="DataMarkers.ShapeFiles.continent.shp">
                    <syncfusion:ShapeFileLayer.MapPointTemplate>
                        <DataTemplate>
                            <Ellipse Height="10" Width="10" Stroke="White"      
                                                 Fill="#8AC63C"/>
                        </DataTemplate>
                    </syncfusion:ShapeFileLayer.MapPointTemplate>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>                   

{% endhighlight %}

## MapPointIcon

[`MapPointIcon`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointIcon) is used for customizing points shapes.It can be customized by following shapes:

* Rectangle

* Circle

* Square

* Diamond

* Star

{% highlight xaml %}

    <syncfusion:SfMap x:Name="maps">
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer Background="White" Uri="MapPoints.ShapeFiles.states.shp">
                    <syncfusion:ShapeFileLayer.SubShapeFileLayers>
                        <syncfusion:SubShapeFileLayer MapPointMargin="20" MapPointIcon="Diamond" Uri="MapPoints.ShapeFiles.landslide.shp">
                        </syncfusion:SubShapeFileLayer>
                    </syncfusion:ShapeFileLayer.SubShapeFileLayers>
                </syncfusion:ShapeFileLayer>
          </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

![Map Points icon image in WPF SfMap](Map-Points_images/Map_Points_Icon_image.png)

## MapPointPopup

MapPointPopup is a popup, displayed when the point is moved to MapPoint. It shows additional information from the object bounded with the MapPoint. You can get the object from dbf file.

### MapPointPopupTemplate

[`MapPointPopupTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.ShapeFileLayer.html#Syncfusion_UI_Xaml_Maps_ShapeFileLayer_MapPointPopupTemplate) is a DataTemplate, used to expose the template for the MapPoint. 

{% highlight xaml %}

<syncfusion:SfMap>
     <syncfusion:SfMap.Layers>
         <syncfusion:ShapeFileLayer Background="White" EnableSelection="True" 
                                    Uri="MapApp.ShapeFiles.states.shp">
              <syncfusion:ShapeFileLayer.SubShapeFileLayers>
                 <syncfusion:SubShapeFileLayer   EnableSelection="True" 
                                    Uri="MapApp.ShapeFiles.landslide.shp">
                  <syncfusion:SubShapeFileLayer.MapPointPopupTemplate>
                        <DataTemplate>
                             <Border Background="#FF252525" Opacity="0.9"  Height="110"
                                     BorderThickness="0.5">
                               <StackPanel Margin="10,5,20,0">
                                   <StackPanel>
                                       <TextBlock Text="Landslide Event in USA"  
                                         Margin="10,5,0,0" Foreground="White" 
                                         FontSize="20"  FontFamily="Segoe UI" />
                                    </StackPanel>
                            <Grid Margin="10,5,10,0">
                               <Rectangle Stroke="#FF505050" StrokeDashArray="6 2" 
                                          Height="2"  VerticalAlignment="Center" />
                            </Grid>
                            <Grid Margin="10,5,0,0" >
                               <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="0.41*"/>
                                    <ColumnDefinition Width="0.1*"/>
                                    <ColumnDefinition Width="0.49*"/>
                                </Grid.ColumnDefinitions>
                                <Grid.RowDefinitions>
                                     <RowDefinition/>
                                     <RowDefinition/>
                                </Grid.RowDefinitions>

                             <TextBlock Foreground="#FFACACAC" Grid.Column="0" 
                                         Grid.Row="0" FontFamily="Segoe UI" 
                                         FontWeight="Normal" FontSize="18" 
                                         Text="Location" />
                             <TextBlock Foreground="#FFACACAC" Grid.Column="1" 
                                         Grid.Row="0" FontFamily="Segoe UI" 
                                         FontWeight="Normal" FontSize="18" Text=" : " />
                             <TextBlock Foreground="#FFACACAC" Margin="5,0,0,0" 
                                        Grid.Column="2" Grid.Row="0" FontFamily="Segoe 
                                        UI" FontWeight="Normal" FontSize="18" 
                                        Text="{Binding [LOCALITY]}" />
                             <TextBlock Foreground="#FFACACAC" Grid.Column="0" 
                                        Grid.Row="1" FontFamily="Segoe UI" 
                                        FontWeight="Normal" FontSize="18" Text="Year" />
                             <TextBlock Foreground="#FFACACAC" Grid.Column="1" 
                                        Grid.Row="1" FontFamily="Segoe UI" 
                                        FontWeight="Normal" FontSize="18" Text=" : " />
                             <TextBlock Foreground="#FFACACAC" Margin="5,0,0,0" 
                                        Grid.Column="2" Grid.Row="1" FontFamily="Segoe 
                                        UI" FontWeight="Normal" FontSize="18" 
                                        Text="{Binding [YEAR]}" />
                          </Grid>
                       </StackPanel>
                    </Border>
                  </DataTemplate>
              </syncfusion:SubShapeFileLayer.MapPointPopupTemplate>
              <syncfusion:SubShapeFileLayer.MapPointTemplate>
                 <DataTemplate>
                      <Ellipse Height="10" Width="10" Margin="-10,-10,0,0" Stroke="White" 
                                                                         Fill="#8AC63C"/>
                 </DataTemplate>
              </syncfusion:SubShapeFileLayer.MapPointTemplate>
           </syncfusion:SubShapeFileLayer>
       </syncfusion:ShapeFileLayer.SubShapeFileLayers>
     </syncfusion:ShapeFileLayer>
   </syncfusion:SfMap.Layers>
</syncfusion:SfMap>

{% endhighlight %}

![Map Points and popup image in WPF SfMap](Map-Points_images/Map_Points_Popup_image.png)

