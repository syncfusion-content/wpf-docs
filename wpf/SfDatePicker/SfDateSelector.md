---
layout: post
title: Explains about DateSelector | SfDatePicker | WPF | Syncfusion
description: Explains about the DateSelector of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# SfDateSelector

The SfDateSelector control opens inside the drop-down popup.

![SfDateSelector](Features_images/Features_img3.png)


The visual elements of the date selector can be customized using the [SelectorStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorStyle.html) property.



## Header

The header property defines the top part of the SfDateSelector.

{% highlight xaml %}


	<syncfusion:SfDatePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

                    <Setter Property="Header" Value="Set your alarm"/>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>

	</syncfusion:SfDatePicker>

{% endhighlight %}

![Header](Features_images/Features_img4.png)




## HeaderTemplate

The header template property is used to decorate the header.

{% highlight xaml %}



	<syncfusion:SfDatePicker VerticalAlignment="Center" 

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfDatePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfDateSelector">

                    <Setter Property="HeaderTemplate">

                        <Setter.Value>

                            <DataTemplate>

                                <StackPanel Orientation="Horizontal">

                                    <TextBlock Text="&#xE170;" 

                                           VerticalAlignment="Top"

                                           Margin="5"

                                           FontSize="22"

                                           FontFamily="Segoe UI Symbol"/>

                                    <TextBlock Text="Set your alarm" 

                                           VerticalAlignment="Top"

                                           Margin="5"

                                           FontSize="22"

                                           />

                                </StackPanel>

                            </DataTemplate>

                        </Setter.Value>

                    </Setter>

                </Style>

            </syncfusion:SfDatePicker.SelectorStyle>        
            </syncfusion:SfDatePicker>

{% endhighlight  %}



![HeaderTemplate](Features_images/Features_img5.png)




## Cell template

The cell template property is used to decorate the selection box with custom visuals. 

N> The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.

## DayCellTemplate

The [DayCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~DayCellTemplate.html) property is used to decorate the day cell selection box.

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

![Day cell template](Features_images/Features_img7.png)


## MonthCellTemplate

 The [MonthCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~MonthCellTemplate.html) property is used to decorate the month cell selection box. 

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

![Month cell template](Features_images/Features_img8.png)



## YearCellTemplate

The [YearCellTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector~YearCellTemplate.html) property is used to decorate the year cell selection box.

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
			
![Year cell template](Features_images/Features_img9.png)