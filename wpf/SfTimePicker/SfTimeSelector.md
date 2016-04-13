---
layout: post
title: Explains about TimeSelector of SfTimePicker control for WPF
description: Explains about TimeSelector of SfTimePicker control for WPF
platform: wpf
control: SfTimePicker
documentation: ug
---

# SfTimeSelector

The SfTimeSelector control opens inside the popup window.

![](Features_images/Features_img3.png)

The visual elements of the time selector can be customized using the property SelectorStyle.


## Header

The header property defines the top part of the time selector.
{% highlight xaml %}

	<syncfusion:SfTimePicker VerticalAlignment="Center"

                       HorizontalAlignment="Center"

                       Width="200">

       <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

                    <Setter Property="Header" Value="Set your alarm"/>

                </Style>

       </syncfusion:SfTimePicker.SelectorStyle>

	</syncfusion:SfTimePicker >

{% endhighlight %}

![](Features_images/Features_img4.png)


## HeaderTemplate

The HeaderTemplate property is used to decorate the header.

{% highlight xaml %}

	<syncfusion:SfTimePicker VerticalAlignment="Center" 

                               HorizontalAlignment="Center"

                               Width="200">

            <syncfusion:SfTimePicker.SelectorStyle>

                <Style TargetType="syncfusion:SfTimeSelector">

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

            </syncfusion:SfTimePicker.SelectorStyle>  
			</syncfusion:SfTimePicker>
			

{% endhighlight %}

![](Features_images/Features_img5.png)


## Cell template

The cell template property is used to decorate the selection box with custom visuals. 


N>  The DataContext of Selection box is Syncfusion.UI.Xaml.Primitives.DateTimeWrapper.



## HourCellTemplate

 The HourCellTemplate property is used to decorate the hour cell selection box.

{% highlight xaml %}

	<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

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

![](Features_images/Features_img7.png)


## MinuteCellTemplate

The MinuteCellTemplate property is used to decorate the minute cell selection box

{% highlight xaml %}

       
	<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

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

![](Features_images/Features_img8.png)


## MeridiemCellTemplate

The MeridiemCellTemplate property is used to decorate the meridiem cell selection box. 

{% highlight xaml %}

	<syncfusion:SfTimePicker VerticalAlignment="Center"

                               HorizontalAlignment="Center"

                               Width="200">

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

![](Features_images/Features_img9.png)


## Setting Incremental values

To set minute and second values in SfTimeSelector with incremental values, use MinuteInterval and SecondsInterval properties respectively.

### MinuteInterval


MinuteInterval property is used to set interval for minute values in SfTimeSelector.

### SecondsInterval


SecondsInterval property is used to set interval for second values in SfTimeSelector.

{% tabs %}
{% highlight xaml %}


	<syncfusion:SfTimeSelector FormatString="hh:MM:ss tt" MinuteInterval="2" SecondsInterval="10"/>

{%endhighlight%}

{%highlight c#%}

	SfTimeSelector timeSelector = new SfTimeSelector();

	timeSelector.FormatString= "hh:MM:ss tt";

	timeSelector.MinuteInterval=2;

	timeSelector.SecondsInterval=10;

{% endhighlight %}

{% endtabs %}

![](Features_images/Features_img10.png)



![](Features_images/Features_img11.png)
