---

layout: post
title: Palette in WPF Sunburst Chart control | Syncfusion
description: Learn here all about Palette support in Syncfusion WPF Sunburst Chart (SfSunburstChart) control and more.
platform: wpf 
control: SfSunburstChart 
documentation: ug

---

# Palette in WPF Sunburst Chart (SfSunburstChart)

Sunburst chart provides support to apply different types of palettes. You can define the palettes by using [`Palette`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SfSunburstChart.html#Syncfusion_UI_Xaml_SunburstChart_SfSunburstChart_Palette) property.

We have some predefined palette such as

* Metro
* AutumnBrights
* FloraHues
* Pineapple
* TomotoSpectrum
* RedChrome
* PurpleChrome
* BlueChrome
* GreenChrome
* Elite
* LightCandy
* SandyBeach

## Applying palette to the chart

Each palette applies a set of predefined brushes to the sunburst chart in a predefined order. The following code shows how to set predefined palette for sunburst chart.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart ItemsSource="{Binding Data}"
                          ValueMemberPath="Value" 
                          Palette="SandyBeach">
</sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight c# %}

sunburstChart.Palette = SunburstColorPalette.SandyBeach;

{% endhighlight %}

{% endtabs %}

![Palettes_img1](Palettes_images/Palettes_img1.jpeg)


## Custom Palette

Sunburst chart provides option which enables you to define your own color brushes with your preferred order for the Palette, using [`ColorModel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SfSunburstChart.html#Syncfusion_UI_Xaml_SunburstChart_SfSunburstChart_ColorModel) as shown in the following code example.

{% tabs %}

{% highlight xaml %}

<sunburst:SfSunburstChart Palette="Custom">

      <sunburst:SfSunburstChart.ColorModel>

                <sunburst:SunburstColorModel>
                    
                    <sunburst:SunburstColorModel.CustomBrushes>
                        
                        <LinearGradientBrush>
                            <GradientStop Color="DeepPink" Offset="0"/>
                            <GradientStop Color="Gray" Offset="1"/>
                        </LinearGradientBrush>
                        
                        <LinearGradientBrush>
                            <GradientStop Color="Green" Offset="0"/>
                            <GradientStop Color="Yellow" Offset="1"/>
                        </LinearGradientBrush>

                        <LinearGradientBrush>
                            <GradientStop Color="Orange" Offset="0"/>
                            <GradientStop Color="Brown" Offset="1"/>
                        </LinearGradientBrush>

                        <LinearGradientBrush>
                            <GradientStop Color="DarkViolet" Offset="0"/>
                            <GradientStop Color="White" Offset="1"/>
                        </LinearGradientBrush>

                    </sunburst:SunburstColorModel.CustomBrushes>
                    
                </sunburst:SunburstColorModel>
                
            </sunburst:SfSunburstChart.ColorModel>

    </sunburst:SfSunburstChart>

{% endhighlight %}

{% highlight c# %}

            chart.Palette = SunburstColorPalette.Custom;

            SunburstColorModel colorModel = new SunburstColorModel();
            LinearGradientBrush brush1 = new LinearGradientBrush();
            brush1.GradientStops.Add(new GradientStop() { Color = Colors.DeepPink, Offset = 0 });
            brush1.GradientStops.Add(new GradientStop() { Color = Colors.Gray, Offset = 1 });

            LinearGradientBrush brush2 = new LinearGradientBrush();
            brush2.GradientStops.Add(new GradientStop() { Color = Colors.Green, Offset = 0 });
            brush2.GradientStops.Add(new GradientStop() { Color = Colors.Yellow, Offset = 1 });

            LinearGradientBrush brush3 = new LinearGradientBrush();
            brush3.GradientStops.Add(new GradientStop() { Color = Colors.Orange, Offset = 0 });
            brush3.GradientStops.Add(new GradientStop() { Color = Colors.Brown, Offset = 1 });

            LinearGradientBrush brush4 = new LinearGradientBrush();
            brush4.GradientStops.Add(new GradientStop() { Color = Colors.DarkViolet, Offset = 0 });
            brush4.GradientStops.Add(new GradientStop() { Color = Colors.White, Offset = 1 });

            colorModel.CustomBrushes.Add(brush1);
            colorModel.CustomBrushes.Add(brush2);
            colorModel.CustomBrushes.Add(brush3);
            colorModel.CustomBrushes.Add(brush4);

            chart.ColorModel = colorModel;

{% endhighlight %}

{% endtabs %}

![Palettes_img2](Palettes_images/Palettes_img2.jpeg)

N> Before applying the color model, you need to set the palette value as Custom.

