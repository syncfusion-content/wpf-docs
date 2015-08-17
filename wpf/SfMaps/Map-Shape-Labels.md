---
layout: post
title: Map-Shape-Labels
description: map shape labels
platform: wpf
control: SfMap
documentation: ug
---

# Map Shape Labels

Labels for map shapes can be displayed by using the LabelPath of ShapeFileLayer. The value of LabelPath must be a field name specified in the .dbf file corresponding to the shapefile. 

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
LabelPath</td><td>
string</td><td>
Gets or sets the field name in the database (.dbf) file.</td></tr>
</table>

{% highlight xml %}

[XAML]

    <syncfusion:SfMap>

        <syncfusion:SfMap.Layers>

            <syncfusion:ShapeFileLayer x:Name="shapeFileLayer"   

                                       Uri="BubbleVisualization.world1.shp"                                                               

                                       LabelPath="NAME" FontSize="14">

            </syncfusion:ShapeFileLayer>

        </syncfusion:SfMap.Layers>

    </syncfusion:SfMap>  

{% endhighlight %}



The labels can also be customized by modifying the ItemsTemplate of ShapeFileLayer. The labels can be accessed by using DBFData as follows:

{% highlight xml %}

[XAML]

     <syncfusion:SfMap>

        <syncfusion:SfMap.Layers>

            <syncfusion:ShapeFileLayer x:Name="shapeFileLayer" 

                                       Uri="BubbleVisualization.world1.shp"

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



_Map with Labels_

