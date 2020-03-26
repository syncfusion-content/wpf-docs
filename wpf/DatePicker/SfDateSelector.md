---
layout: post
title: Explains about DateSelector | SfDatePicker | WPF | Syncfusion
description: Explains about the DateSelector of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# SfDateSelector in the SfDatePicker

The [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) control opens inside the drop-down popup.

![SfDateSelector](Features_images/Features_img3.png)

The visual elements of the date selector can be customized using the [SelectorStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorStyle.html) property.

## Change the Cell templates

We can changes the template for the each selection Date, Month or Year list by the `DayCellTemplate`, `MonthCellTemplate` or `YearCellTemplate` which are available in the `SfDateSelector`.

N> The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.

## Change the DayCell Template

We can change the date selector template by using the [DayCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~DayCellTemplate.html) property. In that, we can add any image, icon or text with the day number.

{% highlight xaml %}

<syncfusion:SfDatePicker VerticalAlignment="Center"
                         HorizontalAlignment="Center"
                         Width="200">

    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="DayCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                                       HorizontalAlignment="Right"
                                       Margin="5"
                                       FontSize="22"
                                       FontFamily="Segoe UI Symbol"
                                       Text="&#xE170;"/>

                            <TextBlock Text="{Binding DayNumber}" 
                                       VerticalAlignment="Bottom" 
                                       Margin="5"
                                       FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight %}

![SfSpellChecker with Day cell template](Features_images/Features_img7.png)


## Change the MonthCell Template

We can change the month selector template by using the [MonthCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~MonthCellTemplate.html) property. In that, we can add any image, icon or text with the month number.

{% highlight xaml %}

<syncfusion:SfDatePicker VerticalAlignment="Center"
                 HorizontalAlignment="Center"
                 Width="200">

    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="MonthCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                               HorizontalAlignment="Right"
                               Margin="5"
                               FontSize="22"
                               FontFamily="Segoe UI Symbol"
                               Text="&#xE170;"/>

                            <TextBlock Text="{Binding MonthNumber}" 
                               VerticalAlignment="Bottom" 
                               Margin="5"
                               FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight %}

![SfSpellChecker with Month cell template](Features_images/Features_img8.png)

## Change the YearCell Template

We can change the year selector template by using the [YearCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~YearCellTemplate.html) property. In that, we can add any image, icon or text with the year number.

{% highlight xaml %}

<syncfusion:SfDatePicker VerticalAlignment="Center"
                 HorizontalAlignment="Center"
                 Width="200">

    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="YearCellTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Grid>
                            <TextBlock VerticalAlignment="Top" 
                               HorizontalAlignment="Right"
                               Margin="5"
                               FontSize="22"
                               FontFamily="Segoe UI Symbol"
                               Text="&#xE170;"/>

                            <TextBlock Text="{Binding YearNumber}" 
                               VerticalAlignment="Bottom" 
                               Margin="5"
                               FontSize="22"/>
                        </Grid>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight %}
			
![SfSpellChecker with Year cell template](Features_images/Features_img9.png)

Click [here]() to download the sample that showcases the `SfDateSelector` template customization. 