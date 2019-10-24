---
layout: post
title: KML Shapes Rendered in ShapeFileLayer | ThefollowingpropertiesexposedatabindingintheMaps | wpf | Syncfusion
description: kml shapes rendered in shapefilelayer
platform: wpf
control: SfMap
documentation: ug
---

# KML Shapes Rendered in ShapeFileLayer

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

![](KML-Shapes-Rendered-in-ShapeFileLayer_images/KML-Shapes-Rendered-in-ShapeFileLayer_img1.png)



