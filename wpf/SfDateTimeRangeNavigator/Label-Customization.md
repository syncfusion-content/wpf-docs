---
layout: post
title: Label-Customization
description: label customization
platform: wpf
control: DateTime Range Navigator
documentation: ug
---

# Label Customization

The SfDateTimeRangeNavigator helps the user to visualize large data in a simplified manner. The timespan of the data is represented in the Higher Level Bar and Lower Level Bar. The timespan in default calculated smartly and provide the suitable DateTime format and Interval for the given data.

User can also set the Interval which they think suitable for their data, this can be done by using Interval Property as in below code snippet. 

_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
Intervals</td><td>
Used to set the Interval type which need to be displayed in the Navigator</td></tr>
</table>


&lt;syncfusion:SfDateTimeRangeNavigator x:Name="rangepicker" ItemsSource="{Binding power}"  XBindingPath="Date" &gt;



            &lt;syncfusion:SfDateTimeRangeNavigator.Intervals&gt; 

                &lt;syncfusion:Interval IntervalType="Quarter"/&gt;

                &lt;syncfusion:Interval IntervalType="Month"/&gt;

            &lt;/syncfusion:SfDateTimeRangeNavigator.Intervals&gt;



            &lt;syncfusion:SfDateTimeRangeNavigator.Content&gt;

                &lt;syncfusion:SfChart   &gt;

                    &lt;syncfusion:SfChart.PrimaryAxis&gt;

                        &lt;syncfusion:CategoryAxis Visibility="Collapsed" /&gt;

                    &lt;/syncfusion:SfChart.PrimaryAxis&gt;

                    &lt;syncfusion:SfChart.SecondaryAxis&gt;

                        &lt;syncfusion:NumericalAxis Visibility="Collapsed" /&gt;

                    &lt;/syncfusion:SfChart.SecondaryAxis&gt;

                    &lt;syncfusion:FastLineBitmapSeries XBindingPath="Date" ItemsSource="{Binding power}" YBindingPath="Value"&gt;

                        &lt;/syncfusion:FastLineBitmapSeries&gt;

                &lt;/syncfusion:SfChart&gt;

                &lt;/syncfusion:SfDateTimeRangeNavigator.Content&gt;

        &lt;/syncfusion:SfDateTimeRangeNavigator&gt;



Following is the screenshot of showing only Quarter and Month intervals in the Navigator



{ ![C:/Users/ApoorvahR/Desktop/5.png](Label-Customization_images/Label-Customization_img1.png) | markdownify }
{:.image }


_Quarter and Month intervals in the Navigator_



The Interval has the following types 

* Year
* Quarter
* Month
* Week
* Day
* Hour



The auto timespan format simplifies the visual representation of data while zooming in with the below formats.

_List of Intervals_

<table>
<tr>
<td>
Intervals</td><td>
Examples</td></tr>
<tr>
<td>
HourInterval</td><td>
7/21/2011 12:00:00 AM -> 12 AM7/21/2011 12:00:00 AM -> 12A</td></tr>
<tr>
<td>
DayInterval</td><td>
7/21/2011 12:00:00 AM -> Thursday, July 21, 20117/21/2011 12:00:00 AM -> Thu, Jul 21, 20117/21/2011 12:00:00 AM -> Thursday, 217/21/2011 12:00:00 AM -> Thu, 21</td></tr>
<tr>
<td>
WeekInterval</td><td>
7/21/2011 12:00:00 AM -> Week 29, July, 20117/21/2011 12:00:00 AM -> Week 29, Jul, 20117/21/2011 12:00:00 AM -> Week 297/21/2011 12:00:00 AM -> W29</td></tr>
<tr>
<td>
MonthInterval</td><td>
7/21/2011 12:00:00 AM -> July, 20117/21/2011 12:00:00 AM -> July7/21/2011 12:00:00 AM -> Jul7/21/2011 12:00:00 AM -> J</td></tr>
<tr>
<td>
QuarterInterval</td><td>
7/21/2011 12:00:00 AM -> Quarter 3, 20117/21/2011 12:00:00 AM -> Quarter 37/21/2011 12:00:00 AM -> Q3, 20117/21/2011 12:00:00 AM -> Q3</td></tr>
<tr>
<td>
YearInterval</td><td>
7/21/2011 12:00:00 AM -> 2011</td></tr>
</table>


Label Style Customization

Label Style can be customized using the LabelBarStyle property and this can be applied to the HigherLevelBarStyle or LowerLevelBarStyle.



&lt;chart:SfDateTimeRangeNavigator.HigherLevelBarStyle&gt;

                    &lt;chart:LabelBarStyle Background="Red" LabelHorizontalAlignment="Left"&gt;

                        &lt;chart:LabelBarStyle.LabelStyle&gt;

                            &lt;Style TargetType="TextBlock"&gt;

                                &lt;Setter Property="FontSize" Value="10"/&gt;

                            &lt;/Style&gt;

                        &lt;/chart:LabelBarStyle.LabelStyle&gt;

                    &lt;/chart:LabelBarStyle&gt;

  &lt;/chart:SfDateTimeRangeNavigator.HigherLevelBarStyle&gt;



Following is the screenshot of Label HorizontalAlignment set to left.



{ ![C:/Users/ApoorvahR/Desktop/6.png](Label-Customization_images/Label-Customization_img2.png) | markdownify }
{:.image }


_Label HorizontalAlignment set to left_

