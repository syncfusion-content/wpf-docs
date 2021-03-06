---
layout: post
title: Annotations in WPF Maps control | Syncfusion
description: Learn here all about Annotations support in Syncfusion WPF Maps (SfMap) control, its elements and more details.
platform: wpf
control: SfMap
documentation: ug
---

# Annotations in WPF Maps (SfMap)

Annotations are notes that are used to leave some message on the map. In Maps, annotations are denoted by the MapAnnotations. MapAnnotation has two major parts:

1. AnnotationLabel
2. AnnotationSymbol

[`AnnotationLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabel) is a `Text` that shows some information in the text format. 

[`AnnotationSymbol`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationSymbol) is a `VisualObject` that shows a note symbolically.

1. [`AnnotationLabelForeground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabelForeground): Get or sets the foreground color of the annotation label.
2. [`AnnotationLabelFontStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabelFontStyle): Gets or sets the font style of the annotation label.
3. [`AnnotationLabelBackground`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabelBackground): Gets or sets the background color of the annotation label.
4. [`AnnotationLabelFontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabelFontFamily): Gets or sets the font family for the annotation label.
5. [`AnnotationLabelFontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationLabelFontSize): Gets or sets the annotation label font size.
6. [`Latitude`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_Latitude): Gets or sets the Latitude coordinate of the Annotation.
7. [`Longitude`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_Longitude): Gets or set the Longitude coordinate of the Annotation.

{% tabs %}

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

{% highlight c# %}

       SfMap map = new SfMap();
            ShapeFileLayer shapeFileLayer = new ShapeFileLayer();
            shapeFileLayer.Uri = "DataMarkers.ShapeFiles.world1.shp";

            MapAnnotations annotations = new MapAnnotations();
            annotations.Latitude = -22;
            annotations.Longitude = 132;
            annotations.AnnotationLabel = "Australia";
            annotations.AnnotationLabelFontFamily = new FontFamily("Times New Roman");
            annotations.AnnotationLabelFontSize = 20;
            annotations.AnnotationLabelFontStyle = FontStyles.Oblique;
            annotations.AnnotationLabelForeground = new SolidColorBrush(Colors.Red);
            Ellipse ellipse = new Ellipse();
            ellipse.Fill = new SolidColorBrush(Colors.Orange);
            ellipse.Height = 10;
            ellipse.Width = 10;
            annotations.AnnotationSymbol = ellipse;
            shapeFileLayer.Annotations.Add(annotations);

            MapAnnotations annotations1 = new MapAnnotations();
            annotations1.Latitude = 40;
            annotations1.Longitude = -98;
            annotations1.AnnotationLabel = "Unites States of America";
            annotations1.AnnotationLabelFontFamily = new FontFamily("Times New Roman");
            annotations1.AnnotationLabelFontSize = 20;
            annotations1.AnnotationLabelFontStyle = FontStyles.Oblique;
            annotations1.AnnotationLabelForeground = new SolidColorBrush(Colors.Red);
            Ellipse ellipse1 = new Ellipse();
            ellipse1.Fill = new SolidColorBrush(Colors.Orange);
            ellipse1.Height = 10;
            ellipse1.Width = 10;
            annotations1.AnnotationSymbol = ellipse1;
            shapeFileLayer.Annotations.Add(annotations1);
            map.Layers.Add(shapeFileLayer);
            grid.Children.Add(map);
          
{% endhighlight %}

{% endtabs %}

![Maps Annotation with Customization](Annotations_images/Annotations_img1.png)

## Positioning a MapAnnotation

MapAnnotation can be positioned anywhere on the map based on latitude and longitude. MapAnnotation has two properties called [`Latitude`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_Latitude) and [`Longitude`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_Longitude) that are string types used to set co-ordinates of the MapAnnotation in the form of latitude and longitude. 

### Customizing the Annotation Template

The default appearance of the annotation can be customized by using the [`AnnotationTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Maps.MapAnnotations.html#Syncfusion_UI_Xaml_Maps_MapAnnotations_AnnotationTemplate) property. The annotation template property is available in the ShapeFileLayer.

AnnotationTemplate is a DataTemplate type, used to customize or override the default template of MapAnnotations.

{% tabs %}
{% highlight xaml %}
     <Grid x:Name="grid">
       <Grid.Resources>
            <DataTemplate x:Key="annotationTemplate">
                <Grid >
                    <ContentPresenter Content="{Binding AnnotationSymbol}"/>
                    <TextBlock Text="{Binding AnnotationLabel}" HorizontalAlignment="Center" 
                                       VerticalAlignment="Center" />
                </Grid>
            </DataTemplate>
        </Grid.Resources>

      <syncfusion:SfMap >
            <syncfusion:SfMap.Layers>
                <syncfusion:ShapeFileLayer   Uri="DataMarkers.ShapeFiles.world1.shp" AnnotationTemplate="{StaticResource annotationTemplate}">
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
                   
                </syncfusion:ShapeFileLayer>
            </syncfusion:SfMap.Layers>

        </syncfusion:SfMap >
    </Grid>

{% endhighlight %}

{% highlight c# %}

 SfMap map = new SfMap();
            ShapeFileLayer shapeFileLayer = new ShapeFileLayer();
            shapeFileLayer.Uri = "WpfUG.Assets.ShapeFiles.world1.shp";
            shapeFileLayer.AnnotationTemplate = grid.Resources["annotationTemplate"] as DataTemplate;

            MapAnnotations annotations = new MapAnnotations();
            annotations.Latitude = -22;
            annotations.Longitude = 132;
            annotations.AnnotationLabel = "Australia";
            Image image = new Image();
            image.Source = new BitmapImage(new Uri(@"/Assets/pin.png", UriKind.Relative));
            image.Height = 100;
            image.Width = 100;
            annotations.AnnotationSymbol = image;
            shapeFileLayer.Annotations.Add(annotations);

            MapAnnotations annotations1 = new MapAnnotations();
            annotations1.Latitude = 40;
            annotations1.Longitude = -98;
            annotations1.AnnotationLabel = "USA";
            image = new Image();
            image.Source = new BitmapImage(new Uri(@"/Assets/pin.png", UriKind.Relative));
            image.Height = 100;
            image.Width = 100;
            annotations1.AnnotationSymbol = image;
            shapeFileLayer.Annotations.Add(annotations1);
            map.Layers.Add(shapeFileLayer);
            grid.Children.Add(map);


{% endhighlight %}

{% endtabs %}


![Maps Annotation with Positioning](Annotations_images/Annotations_img2.png)

N> You can refer to our [WPF Map](https://www.syncfusion.com/wpf-controls/map) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Map example](https://github.com/syncfusion/wpf-demos/tree/master/map) to know how to render and configure the map.

