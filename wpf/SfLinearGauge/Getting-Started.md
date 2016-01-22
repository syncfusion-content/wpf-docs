---
layout: post
title: Linear Gauge Elements | SfLinearGauge | Wpf | Syncfusion
description: Linear Gauge Elements 
platform: wpf
control: SfLinearGauge
documentation: ug
---

# Getting Started

This section explains you the steps required to configure the **SfLinearauge** and also explains the steps to add basic elements of **SfLinearauge** through various API’s available within it.

## Configuring SfLinearGauge using Syncfusion Reference Manager

Syncfusion Reference Manager is used to add Syncfusion Tools.

Follow the below steps to add SfLinearGauge Control using Syncfusion Reference Manager.

Create a simple WPF application using Visual Studio.

![](Getting-Started_images/Getting-Started_img1.jpeg)

Right Click on the Project and select Syncfusion Reference Manager.

![](Getting-Started_images/Getting-Started_img2.jpeg)

The Syncfusion Reference Manager Wizard wil be opened as shown in the figure below.

![](Getting-Started_images/Getting-Started_img3.jpeg)

Search for **SfLinearGauge** using Search Box and select SfLinearGauge Control.  Click on done to add selected SfLinearGauge Control.

![](Getting-Started_images/Getting-Started_img4.jpeg)

The SfLinearGauge assemblies will be automatically added to the Project after Clicking **OK**.

![](Getting-Started_images/Getting-Started_img5.jpeg)

![](Getting-Started_images/Getting-Started_img6.jpeg)

Create a namespace reference to the SfLinearGauge control using Syncfusion’s global namespace reference **schemas.syncfusion.com** or the SfLinearGauge control’s namespace reference using **Syncfusion.UI.Xaml.Gauges** available in the **Syncfusion.SfGauge.WPF** assembly.

{% highlight xaml %}

    xmlns:LinearGauge="http://schemas.syncfusion.com/wpf" 
    (or)
    xmlns:LinearGauge ="clr-   
    namespace:Syncfusion.UI.Xaml.Gauges;assembly=Syncfusion.SfLinearGauge.WPF"
    
{% endhighlight %}

Add the following code to create a simple SfLinearGauge control.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="LinearGauge.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:Gauges="http://schemas.syncfusion.com/wpf"
    Title="MainWindow" Height="350" Width="525">
    <Grid Name="Grid">
    <Gauges:SfLinearGauge/>
    </Grid
    </Window>

{% endhighlight %}

{% highlight c# %}

    SfLinearGauge lineargauge = new SfLinearGauge();
    this.Grid.Children.Add(lineargauge);
    
{% endhighlight %}
{% endtabs %}

The SfLinearGauge  will be created as shown in the figure below.

![](Getting-Started_images/Getting-Started_img7.png)

>**Note:- The Syncfusion Reference Manager is available in versions 11.3.0.30 and later. It supports referencing assemblies from version 10.4.0.71 version to the current version and Syncfusion Reference Manager can be used only in Visual Studio 2010, 2012, 2013 and 2015.**

## Configuring SfLinearGauge

SfLinearGauge exists in the following assembly and namespace.

**Assembly**: Syncfusion.SfGauge.Wpf

**Namespace**: Syncfusion.UI.Xaml.Gauges

Create a namespace reference to the SfLinearGauge control using Syncfusion’s global namespace reference **schemas.syncfusion.com** or the SfLinearGauge control’s namespace reference using **Syncfusion.UI.Xaml.Gauges** available in the **Syncfusion.SfGauge.WPF** assembly.

{% highlight xaml %}

    xmlns:Gauges="http://schemas.syncfusion.com/wpf" 
    (or)
    xmlns:Gauges ="clr-   
    namespace:Syncfusion.UI.Xaml.Gauges;assembly=Syncfusion.SfLinearGauge.WPF"
    
{% endhighlight %}

{% highlight xaml %}

    <Gauges:SfLinearGauge/>

{% endhighlight %}

Run the above code and now the default SfLinearGauge can be displays as follows. In order to customize scales and other SfLinearGauge elements, you have to add the respecting element to SfLinearGauge.

![](Getting-Started_images/Getting-Started_img8.png)

As you can see now in the above image, the SfLinearGauge displays its default elements. To customize the basic look and feel of the SfLinearGauge you have to add respective elements to SfLinearGauge, which will be explained in the next section.

## Configuring LinearScale 

You can configure the LinearScale elements by making use of following API’s available in SfLinearGauge.

They are:

* ScaleDirection
* ScaleBarStroke
* ScaleBarSize
* ScaleBarLength
* ScaleBarBorderThickness
* Interval
* Minimum
* Maximum

{% tabs %}
{% highlight xaml %}

              <Gauges:SfLinearGauge Name="linearGauge" Orientation="Horizontal">
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale ScaleDirection="Forward"
                                    ScaleBarStroke="White" 
                                    ScaleBarSize="20" 
                                    ScaleBarLength="350"
                                    ScaleBarBorderThickness="1"
                                    Interval="10"
                                    Minimum="0" Maximum="100">
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge> 

{% endhighlight %}

{% highlight c# %}

            SfLinearGauge lineargauge = new SfLinearGauge();
            lineargauge.Orientation = Orientation.Horizontal;
            LinearScale _mainScale = new LinearScale();
            _mainScale.ScaleDirection = LinearScaleDirection.Forward;
            _mainScale.ScaleBarStroke = new SolidColorBrush(Colors.White);
            _mainScale.ScaleBarSize = 20;
            _mainScale.ScaleBarLength = 350;
            _mainScale.ScaleBarBorderThickness = new Thickness(1);
            _mainScale.Interval = 10;
            _mainScale.Minimum = 0;
            _mainScale.Maximum = 100;
            lineargauge.MainScale = _mainScale;
            this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img9.jpeg)

## Adding Ranges 

You can add ranges to SfLinearGauge by creating **LinearRange** collection using **Ranges**.

{% tabs %}
{% highlight xaml %}

     <Gauges:SfLinearGauge>
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale>
                    <Gauges:LinearScale.Ranges>
                        <Gauges:LinearRange StartValue="0" EndValue="35" 
                                            StartWidth="25" EndWidth="10" 
                                            RangeOffset="5" RangeOpacity="1"
                                            RangeStroke="Green"/>
                        <Gauges:LinearRange StartValue="65" EndValue="100" 
                                            StartWidth="10" EndWidth="25" 
                                            RangeOffset="5" RangeOpacity="1"
                                            RangeStroke="Red"/>
                    </Gauges:LinearScale.Ranges>
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge>


{% endhighlight %}

{% highlight c# %}

           SfLinearGauge lineargauge = new SfLinearGauge();
           LinearScale _mainScale = new LinearScale();
           _mainScale.Ranges.Add(new LinearRange()
           {
               StartValue = 0,
               EndValue = 35,
               StartWidth = 25,
               EndWidth = 10,
               RangeOffset = 5,
               RangeOpacity = 1,
               RangeStroke = new SolidColorBrush(Colors.Green)
           });
           _mainScale.Ranges.Add(new LinearRange() 
           { 
               StartValue = 65,
               EndValue = 100, 
               StartWidth = 10, 
               EndWidth = 25,
               RangeOffset = 5,
               RangeOpacity = 1,
               RangeStroke = new SolidColorBrush(Colors.Red) 
           });
           lineargauge.MainScale = _mainScale;
           this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img10.jpeg)

## Adding Pointers 

You can also add Pointers to SfLinearGauge to point a values on the scale.

{% tabs %}
{% highlight xaml %}

      <Gauges:SfLinearGauge Name="linearGauge">
            <Gauges:SfLinearGauge.MainScale>
                <Gauges:LinearScale>
                    <Gauges:LinearScale.Pointers>
                        <Gauges:LinearPointer Value="40" PointerType="BarPointer" />
                        <Gauges:LinearPointer Value="40" PointerType="SymbolPointer"/>
                    </Gauges:LinearScale.Pointers>
                </Gauges:LinearScale>
            </Gauges:SfLinearGauge.MainScale>
        </Gauges:SfLinearGauge>

{% endhighlight %}

{% highlight c# %}

           SfLinearGauge lineargauge = new SfLinearGauge();
           LinearScale _mainScale = new LinearScale();
           _mainScale.Pointers.Add(new LinearPointer()
           {
               Value = 40,
               PointerType = LinearPointerType.BarPointer
           });
           _mainScale.Pointers.Add(new LinearPointer()
           {
               Value = 40,
               PointerType = LinearPointerType.SymbolPointer,
               SymbolPointerPosition = LinearSymbolPointersPosition.Above
           });
           lineargauge.MainScale = _mainScale;
           this.Grid.Children.Add(lineargauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img11.jpeg)
