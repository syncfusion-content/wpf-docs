---
layout: post
title: Getting Started | SfSchedule | Wpf | Syncfusion
description: Getting Started
platform: wpf
control: SfSchedule
documentation: ug
---

# Getting Started

This section explains you the steps required to configure the **SfCircularGauge** and also explains the steps to add basic elements of **SfCircularGauge** through various API’s available within it.

## Configuring SfCircularGauge using Syncfusion Reference Manager

Syncfusion Reference Manager is used to add   Syncfusion Tools.

Follow the below steps to add SfCircularGauge using Syncfusion Reference Manager

Create a simple WPF application using Visual Studio.

![](Getting-Started_images/Getting-Started_img1.jpeg)

Right Click on the Project and _select Syncfusion Reference Manager.

![](Getting-Started_images/Getting-Started_img2.jpeg)

The Syncfusion Reference Manager Wizard will be opened as shown in the figure below.

![](Getting-Started_images/Getting-Started_img3.jpeg)

Search for **SfCircularGauge** using Search Box and select SfCircularGauge Control.  Click on done to add selected SfCircularGauge Control.

![](Getting-Started_images/Getting-Started_img4.jpeg)

The SfCircularGauge assemblies will be automatically added to the Project after Clicking **OK**.

![](Getting-Started_images/Getting-Started_img5.jpeg)

![](Getting-Started_images/Getting-Started_img6.png)

Create a namespace reference to the SfCircularGauge control using Syncfusion’s global namespace reference **schemas.syncfusion.com** or the SfCircularGauge control’s namespace reference using **Syncfusion.UI.Xaml.Gauges** available in the **Syncfusion.SfGauge.WPF** assembly.

{% highlight xml %}

    xmlns:syncfusion ="http://schemas.syncfusion.com/wpf" 
    
    or
    
    xmlns:syncfusion ="clr-namespace:Syncfusion.UI.Xaml.Gauges;assembly=Syncfusion.SfGauge.Wpf"

{% endhighlight %}

Add the following code to create a simple SfCircularGauge control.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="SampleCircularGauge.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
    Title="MainWindow" Height="350" Width="525">
    <Grid Name="Grid" Background="Black">
    <syncfusion:SfCircularGauge></syncfusion:SfCircularGauge>
    </Grid>
</Window>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circulargauge = new SfCircularGauge();
    this.Grid.Children.Add(circulargauge); 

{% endhighlight %}
{% endtabs %}

The default SfCircularGauge control will be created as shown in the figure below.

![](Getting-Started_images/Getting-Started_img7.png)

>**Note:-The Syncfusion Reference Manager is available in versions 11.3.0.30 and later. It supports referencing assemblies from version 10.4.0.71 version to the current version and Syncfusion Reference Manager can be used only in Visual Studio 2010, 2012, 2013 and 2015.**

## Configuring SfCircularGauge

**SfCircularGauge** is available in the following assembly and namespace:

**Assembly**: Syncfusion.SfGauge.Wpf

**Namespace**: Syncfusion.UI.Xaml.Gauges

Create a namespace reference to the SfCircularGauge control using Syncfusion’s global namespace reference **schemas.syncfusion.com** or the SfCircularGauge control’s namespace reference using **Syncfusion.UI.Xaml.Gauges** available in the **Syncfusion.SfGauge.WPF** assembly.

{% highlight xml %}

    xmlns:syncfusion ="http://schemas.syncfusion.com/wpf" 
    
    or
    
    xmlns:syncfusion ="clr-namespace:Syncfusion.UI.Xaml.Gauges;assembly=Syncfusion.SfGauge.Wpf"

{% endhighlight %}

{% highlight xml %}

    <syncfusion:SfCircularGauge/>
    
{% endhighlight %}

Run the above code and now the default SfCircularGauge can be displays as follows. In order to customize scales and other SfCircularGauge elements, you have to add the respecting element to SfCircularGauge.

![](Getting-Started_images/Getting-Started_img8.png)

As you can see now in the above image, the SfCircularGauge displays its default elements. To customize the basic look and feel of the SfCircularGauge you have to add respective elements to SfCircularGauge, which will be explained in the next section.

## Adding Header 

You can assign a unique header to **SfCircularGauge** by making use of **GaugeHeader** property and you can positioned it wherever you want using **GaugeHeaderPosition** and **HeaderAlignment** property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfCircularGauge GaugeHeaderPosition="0.45,0.8" HeaderAlignment="Custom">
            <syncfusion:SfCircularGauge.GaugeHeader>
                <TextBlock Text="Temperature (K)" 
                              Height="20" Width="150" 
                              FontSize="20" Foreground="White"/>
            </syncfusion:SfCircularGauge.GaugeHeader>
        </syncfusion:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}
    
            SfCircularGauge circularGauge = new SfCircularGauge();
            circularGauge.GaugeHeaderPosition = new Point(0.45, 0.8);
            circularGauge.HeaderAlignment = HeaderAlignment.Custom;
            TextBlock _textBlock = new TextBlock()
            {
                Text = "Temperature (K)",
                Height = 20,
                Width = 150,
                FontSize = 20,
                Foreground = new SolidColorBrush(Colors.White)
            };
            circularGauge.GaugeHeader = _textBlock;
            this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img9.png)

## Configuring Scales

You can configure the **CircularScale** elements by making use of following API’s available in SfCircularGage.

They are:

* StartAngle
* SweepAngle
* StartValue
* EndValue
* Interval
* TickStroke
* LabelStroke

{% tabs %}
{% highlight xaml %}

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <syncfusion:SfCircularGauge x:Name="gauge" GaugeHeaderPosition="0.45,0.8" HeaderAlignment="Custom" >

                <syncfusion:SfCircularGauge.GaugeHeader>

                    <TextBlock Text="Temperature (K)" 
                              Height="40" Width="150" 
                              FontSize="20" Foreground="White"/>

                </syncfusion:SfCircularGauge.GaugeHeader>
                <syncfusion:SfCircularGauge.Scales>
                    <syncfusion:CircularScale StartAngle="135" 
                                   SweepAngle="270" 
                                   StartValue="0"
                                   LabelStroke="White" TickStroke="White"
                                   EndValue="100"
                                   Interval="10">
                    </syncfusion:CircularScale>
                </syncfusion:SfCircularGauge.Scales>
            </syncfusion:SfCircularGauge>
        </Grid>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge();
            circularGauge.GaugeHeaderPosition = new Point(0.45, 0.8);
            circularGauge.HeaderAlignment = HeaderAlignment.Custom;
            CircularScale _mainscale = new CircularScale();
            _mainscale.StartAngle = 135;
            _mainscale.SweepAngle = 270;
            _mainscale.StartValue = 0;
            _mainscale.EndValue = 100;
            _mainscale.Interval = 10;
            circularGauge.Scales.Add(_mainscale);
            TextBlock _textBlock = new TextBlock()
            {
                Text = "Temperature (K)",
                Height = 20,
                Width = 150,
                FontSize = 20,
                Foreground = new SolidColorBrush(Colors.White)
            };
            circularGauge.GaugeHeader = _textBlock;
            this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img10.png)

## Adding Ranges 

You can add ranges to SfCircularGauge by creating ranges collection using **Ranges**.

{% tabs %}
{% highlight xaml %}
           <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <syncfusion:SfCircularGauge x:Name="gauge" GaugeHeaderPosition="0.45,0.8" HeaderAlignment="Custom" >

                <syncfusion:SfCircularGauge.GaugeHeader>

                    <TextBlock Text="Temperature (K)" 
                              Height="40" Width="150" 
                              FontSize="20" Foreground="White"/>

                </syncfusion:SfCircularGauge.GaugeHeader>
                <syncfusion:SfCircularGauge.Scales>
                    <syncfusion:CircularScale StartAngle="135" 
                                   SweepAngle="270" 
                                   StartValue="0"
                                   EndValue="100"
                                   Interval="10">

                        <syncfusion:CircularScale.Ranges>
                            <syncfusion:CircularRange StartValue="0" 
                                             EndValue="60" Stroke="#666666" />
                            <syncfusion:CircularRange StartValue="60" 
                                             EndValue="100" Stroke="#C1252C" />
                        </syncfusion:CircularScale.Ranges>
                    </syncfusion:CircularScale>
                </syncfusion:SfCircularGauge.Scales>
            </syncfusion:SfCircularGauge>
        </Grid>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge();
            circularGauge.GaugeHeaderPosition = new Point(0.45, 0.8);
            circularGauge.HeaderAlignment = HeaderAlignment.Custom;
            CircularScale _mainscale = new CircularScale();
            _mainscale.StartAngle = 135;
            _mainscale.SweepAngle = 270;
            _mainscale.StartValue = 0;
            _mainscale.EndValue = 100;
            _mainscale.Interval = 10;
            _mainscale.Ranges.Add(new CircularRange()
            {
                StartValue = 0,
                EndValue = 60,
                Stroke = new SolidColorBrush(Color.FromArgb(0XFF, 0X66, 0X66, 0X66))
            });
            _mainscale.Ranges.Add(new CircularRange()
            {
                StartValue = 60,
                EndValue = 100,
                Stroke = new SolidColorBrush(Color.FromArgb(0XFF, 0XC1, 0X25, 0X2C))
            });
            circularGauge.Scales.Add(_mainscale);
            TextBlock _textBlock = new TextBlock()
            {
                Text = "Temperature (K)",
                Height = 20,
                Width = 150,
                FontSize = 20,
                Foreground = new SolidColorBrush(Colors.White)
            };
            circularGauge.GaugeHeader = _textBlock;
            this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img11.png)


## Adding Pointers 

You can add Pointers to SfCircularGauge to point a values on the scale.

{% tabs %}
{% highlight xaml %}

            <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <syncfusion:SfCircularGauge x:Name="gauge" GaugeHeaderPosition="0.45,0.8" HeaderAlignment="Custom" >

                <syncfusion:SfCircularGauge.GaugeHeader>

                    <TextBlock Text="Temperature (K)" 
                              Height="40" Width="150" 
                              FontSize="20" Foreground="White"/>

                </syncfusion:SfCircularGauge.GaugeHeader>
                <syncfusion:SfCircularGauge.Scales>
                    <syncfusion:CircularScale StartAngle="135" 
                                   SweepAngle="270" 
                                   StartValue="0"
                                   EndValue="100"
                                   Interval="10">

                        <syncfusion:CircularScale.Ranges>
                            <syncfusion:CircularRange StartValue="0" 
                                             EndValue="60" Stroke="#666666" />
                            <syncfusion:CircularRange StartValue="60" 
                                             EndValue="100" Stroke="#C1252C" />
                        </syncfusion:CircularScale.Ranges>

                        <syncfusion:CircularScale.Pointers>
                            <syncfusion:CircularPointer PointerType="NeedlePointer" Value="10"/>
                        </syncfusion:CircularScale.Pointers>
                    </syncfusion:CircularScale>
                </syncfusion:SfCircularGauge.Scales>
            </syncfusion:SfCircularGauge>
        </Grid>

{% endhighlight %}

{% highlight c# %}

            SfCircularGauge circularGauge = new SfCircularGauge();
            circularGauge.GaugeHeaderPosition = new Point(0.45, 0.8);
            circularGauge.HeaderAlignment = HeaderAlignment.Custom;
            CircularScale _mainscale = new CircularScale();
            _mainscale.StartAngle = 135;
            _mainscale.SweepAngle = 270;
            _mainscale.StartValue = 0;
            _mainscale.EndValue = 100;
            _mainscale.Interval = 10;
            _mainscale.Ranges.Add(new CircularRange()
            {
                StartValue = 0,
                EndValue = 60,
                Stroke = new SolidColorBrush(Color.FromArgb(0XFF, 0X66, 0X66, 0X66))
            });
            _mainscale.Ranges.Add(new CircularRange()
            {
                StartValue = 60,
                EndValue = 100,
                Stroke = new SolidColorBrush(Color.FromArgb(0XFF, 0XC1, 0X25, 0X2C))
            });
            _mainscale.Pointers.Add(new CircularPointer()
            {
                PointerType = PointerType.NeedlePointer,
                Value = 10
            });
            circularGauge.Scales.Add(_mainscale);
            TextBlock _textBlock = new TextBlock()
            {
                Text = "Temperature (K)",
                Height = 20,
                Width = 150,
                FontSize = 20,
                Foreground = new SolidColorBrush(Colors.White)
            };
            circularGauge.GaugeHeader = _textBlock;
            this.Grid.Children.Add(circularGauge);

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img12.png)
