---
layout: post
title: Explains about DateSelector in WPF SfDatePicker control | Syncfusion
description: This page explains about how to customize the date selector and select a date in various ways from the WPF SfDatePicker control.
platform: wpf
control: SfDatePicker
documentation: ug
---

# DateSelector in WPF SfDatePicker

The [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) control opens inside the drop-down popup.

![SfDateSelector](Features_images/Features_img3.png)

The visual elements of the date selector can be customized using the [SelectorStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorStyle.html) property.

## Change the Cell templates

We can changes the template for the each selection Date, Month or Year list by using the `DayCellTemplate`, `MonthCellTemplate` or `YearCellTemplate` which are available in the `SfDateSelector`.

N> The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.

## Change the DayCell Template

We can change the day selector template by using the [DayCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~DayCellTemplate.html) property. In that, we can add any image, icon or text with the day values.

{% highlight xaml %}

<syncfusion:SfDatePicker VerticalAlignment="Center"
                         HorizontalAlignment="Center"
                         Width="200"
                         Name="sfDatePicker">

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
                         Width="200"
                         Name="sfDatePicker">

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
                         Width="200"
                         Name="sfDatePicker">

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

## Change size of cells

We can change the cell size in the `SfDateSelector` control by setting the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemWidth.html) and [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemHeight.html) properties. The default value of the `SelectorItemWidth` and `SelectorItemHeight` properties is `80` and `70`. 

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker SelectorItemWidth="100" 
                         SelectorItemHeight="100" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorItemWidth = 100;
sfDatePicker.SelectorItemHeight = 100;

{% endhighlight %}
{% endtabs %}

![SfDateSelector item width and height changed](Customizing-DropDown_images/SelectorItemWidth.png)

## DateSelector item spacing
 
We can change the space between `SfDateSelector` date, month and year items by using the [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorItemSpacing.html) property. The default value of the `SelectorItemSpacing` property is `4`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker SelectorItemSpacing="50" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorItemSpacing = 50;

{% endhighlight %}
{% endtabs %}

![SfDateSelector item with custom spacing](Customizing-DropDown_images/SelectorItemSpacing.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/SfDateSelector-templates) to download the sample that showcases the `SfDateSelector` template customization. 

## OK and Cancel button visibility

The selected date from the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) can be updated in the [SfDatePicker.Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Value.html) property on after clicking `OK` buttons. If we want to hide the `Ok` and `Cancel` buttons, you can use the 
[SfDateSelector.ShowDoneButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~ShowDoneButton.html) and [SfDateSelector.ShowCancelButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~ShowCancelButton.html) properties values as `false`. The default value of `SfDateSelector.ShowDoneButton` and `SfDateSelector.ShowCancelButton` properties values is `true`.

{% highlight XAML %}

<syncfusion:SfDatePicker Name="sfdatePicker" 
                         IsDropDownOpen="True"
                         Width="200"
                         Name="sfDatePicker">
    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <!--Ok button hided-->
            <Setter Property="ShowDoneButton" Value="False"/>
            <!--Cancel button hided-->
            <Setter Property="ShowCancelButton" Value="False"/>
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>
		
{% endhighlight %}

![SfdatePicker hides the cancel and done button](Features_images/Features_img11.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/SfDateSelector-footer) to download the sample that showcases the `OK` and `Cancel` button visibility.