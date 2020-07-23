---
layout: post
title: Annotations | SfMap | wpf | Syncfusion
description: annotations
platform: wpf
control: SfMap
documentation: ug
---

# Annotations

Annotations are notes that are used to leave some message on the map. In Maps, annotations are denoted by the MapAnnotations. MapAnnotation has two major parts:

1. AnnotationLabel
2. AnnotationSymbol

AnnotationLabel is a “Text” that shows some information in the text format. 

AnnotationSymbol is a “VisualObject” that shows a note symbolically.

1. AnnotationLabelForeground: Get or sets the foreground color of the annotation label.
2. AnnotationLabelFontStyle: Gets or sets the font style of the annotation label.
3. AnnotationLabelBackground: Gets or sets the background color of the annotation label.
4. AnnotationLabelFontFamily: Gets or sets the font family for the annotation label.
5. AnnotationLabelFontSize: Gets or sets the annotation label font size.


{% highlight xaml %}

    <syncfusion:SfMap >
        <syncfusion:SfMap.Layers>
            <syncfusion:ShapeFileLayer Uri="DataMarkers.ShapeFiles.world1.shp">
                <syncfusion:ShapeFileLayer.Annotations>
                    <syncfusion:MapAnnotations Latitude="-22" Longitude="132" 
                                               AnnotationLabel="Australia" 
                                               AnnotationLabelFontFamily="Times New Roman" 
                                               AnnotationLabelFontSize="20" 
                                               AnnotationLabelFontStyle="Oblique" 
                                               AnnotationLabelForeground="Red" >
                        <syncfusion:MapAnnotations.AnnotationSymbol>
                            <Ellipse Fill="Orange" Height="10" Width="10">
                            </Ellipse>
                        </syncfusion:MapAnnotations.AnnotationSymbol>
                    </syncfusion:MapAnnotations>
                    <syncfusion:MapAnnotations Latitude="40" Longitude="-98" 
                                               AnnotationLabel="Unites States of America" 
                                               AnnotationLabelFontFamily="Times New Roman" 
                                               AnnotationLabelFontSize="20" 
                                               AnnotationLabelFontStyle="Oblique" 
                                               AnnotationLabelForeground="Red" >
                        <syncfusion:MapAnnotations.AnnotationSymbol>
                            <Ellipse Fill="Orange" Height="10" Width="10">
                            </Ellipse>
                        </syncfusion:MapAnnotations.AnnotationSymbol>
                    </syncfusion:MapAnnotations>
                </syncfusion:ShapeFileLayer.Annotations>
            </syncfusion:ShapeFileLayer>
        </syncfusion:SfMap.Layers>
    </syncfusion:SfMap >

{% endhighlight %}

![](Annotations_images/Annotations_img1.png)



## Positioning a MapAnnotation

MapAnnotation can be positioned anywhere on the map based on latitude and longitude. MapAnnotation has two properties called “Latitude” and “Longitude” that are string types used to set co-ordinates of the MapAnnotation in the form of latitude and longitude. 

### Customizing the Annotation Template

The default appearance of the annotation can be customized by using the AnnotationTemplate property. The annotation template property is available in the ShapeFileLayer.

#### About the AnnotationTemplate Property

AnnotationTemplate is a DataTemplate type, used to customize or override the default template of MapAnnotations.

{% highlight xaml %}

       <syncfusion:SfMap >
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer   Uri="DataMarkers.ShapeFiles.world1.shp">
                    <syncfusion:ShapeFileLayer.Annotations>
                        <syncfusion:MapAnnotations Latitude="-22" Longitude="132" AnnotationLabel="Australia"  >
                            <syncfusion:MapAnnotations.AnnotationSymbol>
                                <Image Height="100" Width="100" Source="note.jpg" />
                            </syncfusion:MapAnnotations.AnnotationSymbol>
                        </syncfusion:MapAnnotations>
                        <syncfusion:MapAnnotations Latitude="40" Longitude="-98" AnnotationLabel="USA">
                            <syncfusion:MapAnnotations.AnnotationSymbol>
                                <Image Height="100" Width="100" Source="note.jpg" />
                            </syncfusion:MapAnnotations.AnnotationSymbol>
                        </syncfusion:MapAnnotations>
                    </syncfusion:ShapeFileLayer.Annotations>
                    <syncfusion:ShapeFileLayer.AnnotationTemplate>
                        <DataTemplate>
                            <Grid Margin="-50,-20,0,0">
                                <ContentPresenter Content="{Binding AnnotationSymbol}"/>
                                <TextBlock Text="{Binding AnnotationLabel}" HorizontalAlignment="Center" 
                                       VerticalAlignment="Center"/>
                            </Grid>
                        </DataTemplate>
                    </syncfusion:ShapeFileLayer.AnnotationTemplate>
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>

        </syncfusion:SfMap >

{% endhighlight %}


![](Annotations_images/Annotations_img2.png)



