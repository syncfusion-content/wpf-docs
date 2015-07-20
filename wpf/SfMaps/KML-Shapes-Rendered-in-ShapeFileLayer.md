---
layout: post
title: KML-Shapes-Rendered-in-ShapeFileLayer
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



[XAML]



        &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer Uri="KmlImportDemo.KMLFiles.Eu.kml"&gt;                    

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap&gt;



{ ![](KML-Shapes-Rendered-in-ShapeFileLayer_images/KML-Shapes-Rendered-in-ShapeFileLayer_img1.png) | markdownify }
{:.image }


