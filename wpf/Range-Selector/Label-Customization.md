---
layout: post
title: Label Customization | SfDateTimeRangeNavigator | wpf | Syncfusion
description: This section explores how to customize the label with Intervals, Formatters and also visibility of label bars in DateTimeRangeNavigator
platform: wpf
control: SfDateTimeRangeNavigator
documentation: ug
---

# Label Customization in DateTimeRangeNavigator

The date-time range navigator control helps users to visualize large data in a simplified manner. The timespan of data is represented in the higher level bar and lower level bar. The timespan calculates data smartly and provides suitable date-time format and interval, by default.

Users can also set the interval as needed for their data. This can be done by using the Interval property as demonstrated in the following code sample. 

**Properties**

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
{{'[`IntervalType`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Interval.html#Syncfusion_UI_Xaml_Charts_Interval_IntervalType)'| markdownify }}</td><td>
Sets the interval type that needs to be displayed in the navigator.</td></tr>
<tr>
<td>
{{'[`LabelFormatters`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Interval.html#Syncfusion_UI_Xaml_Charts_Interval_LabelFormatters)'| markdownify }}</td><td>
Gets or sets string collection to set the label format for the navigator labels.</td></tr>
</table>

{% tabs %}

{% highlight xaml %}

<syncfusion:SfDateTimeRangeNavigator x:Name="rangepicker" ItemsSource="{Binding power}"  XBindingPath="Date" >

	<syncfusion:SfDateTimeRangeNavigator.Intervals> 

		<syncfusion:Interval IntervalType="Quarter"/>

		<syncfusion:Interval IntervalType="Month"/>

	</syncfusion:SfDateTimeRangeNavigator.Intervals>

	<syncfusion:SfDateTimeRangeNavigator.Content>

		<syncfusion:SfChart   >

			<syncfusion:SfChart.PrimaryAxis>

				<syncfusion:CategoryAxis Visibility="Collapsed" />

			</syncfusion:SfChart.PrimaryAxis>

			<syncfusion:SfChart.SecondaryAxis>

				<syncfusion:NumericalAxis Visibility="Collapsed" />

			</syncfusion:SfChart.SecondaryAxis>

			<syncfusion:FastLineBitmapSeries XBindingPath="Date" ItemsSource="{Binding power}" YBindingPath="Value">

				</syncfusion:FastLineBitmapSeries>

		</syncfusion:SfChart>

		</syncfusion:SfDateTimeRangeNavigator.Content>

</syncfusion:SfDateTimeRangeNavigator>

{% endhighlight  %}

{% highlight c# %}

SfChart chart = new SfChart();

chart.PrimaryAxis = new CategoryAxis() { Visibility = Visibility.Collapsed };

chart.SecondaryAxis = new NumericalAxis() { Visibility = Visibility.Collapsed };

FastLineBitmapSeries candleSeries = new FastLineBitmapSeries()
{

	ItemsSource = new ViewModel().Power,

	XBindingPath = "Date",

	YBindingPath = "Value"

};

chart.Series.Add(candleSeries);

SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

	ItemsSource = new ViewModel().Power,

	XBindingPath = "Date"

};

rangeNavigator.Intervals.Add(new Interval() { IntervalType = NavigatorIntervalType.Quarter });

rangeNavigator.Intervals.Add(new Interval() { IntervalType = NavigatorIntervalType.Month });

rangeNavigator.Content = chart;

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates only Quarter and Month intervals in the navigator.

![Label customization in WPF SfDateTimeRangeNavigator](Label-Customization_images/Label-Customization_img1.png)

The interval can be set in the following types: 

* [`Year`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Quarter`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Month`(https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Week`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Day`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)
* [`Hour`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.NavigatorIntervalType.html)

The auto timespan format simplifies the visual representation of data when zooming in with the following formats:

**Intervals**

<table>
<tr>
<th>
Intervals</th><th>
Examples</th></tr>
<tr>
<td>
HourInterval</td><td>
7/21/2011 12:00:00 AM > 12 AM7/21/2011 12:00:00 AM > 12A</td></tr>
<tr>
<td>
DayInterval</td><td>
7/21/2011 12:00:00 AM > Thursday, July 21, 20117/21/2011 12:00:00 AM > Thu, Jul 21, 20117/21/2011 12:00:00 AM > Thursday, 217/21/2011 12:00:00 AM > Thu, 21</td></tr>
<tr>
<td>
WeekInterval</td><td>
7/21/2011 12:00:00 AM > Week 29, July, 20117/21/2011 12:00:00 AM > Week 29, Jul, 20117/21/2011 12:00:00 AM > Week 297/21/2011 12:00:00 AM > W29</td></tr>
<tr>
<td>
MonthInterval</td><td>
7/21/2011 12:00:00 AM > July, 20117/21/2011 12:00:00 AM > July7/21/2011 12:00:00 AM > Jul7/21/2011 12:00:00 AM > J</td></tr>
<tr>
<td>
QuarterInterval</td><td>
7/21/2011 12:00:00 AM > Quarter 3, 20117/21/2011 12:00:00 AM > Quarter 37/21/2011 12:00:00 AM > Q3, 20117/21/2011 12:00:00 AM > Q3</td></tr>
<tr>
<td>
YearInterval</td><td>
7/21/2011 12:00:00 AM > 2011</td></tr>
</table>


**Label style customization**

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
LabelBarStyle</td><td>
Allows to customize the label style using the LabelBarStyle property, and this property can be applied to the [`HigherLevelBarStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_HigherLevelBarStyle) or [`LowerLevelBarStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfDateTimeRangeNavigator.html#Syncfusion_UI_Xaml_Charts_SfDateTimeRangeNavigator_LowerLevelBarStyle).</td></tr>
<tr>
<td>
{{'[`SelectedLabelStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_SelectedLabelStyle)'| markdownify }}</td><td>
Defines the label style for labels in the selected region.</td></tr>
<tr>
<td>
{{'[`Position`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LabelBarStyle.html#Syncfusion_UI_Xaml_Charts_LabelBarStyle_Position)'| markdownify }}</td><td>
Positions the upper and lower labels inside or outside the label bar.</td></tr>
</table>

 {% tabs %}

{% highlight xaml %}

<syncfusion:SfDateTimeRangeNavigator x:Name="navigator">

    syncfusion:SfRangeNavigator.Resources>

        <Style TargetType="TextBlock" x:Key="labelStyle">

            <Setter Property="FontSize" Value="10"/>

        </Style>
                
    </syncfusion:SfRangeNavigator.Resources>

    <syncfusion:SfDateTimeRangeNavigator.HigherLevelBarStyle>

            <syncfusion:LabelBarStyle Background="Red" 
                                          
                                      LabelHorizontalAlignment="Left"  
                                          
                                      SelectedLabelStyle="{StaticResource labelStyle}"/>

    </syncfusion:SfDateTimeRangeNavigator.HigherLevelBarStyle>

</syncfusion:SfDateTimeRangeNavigator>

{% endhighlight %}

{% highlight c# %}

LabelBarStyle barStyle = new LabelBarStyle()
{

	LabelHorizontalAlignment = HorizontalAlignment.Left,

	Background = new SolidColorBrush(Colors.Red),

	SelectedLabelStyle = grid.Resources["labelStyle"] as Style

};


SfDateTimeRangeNavigator rangeNavigator = new SfDateTimeRangeNavigator()
{

	HigherLevelBarStyle = barStyle

};

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates setting the Label HorizontalAlignment to left.

![Label customization in WPF SfDateTimeRangeNavigator](Label-Customization_images/Label-Customization_img2.png)

### Visibility of label bar 
 
SfDateTimeRangeNavigator provides support to customize the visibility of lower bar and upper bar using the `LowerLabelBarVisibility` and `UpperLabelBarVisibility` types.