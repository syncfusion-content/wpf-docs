---
layout: post
title: KML-Shapes-Rendered-in-SubShapeFileLayer
description: kml shapes rendered in subshapefilelayer
platform: wpf
control: SfMap
documentation: ug
---

# KML Shapes Rendered in SubShapeFileLayer


{% highlight xml %}


[XAML]



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



![](KML-Shapes-Rendered-in-SubShapeFileLayer_images/KML-Shapes-Rendered-in-SubShapeFileLayer_img1.png)



