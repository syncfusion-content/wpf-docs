---
layout: post
title: Date Selector in WPF DatePicker control | Syncfusion
description: Learn here all about Date Selector support in Syncfusion WPF DatePicker (SfDatePicker) control and more.
platform: wpf
control: SfDatePicker
documentation: ug
---

# Date Selector in WPF DatePicker (SfDatePicker)

The [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html) is a sub-control of [SfDatePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html) which opens inside the drop-down popup and used to select the date for the `SfDatePicker`. It contains the date, month and year selection cells for select the date. The selected date of the `SfDateSelector` is assigned to the [SfDatePicker.Value](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_Value) property. 

![SfDateSelector](Features_images/Features_img3.png)

The visual elements of the date selector can be customized using the [SelectorStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_SelectorStyle) property.

## Change the Cell templates

We can changes the template for the Date, Month or Year selector by using the `DayCellTemplate`, `MonthCellTemplate` or `YearCellTemplate` which are available in the `SfDateSelector`.

N> The DataContext of Month, Date and Year selection cell is [DateTimeWrapper](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Primitives.DateTimeWrapper.html).

## Change the DayCell Template

We can change the day selector template by using the [DayCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html#Syncfusion_Windows_Controls_Input_SfDateSelector_DayCellTemplate) property. In that, we can add like image, icon or text with the day numbers.

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

We can change the month selector template by using the [MonthCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html#Syncfusion_Windows_Controls_Input_SfDateSelector_MonthCellTemplate) property. In that, we can add like image, icon or text with the month numbers.

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

We can change the year selector template by using the [YearCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html#Syncfusion_Windows_Controls_Input_SfDateSelector_YearCellTemplate) property. In that, we can add like image, icon or text with the year numbers.

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

We can change the cell size in the `SfDateSelector` control by setting the [SelectorItemWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_SelectorItemWidth) and [SelectorItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_SelectorItemHeight) properties. The default value of the `SelectorItemWidth` and `SelectorItemHeight` properties is `80` and `70`. 

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
 
We can change the space between `SfDateSelector` date, month and year items by using the [SelectorItemSpacing](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_SelectorItemSpacing) property. The default value of the `SelectorItemSpacing` property is `4`.

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

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/DateSelectorTemplates) to download the sample that showcases the `SfDateSelector` template customization. 
