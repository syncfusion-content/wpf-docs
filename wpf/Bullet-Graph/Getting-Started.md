---
layout: post
title: Getting Started with WPF Bullet Graph control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Bullet Graph (SfBulletGraph) control, its elements and more details.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Getting Started with WPF Bullet Graph (SfBulletGraph)

This section explains you the steps required to configure the [`SfBulletGraph`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html) and also explains the steps to add basic elements of `SfBulletGraph` using the various API’s available within it.

## Configuring SfBulletGraph using Syncfusion Reference Manager

Syncfusion Reference Manager is used to add Syncfusion Tools.

Follow these steps to add `SfBulletGraph` Control using the Syncfusion Reference Manager.

Create a simple WPF application using Visual Studio.

![Create new WPF Project in Visual Studio](Getting-Started_images/Getting-Started_img1.jpeg)

Right Click on the Project and select Syncfusion Reference Manager.

![selecting Syncfusion Reference Manager](Getting-Started_images/Getting-Started_img2.jpeg)

The Syncfusion Reference Manager Wizard will be opened as shown in the figure below.

![Opening Syncfusion Reference Manager Wizard](Getting-Started_images/Getting-Started_img3.jpeg)

Search for `SfBulletGraph` using SearchBox and select the `SfBulletGraph` Control. Click `Done` to add selected SfBulletGraph control.

![Selecting SfBulletGraph Control in Syncfusion Reference Manager](Getting-Started_images/Getting-Started_img4.jpeg)

The `SfBulletGraph` assemblies will be automatically added to the project after clicking `OK`.

![Adding SfBulletGraph assemblies in WPF application](Getting-Started_images/Getting-Started_img5.jpeg)

![Added SfBulletGraph assemblies in WPF application](Getting-Started_images/Getting-Started_img6.jpeg)

Create a namespace reference to the SfBulletGraph control using Syncfusion’s global namespace reference **schemas.Syncfusion.com** or the SfBulletGraph control’s namespace reference using **Syncfusion.UI.Xaml.BulletGraph** available in the **Syncfusion.SfBulletGraph.WPF** assembly.

{% highlight xaml %}

    xmlns:bulletgraph="http://schemas.syncfusion.com/wpf"
    (or)
    xmlns:bulletgraph ="clr-
    namespace:Syncfusion.UI.Xaml.BulletGraph;assembly=Syncfusion.SfBulletGraph. WPF"

{% endhighlight %}

Add the following code to create a simple SfBulletGraph control.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="SfBulletGraph.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion ="http://schemas.syncfusion.com/wpf"
    Title="MainWindow" Height="350" Width="525">
    <Grid x:Name="LayoutRoot">
    <syncfusion:SfBulletGraph/>
    </Grid>
    </Window>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    this.Grid.Children.Add(bulletgraph);        
    
{% endhighlight %}
{% endtabs %}

The SfBulletGraph control will be created as shown in the figure below.

![Displaying SfBulletGraph control](Getting-Started_images/Getting-Started_img7.jpg)

>**Note:- The Syncfusion Reference Manager is available in versions 11.3.0.30 and later. It supports referencing assemblies from version 10.4.0.71 version to the current version and Syncfusion Reference Manager can be used only in Visual Studio 2010, 2012, 2013 and 2015.**

## Configuring SfBulletGraph

**SfBulletGraph** is available in the following assembly and namespace:

**Assembly**: Syncfusion.SfBulletGraph.Wpf

**Namespace**: Syncfusion.UI.Xaml.BulletGraph

Create a namespace reference to the SfBulletGraph control using Syncfusion’s global namespace reference **schemas.Syncfusion.com** or the SfBulletGraph control’s namespace reference using **Syncfusion.UI.Xaml.BulletGraph** available in the **Syncfusion.SfBulletGraph.WPF** assembly.

{% highlight xaml %}

    xmlns:bulletgraph="http://schemas.syncfusion.com/wpf"
    (or)
    xmlns:bulletgraph ="clr-
    namespace:Syncfusion.UI.Xaml.BulletGraph;assembly=Syncfusion.SfBulletGraph. WPF"

{% endhighlight %}

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph/>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    this.Grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Displaying SfBulletGraph control](Getting-Started_images/Getting-Started_img7.jpg)

As you can see now in the above image, the SfBulletGraph displays its default elements. To customize its element, you have to add respective elements to SfBulletGraph, following section contains the steps to add the basic elements to SfBulletGraph.

## Adding Caption

You can assign a caption to bullet graph by making use of [`Caption`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Caption) property and also you can position it either near or far using the [`CaptionPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_CaptionPosition) property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph CaptionPosition="Far">
            <syncfusion:SfBulletGraph.Caption>
                <StackPanel Margin="0,0,10,0">
                    <TextBlock Text="Revenue YTD" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                    <TextBlock Text="$ in Thousands" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                </StackPanel>
            </syncfusion:SfBulletGraph.Caption>
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.CaptionPosition = BulletGraphCaptionPosition.Far;
            TextBlock textBlock = new TextBlock() { Text = "Revenue YTD" };
            TextBlock textBlock1 = new TextBlock() { Text = "$ in Thousands" };
            StackPanel stackPanel = new StackPanel();
            stackPanel.Children.Add(textBlock);
            stackPanel.Children.Add(textBlock1);
            bulletgraph.Caption = stackPanel;
            grid.Children.Add(bulletgraph);

    
{% endhighlight %}
{% endtabs %}

![Adding Caption to SfBulletGraph control](Caption_images/CaptionPosition.png)

## Configuring Ticks and Labels 

You can configure Ticks and Labels of Quantitative Scale by making use of following API’s available in SfBulletGraph.

They are:

* Minimum
* Maximum
* Interval
* MinorTicksPerInterval
* MajorTickSize
* MinorTickSize
* MajorTickStroke
* LabelStroke
* MinorTickStroke

{% tabs %}
{% highlight xaml %}

      <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"
                                  ComparativeMeasure="7" FeaturedMeasure="5" FeaturedMeasureBarStroke="Black" MajorTickStroke="Red"
                                  MinorTickStroke="Green" MinorTicksPerInterval="3"
                                    MajorTickSize="15" MinorTickSize="10">
            <syncfusion:SfBulletGraph.QualitativeRanges>
                <syncfusion:QualitativeRange RangeEnd="4.5" RangeStroke="#EBEBEB"></syncfusion:QualitativeRange>
                <syncfusion:QualitativeRange RangeEnd="10" RangeStroke="#7F7F7F"></syncfusion:QualitativeRange>
                <syncfusion:QualitativeRange RangeEnd="7.5" RangeStroke="#D8D8D8"></syncfusion:QualitativeRange>
            </syncfusion:SfBulletGraph.QualitativeRanges>
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.Minimum = 0;
            bulletgraph.Maximum = 10;
            bulletgraph.Interval = 2;
            bulletgraph.FeaturedMeasure = 5;
            bulletgraph.ComparativeMeasure = 7;
            bulletgraph.MajorTickStroke = new SolidColorBrush(Colors.Red);
            bulletgraph.MinorTickStroke = new SolidColorBrush(Colors.Green);
            bulletgraph.FeaturedMeasureBarStroke = new SolidColorBrush(Colors.Black);
            bulletgraph.MinorTicksPerInterval = 3;
            bulletgraph.MinorTickSize = 10;
            bulletgraph.MajorTickSize = 15;
            bulletgraph.Orientation = Orientation.Horizontal;
            QualitativeRange range1 = new QualitativeRange();
            range1.RangeEnd = 4.5;
            range1.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#EBEBEB");
            QualitativeRange range2 = new QualitativeRange();
            range2.RangeEnd = 10;
            range2.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#7F7F7F");

            QualitativeRange range3 = new QualitativeRange();
            range3.RangeEnd = 7.5;
            range3.RangeStroke = (Brush)new BrushConverter().ConvertFrom("#D8D8D8");

            bulletgraph.QualitativeRanges.Add(range1);
            bulletgraph.QualitativeRanges.Add(range2);
            bulletgraph.QualitativeRanges.Add(range3);
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Configuring Ticks and Labels](Getting-Started_images/Getting-Started_img9.jpg)


## Adding Ranges 

You can add ranges to bullet graph by creating ranges collection using [`QualitativeRanges`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_QualitativeRanges). 

{% tabs %}
{% highlight xaml %}

           <syncfusion:SfBulletGraph Orientation="Horizontal" Minimum="0" Maximum="10" Interval="2"  
                                  QualitativeRangesSize="30"  MinorTicksPerInterval="3" ComparativeMeasure="7" FeaturedMeasure="5"
                                  QuantitativeScaleLength="300" FeaturedMeasureBarStroke="Black"  MinorTickSize="10" MajorTickSize="14">
            <syncfusion:SfBulletGraph.QualitativeRanges>
                <syncfusion:QualitativeRange RangeEnd="4.5" RangeCaption="Bad"
                                             RangeStroke="Red"
                                             RangeOpacity="1">
                </syncfusion:QualitativeRange>
                <syncfusion:QualitativeRange RangeEnd="7.5" 
                                             RangeStroke="Yellow"
                                             RangeOpacity="1">
                </syncfusion:QualitativeRange>
                <syncfusion:QualitativeRange RangeEnd="10" 
                                             RangeStroke="Green"
                                             RangeOpacity="1">
                </syncfusion:QualitativeRange>
            </syncfusion:SfBulletGraph.QualitativeRanges>
        </syncfusion:SfBulletGraph>


{% endhighlight %}

{% highlight c# %}

          SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.Minimum = 0;
            bulletgraph.Maximum = 10;
            bulletgraph.FeaturedMeasure = 5;
            bulletgraph.ComparativeMeasure = 7;
            bulletgraph.Interval = 2;
            bulletgraph.MinorTickSize = 8;
            bulletgraph.MinorTicksPerInterval = 3;
            bulletgraph.QualitativeRangesSize = 30;
            bulletgraph.QuantitativeScaleLength = 300;
            bulletgraph.FeaturedMeasureBarStroke = new SolidColorBrush(Colors.Black);
            bulletgraph.QualitativeRanges.Add(new QualitativeRange()
            {
                RangeEnd = 4.5,
                RangeOpacity = 1,
                RangeStroke = new SolidColorBrush(Colors.Red)
            });
            bulletgraph.QualitativeRanges.Add(new QualitativeRange()
            {
                RangeEnd = 7.5,
                RangeOpacity = 1,
                RangeStroke = new SolidColorBrush(Colors.Yellow)
            });
            bulletgraph.QualitativeRanges.Add(new QualitativeRange()
            {
                RangeEnd = 10,
                RangeOpacity = 1,
                RangeStroke = new SolidColorBrush(Colors.Green)
            });
            grid.Children.Add(bulletgraph);
            
{% endhighlight %}
{% endtabs %}

SfBulletGraph ranges are displayed as follows.

You can get the complete getting started sample [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/BulletGraphDemo-1174716111).

![Adding Ranges to SfBulletGraph control](Getting-Started_images/Getting-Started_img10.jpg)

## Theme

Bullet Graph supports various built-in themes. Refer to the below links to apply themes for the Bullet Graph,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Bullet Graph](Getting-Started_images/Theme.png)
