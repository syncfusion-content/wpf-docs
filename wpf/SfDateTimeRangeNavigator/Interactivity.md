---
layout: post
title: Interactivity | SfDateTimeRangeNavigator | wpf | Syncfusion
description: interactivity
platform: wpf
control: SfDateTimeRangeNavigator
documentation: ug
---

# Interactivity

SfDateTimeRangeNavigator provides interactive features such as zooming, panning. The navigator has a resizable scrollbar which is used to zoom in large amount of data and also helps to navigate to particular timespan by moving the scrollbar. 

The ZoomPosition and ZoomFactor of the chart axis can be bind with the SfDateTimeRangeNavigator.

## Property

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
ZoomPosition</td><td>
Represents the ZoomPosition of the Selected Range in the Navigator</td></tr>
<tr>
<td>
ZoomFactor</td><td>
Represent the ZoomFactor of the Selected Range in the Navigator</td></tr>
<tr>
<td>
SelectedData</td><td>
Used to get the selected data between a selected range in the Navigator</td></tr>
<tr>
<td>
ShowGridLines</td><td>
Used to show the gridlines inside the content of a Navigator</td></tr>
<tr>
<td>
Minimum</td><td>
Used to set the minimum or starting range of the Navigator</td></tr>
<tr>
<td>
Maximum</td><td>
Used to set the maximum or ending range of the Navigator</td></tr>
<tr>
<td>
ViewRangeStart</td><td>
Used to get the Start value of the Selected range of the Navigator</td></tr>
<tr>
<td>
ViewRangeEnd</td><td>
Used to get the End value of the Selected range of the Navigator</td></tr>
<tr>
<td>
EnableDeferredUpdate</td><td>
Used to enable deferred scrolling and panning.</td></tr>
</table>


## Event

<table>
<tr>
<th>
Event</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
ValueChanged</td><td>
ValueChanged(Object sender, EventArgs e)</td><td>
This event is triggered when the position of the scrollbar changed</td></tr>
</table>

{% highlight xaml %}

<chart:SfChart x:Name="financialChart">            

  <chart:SfChart.PrimaryAxis>

         <chart:CategoryAxis Name="axis1" ZoomPosition="{Binding ElementName=RangeNavigator, Path=ZoomPosition, Mode=TwoWay}" ZoomFactor="{Binding ElementName=RangeNavigator, Path=ZoomFactor, Mode=TwoWay}" Header="Date" LabelFormat="MMM/dd"  LabelTemplate="{StaticResource labelTemplate}" />                

  </chart:SfChart.PrimaryAxis>            

  <chart:SfChart.SecondaryAxis>                

                  <chart:NumericalAxis  />  

</chart:SfChart.SecondaryAxis>            

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" XBindingPath="_Date"  High="High" Open="Open" Close="Close" Low="Low"  Label="Candleseries">            

</chart:CandleSeries>        

</chart:SfChart>        

<chart:SfDateTimeRangeNavigator x:Name="RangeNavigator" ItemsSource="{Binding StockPriceDetails}" XBindingPath="_Date" >                

	<chart:SfDateTimeRangeNavigator.Content>                   

		<chart:SfLineSparkline ItemsSource="{Binding StockPriceDetails}"   YBindingPath="High" >                    </chart:SfLineSparkline>                

	</chart:SfDateTimeRangeNavigator.Content>            

</chart:SfDateTimeRangeNavigator>


{% endhighlight  %}
The following is the screenshot of SfDateTimeRangeNavigator selecting one Quarter of data.

![](Interactivity_images/Interactivity_img1.png)

SfDateTimeRangeNavigator selecting  one Quarter of data
{:.caption}

The following is the screenshot of SfDateTimeRangeNavigator after zooming into weeks of data from 6 months of data.

![](Interactivity_images/Interactivity_img2.png)

SfDateTimeRangeNavigator after zooming into weeks of data from 6 months of data
{:.caption}

## ThumbStyle Customization

SfDateTimeRangeNavigator provides many properties to customize the elements such as Upper, Lower bar and Left, Right thumb, etc.,

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
LeftThumbStyle</td><td>
Used to define the style for left thumb of the Navigator</td></tr>
<tr>
<td>
RightThumbStyle</td><td>
Used to define the style for right thumb of the Navigator</td></tr>
<tr>
<td>
LineStyle</td><td>
Used to define the style for line in the left or right thumb</td></tr>
<tr>
<td>
SymbolTemplate</td><td>
Used to define the style for symbol placed in the left or right thumb</td></tr>
</table>

{% highlight xaml %}

<chart:SfDateTimeRangeNavigator.RightThumbStyle>

    <chart:ThumbStyle>
    
        <chart:ThumbStyle.SymbolTemplate>
        
            <DataTemplate>
            
                <Grid>
                
                    <Ellipse Height="40" Width="40"  Fill="Green" Stroke="Black"
                         VerticalAlignment="Center" StrokeThickness="2">
                    </Ellipse>
                    
                    <Ellipse Height="7" Width="7" Fill="White" VerticalAlignment="Center"/>
                </Grid>
                
            </DataTemplate>
            
        </chart:ThumbStyle.SymbolTemplate>
        
    </chart:ThumbStyle>
    
</chart:SfDateTimeRangeNavigator.RightThumbStyle>

{% endhighlight  %}

The following is the screenshot of SfDateTimeRangeNavigator with customized Right thumb.

![](Interactivity_images/Interactivity_img3.png)

## Higher and Lower bar customization

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
HigherBarGridLineStyle</td><td>
Used to define the style for upper labels bar gridlines.</td></tr>
<tr>
<td>
LowerBarGridLineStyle</td><td>
Used to define the style for lower labels bar gridlines.</td></tr>
<tr>
<td>
HigherBarTickLineStyle</td><td>
Used to define the style for upper labels bar ticklines.</td></tr>
<tr>
<td>
LowerBarTickLineStyle</td><td>
Used to define the style for lower labels bar ticklines.</td></tr>
</table>