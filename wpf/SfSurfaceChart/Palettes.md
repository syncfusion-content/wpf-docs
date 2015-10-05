# Palettes

Surface chart provides options to apply different kinds of palettes.

Some of the predefined palettes include:

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

### Applying Predefined Brushes

Using the above palette you can apply a set of predefined brushes to surface chart as shown in the following code example. 

{% highlight xml %}

<chart:SfSurfaceChart Palette="Metro" />
	
{% endhighlight %}

![C:/Users/sheiksyedm/Desktop/Surface_Doc_Img/Palette1.png](surface_chart_images/surface_chart_img12.jpeg)


### Applying Custom Brushes

The custom palette option enables you to define your own color brushes for the Palette using ColorModel property as given in the following code example.

{% highlight xml %}

<chart:SfSurfaceChart Palette="Custom" >
         <Syncfusion:SfSurfaceChart.ColorModel>
                    <Syncfusion:ChartColorModel>
                        <Syncfusion:ChartColorModel.CustomBrushes>
                            <SolidColorBrush Color="Red"/>
                            <SolidColorBrush Color="DarkOrange"/>
                            <SolidColorBrush Color="Yellow"/>
                            <SolidColorBrush Color="Lime"/>
                            <SolidColorBrush Color="Green"/>
                        </Syncfusion:ChartColorModel.CustomBrushes>
                    </Syncfusion:ChartColorModel>
       </Syncfusion:SfSurfaceChart.ColorModel>
<chart:SfSurfaceChart />
	
{% endhighlight %}

![C:/Users/sheiksyedm/Desktop/Surface_Doc_Img/CustomPalette1.png](surface_chart_images/surface_chart_img13.jpeg)