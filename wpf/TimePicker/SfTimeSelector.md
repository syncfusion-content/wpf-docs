---
layout: post
title: Explains about TimeSelector in WPF SfTimePicker control | Syncfusion
description: This page explains about how to customize the time selector and select a time in various ways from the WPF SfTimePicker control.
platform: wpf
control: SfTimePicker
documentation: ug
---

# TimeSelector in WPF SfTimePicker

The [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) control opens inside the drop-down popup.

![SfTimeSelector](Features_images/Features_img3.png)

The visual elements of the time selector can be customized using the [SelectorStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SelectorStyle.html) property.

## Change the Cell templates

We can changes the template for the each selection hour, minute or meridiem list by using the `HourCellTemplate`,  `MinuteCellTemplate` or `MeridiemCellTemplate` which are available in the `SfTimeSelector`.

N> The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.

## Change the HourCell Template

We can change the hour selector template by using the [HourCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~HourCellTemplate.html) property. In that, we can add any image, icon or text with the hour values.

{% highlight xaml %}

<syncfusion:SfTimePicker VerticalAlignment="Center"
                         HorizontalAlignment="Center"
                         Width="200"
                         Name="sfTimePicker">

    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <Setter Property="HourCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                                       HorizontalAlignment="Right"
                                       Margin="5"
                                       FontSize="22"
                                       FontFamily="Segoe UI Symbol"
                                       Text="&#xE170;"/>

                            <TextBlock Text="{Binding HourNumber}" 
                                       VerticalAlignment="Bottom" 
                                       Margin="5"
                                       FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>

{% endhighlight %}

![SfSpellChecker with Hour cell template](Features_images/Features_img7.png)


## Change the MinuteCell Template

We can change the minute selector template by using the [MinuteCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~MinuteCellTemplate.html) property. In that, we can add any image, icon or text with the minute values.

{% highlight xaml %}

<syncfusion:SfTimePicker VerticalAlignment="Center"
                         HorizontalAlignment="Center"
                         Width="200"
                         Name="sfTimePicker">

    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <Setter Property="MinuteCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                               HorizontalAlignment="Right"
                               Margin="5"
                               FontSize="22"
                               FontFamily="Segoe UI Symbol"
                               Text="&#xE170;"/>

                            <TextBlock Text="{Binding MinuteNumber}" 
                               VerticalAlignment="Bottom" 
                               Margin="5"
                               FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>

{% endhighlight %}

![SfSpellChecker with Minute cell template](Features_images/Features_img8.png)

## Change the MeridiemCell Template

We can change the meridiem selector template by using the [MeridiemCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~MeridiemCellTemplate.html) property. In that, we can add any image, icon or text with the meridiem values.

{% highlight xaml %}

<syncfusion:SfTimePicker VerticalAlignment="Center"
                         HorizontalAlignment="Center"
                         Width="200"
                         Name="sfTimePicker">

    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <Setter Property="MeridiemCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                               HorizontalAlignment="Right"
                               Margin="5"
                               FontSize="22"
                               FontFamily="Segoe UI Symbol"
                               Text="&#xE170;"/>

                            <TextBlock Text="{Binding AmPmString}" 
                               VerticalAlignment="Bottom" 
                               Margin="5"
                               FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>

{% endhighlight %}
			
![SfSpellChecker with Meridiem cell template](Features_images/Features_img9.png)

## Change size of cells

We can change the cell size in the `SfTimeSelector` control by setting the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SelectorItemWidth.html) and [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SelectorItemHeight.html) properties. The default value of the `SelectorItemWidth` and `SelectorItemHeight` properties is `30` and `30`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:SfTimePicker SelectorItemWidth="60" 
                         SelectorItemHeight="60" 
	                     x:Name="sfTimePicker"/>

{% endhighlight %}
{% highlight c# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.SelectorItemWidth = 60;
sfTimePicker.SelectorItemHeight = 60;

{% endhighlight %}
{% endtabs %}

![SfTimeSelector item width and height changed](Features_images/SelectorItemWidth.png)

## TimeSelector item spacing
 
We can change the space between `SfTimeSelector` hour, minutes and meridiem items by using the [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SelectorItemSpacing.html)  property. The default value of the `SelectorItemSpacing` property is `4`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfTimePicker SelectorItemSpacing="50" 
	                     x:Name="sfTimePicker"/>

{% endhighlight %}
{% highlight c# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.SelectorItemSpacing = 50;

{% endhighlight %}
{% endtabs %}

![SfTimeSelector item with custom spacing](Customizing-DropDown_images/SelectorItemSpacing.png)

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/SfTimeSelector-templates) to download the sample that showcases the `SfTimeSelector` template customization. 

## OK and Cancel button visibility

The selected time from the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) can be updated in the [SfTimePicker.Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~Value.html) property on after clicking `OK` buttons. If we want to hide the `Ok` and `Cancel` buttons, you can use the 
[SfTimeSelector.ShowDoneButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~ShowDoneButton.html) and [SfTimeSelector.ShowCancelButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector~ShowCancelButton.html) properties values as `false`. The default value of `SfTimeSelector.ShowDoneButton` and `SfTimeSelector.ShowCancelButton` properties values is `true`.

{% highlight XAML %}

<syncfusion:SfTimePicker Name="sfTimePicker" 
                         IsDropDownOpen="True"
                         Width="200"
                         Name="sfTimePicker">
    <syncfusion:SfTimePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfTimeSelector">
            <!--Ok button hided-->
            <Setter Property="ShowDoneButton" Value="False"/>
            <!--Cancel button hided-->
            <Setter Property="ShowCancelButton" Value="False"/>
        </Style>
    </syncfusion:SfTimePicker.SelectorStyle>
</syncfusion:SfTimePicker>
		
{% endhighlight %}

![SfTimePicker hides the cancel and done button](Features_images/Features_img11.png)

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/SfTimeSelector-footer) to download the sample that showcases the `OK` and `Cancel` button visibility.