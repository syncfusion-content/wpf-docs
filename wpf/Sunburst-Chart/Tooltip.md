---

layout: post
title: Tooltip in WPF Sunburst Chart control | Syncfusion
description: Learn here all about Tooltip support in Syncfusion WPF Sunburst Chart (SfSunburstChart) control and more.
platform: wpf 
control: SfSunburstChart 
documentation: ug

---

# Tooltip in WPF Sunburst Chart (SfSunburstChart)

ToolTip allows you to display any information over a sunburst segment. It appears when mouse hovered over or touch any chart segment. By default, it displays the corresponding segment category name and its value. Visibility of the tooltip can be controlled using [`ShowToolTip`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_ShowToolTip) property.

{% tabs %}

{% highlight xaml %}

      <sunburst:SfSunburstChart.Behaviors>

                <sunburst:SunburstToolTipBehavior ShowToolTip="True"/>

            </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.ShowToolTip = true;
chart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}


![Tooltip_img1](Tooltip_images/Tooltip_img1.jpeg)


## Aligning the ToolTip

The tooltip position can be aligned with respect to the cursor position by using [`HorizontalAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_HorizontalAlignment) and [`VerticalAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_VerticalAlignment) properties.

### HorizontalAlignment

The following code shows, how to position the tooltip to right of the cursor.

{% tabs %}

{% highlight xaml %}

      <sunburst:SfSunburstChart.Behaviors>

         <sunburst:SunburstToolTipBehavior HorizontalAlignment="Right"/>

    </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.HorizontalAlignment = HorizontalAlignment.Right;
sunburstChart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}

![Tooltip_img2](Tooltip_images/Tooltip_img2.jpeg)


### VerticalAlignment

The following code shows, how to position the tooltip to bottom of the cursor.

{% highlight xaml %}

    <sunburst:SfSunburstChart.Behaviors>

     <sunburst:SunburstToolTipBehavior VerticalAlignment="Bottom"  />

    </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

![Tooltip_img3](Tooltip_images/Tooltip_img3.jpeg)


## VerticalOffset and HorizontalOffset

The tooltip position can be customized to a custom position from the cursor using the [`HorizontalOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_HorizontalOffset) and [`VerticalOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_VerticalOffset) properties.

{% tabs %}

{% highlight xaml %}

         <sunburst:SfSunburstChart.Behaviors>

       <sunburst:SunburstToolTipBehavior HorizontalOffset="50"
                                         VerticalOffset="50"/>

        </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.HorizontalOffset = 50;
tooltip.VerticalOffset = 50;
sunburstChart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}


![Tooltip_img4](Tooltip_images/Tooltip_img4.jpeg)


### TooltipDuration

You can set display duration for tooltip by using the [`ShowDuration`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_ShowDuration) property.

{% tabs %}

{% highlight xaml %}

         <sunburst:SfSunburstChart.Behaviors>

            <sunburst:SunburstToolTipBehavior ShowDuration="6000"/>

          </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.ShowDuration = 6000;
chart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}

## Show Delay

We can set the initial display delay for Tooltip by using [`InitialShowDelay`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_InitialShowDelay) property as like in below code. 

{% tabs %}

{% highlight xaml %}

           <sunburst:SfSunburstChart.Behaviors>

            <sunburst:SunburstToolTipBehavior InitialShowDelay="500"/>
                
    </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.InitialShowDelay = 500;
sunburstChart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}

## Animation for Tooltip

You can enable the translate animation for Tooltip by using [`EnableAnimation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_EnableAnimation) and [`AnimationDuration`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_AnimationDuration) property.

{% tabs %}

{% highlight xaml %}

    <sunburst:SfSunburstChart.Behaviors>

     <sunburst:SunburstToolTipBehavior EnableAnimation="True" 
                                       AnimationDuration="5000"/>

    </sunburst:SfSunburstChart.Behaviors>

{% endhighlight %}

{% highlight c# %}

SunburstToolTipBehavior tooltip = new SunburstToolTipBehavior();
tooltip.EnableAnimation = true;
tooltip.AnimationDuration = 5000;
sunburstChart.Behaviors.Add(tooltip);

{% endhighlight %}

{% endtabs %}

## Customize the Tooltip

You can customize the default appearance of the tooltip by applying the [`TooltipTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SunburstChart.SunburstToolTipBehavior.html#Syncfusion_UI_Xaml_SunburstChart_SunburstToolTipBehavior_ToolTipTemplate) property.

{% highlight xaml %}

    <sunburst:SunburstToolTipBehavior.ToolTipTemplate>
                        
        <DataTemplate>
                            
               <Border Background="{Binding Interior}"
                       BorderBrush="{Binding Interior}"
                       BorderThickness="4">
                       <StackPanel>
                           <StackPanel Orientation="Horizontal">
                               <TextBlock Text="Category : "/>
                               <TextBlock Text="{Binding Category}"/>
                            </StackPanel>
                            <StackPanel Orientation="Horizontal">
                                <TextBlock Text="Value : "/>
                                <TextBlock Text="{Binding Value}"/>
                            </StackPanel>
                        </StackPanel>
               </Border>
                            
       </DataTemplate>
                        
    </sunburst:SunburstToolTipBehavior.ToolTipTemplate>

{% endhighlight %}

![Tooltip_img5](Tooltip_images/Tooltip_img5.jpeg)


