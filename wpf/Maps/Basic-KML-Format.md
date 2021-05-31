---
layout: post
title: KML Format in WPF Maps control | Syncfusion
description: Learn here all about KML Format support in Syncfusion WPF Maps (SfMap) control, its elements and more details.
platform: wpf
control: SfMap
 documentation: ug
---

# KML Format in WPF Maps (SfMap)

KML is a file format used for rendering geographical data. It uses a tag-based structure with nested elements and attributes. KML is based on the XML standard, and all tags of a KML file are case-sensitive.

Currently, the SfMaps control supports the following KML elements:

* Place mark
* Point
* LinearRing
* Polygon
* MultiGeometry
* Region
* Style
* StyleMap
* BalloonStyle
* LineStyle
* PolyStyle
* IconStyle
* ExtendedData

## KML Shapes Support in ShapeFileLayer

A KML file can be rendered with the help of the ShapeFileLayer in SfMap. The KML file should be added as an Embedded Resource to the application project. The URI of the KML file must be given in the following order:

1. Namespace of project
2. Folder names
3. KmlFileName.kml

{% highlight xaml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer Uri="KmlImportDemo.KMLFiles.Eu.kml">                    
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}

![KML Shapes Support in ShapeFileLayer](KML-Shapes-Rendered-in-ShapeFileLayer_images/KML-Shapes-Rendered-in-ShapeFileLayer_img1.png)

## KML Shapes Support in SubShapeFileLayer

A KML file can be rendered with the help of the SubShapeFileLayer in SfMap.The URI of the KML file given in SubShapeFileLayer as follows. 

{% highlight xaml %}

        <syncfusion:SfMap>
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer Uri="KmlImportDemo. ShapeFiles.world1.shp">
                    <syncfusion:ShapeFileLayer.SubShapeFileLayers>
                        <syncfusion:SubShapeFileLayer Uri="KmlImportDemo.KmlFiles.Eu.kml"/>
                    </syncfusion:ShapeFileLayer.SubShapeFileLayers>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>
        </syncfusion:SfMap>

{% endhighlight %}


![KML Shapes Support in SubShapeFileLayer](KML-Shapes-Rendered-in-SubShapeFileLayer_images/KML-Shapes-Rendered-in-SubShapeFileLayer_img1.png)

