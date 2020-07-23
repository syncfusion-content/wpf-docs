---
layout: post
title: Map Shape Labels | SfMap | wpf | Syncfusion
description: map shape labels
platform: wpf
control: SfMap
documentation: ug
---

# Map Shape Labels

Labels for map shapes can be displayed by using the [`LabelPath`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeFileLayer~LabelPath.html) of ShapeFileLayer. The value of LabelPath must be a field name specified in the .dbf file corresponding to the shapefile. 



<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
LabelPath</td><td>
string</td><td>
Gets or sets the field name in the database (.dbf) file.</td></tr>
</table>

{% highlight xaml %}

      <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer x:Name="shapeFileLayer"   
                                       Uri="DataMarkers.ShapeFiles.world1.shp"                                                               
                                       LabelPath="NAME" FontSize="14">
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

The labels can also be customized by modifying the [`ItemsTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMaps.WPF~Syncfusion.UI.Xaml.Maps.ShapeFileLayer~ItemsTemplate.html) of ShapeFileLayer. The labels can be accessed by using DBFData as follows:

{% highlight xaml %}

       <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer Uri="DataMarkers.ShapeFiles.world1.shp"
                                       LabelPath="NAME">
                    <syncfusion:ShapeFileLayer.ItemsTemplate>
                        <DataTemplate>
                            <Grid Background="Gray" Opacity="0.75">
                                <TextBlock Text="{Binding DBFData[NAME]}"
                                       FontSize="14" Margin="10 5"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:ShapeFileLayer.ItemsTemplate>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}


![](Map-Shape-Labels_images/Map-Shape-Labels_img1.png)


