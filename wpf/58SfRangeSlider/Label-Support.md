---
layout: post
title: Label-Support
description: label support
platform: wpf
control: SfRangeSlider 
documentation: ug
---

# Label Support

This feature allows you to display labels for custom values given in the CustomLabels collection when the ShowCustomLabels property is set to true. It also displays labels for all of the tick values when ShowValueLabels is set to true.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
CustomLabels</td><td>
It describes an observable collection of items that contains the custom labels and the values for that the labels should be displayed.</td></tr>
<tr>
<td>
ShowCustomLabels</td><td>
This property allows you to display custom labels for particular values based on CustomLabels collection.</td></tr>
<tr>
<td>
ShowValueLabels</td><td>
This property allows you to display labels for the ticks.</td></tr>
<tr>
<td>
LabelPlacement</td><td>
This property specifies the position of the custom label placement.</td></tr>
<tr>
<td>
ValuePlacement</td><td>
This property specifies the position of the label for all of the ticks.</td></tr>
<tr>
<td>
LabelOrientation</td><td>
LabelOrientation specifies the orientation of the labels as either horizontal or vertical.</td></tr>
</table>
## CustomLabels

CustomLabels is an observable collection of items that contains the Label and Value properties. Create an observable collection of items by specifying the custom labels for corresponding values as illustrated in the following code example.



[C#]



this.customCollection.Add(new Items(){label = "Min", value= 100});

this.customCollection.Add(new Items() { label = "Max", value = 200 });

private ObservableCollection<Items> customCollection = new ObservableCollection<Items>();



public ObservableCollection<Items> CustomCollection

{

get { return customCollection; }

set { customCollection = value; }

}



In the following code example, the CustomCollection property is bound to CustomLabels property in the SfRangeSlider control that populates the custom labels collection.

[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" /&gt;



{ ![](Label-Support_images/Label-Support_img1.png) | markdownify }
{:.image }


_RangeSlider with CustomLabels_

## ShowCustomLabels

The default value of ShowCustomLabels is false. When set to true, it displays the custom labels for particular values based on the CustomLabels collection.

[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" /&gt;





{ ![](Label-Support_images/Label-Support_img2.png) | markdownify }
{:.image }


_RangeSlider with ShowCustomLabels_

## LabelPlacement

LabelPlacement property describes the position of the custom labels for particular values mentioned in the CustomLabels collection. Available options for this property are:

1. BottomRight
2. TopLeft



The following code example illustrates the usage of the LabelPlacement property. The output is displayed in the corresponding images.



[XAML]

&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" CustomLabels="{Binding CustomCollection}" LabelPlacement="BottomRight"/&gt;



{ ![](Label-Support_images/Label-Support_img3.png) | markdownify }
{:.image }


_LabelPlacement in BottomRight_



[XAML]



<editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowCustomLabels="True" 

CustomLabels="{Binding CustomCollection}" LabelPlacement="TopLeft"/>



{ ![](Label-Support_images/Label-Support_img4.png) | markdownify }
{:.image }


_LabelPlacement in TopLeft_

## ShowValueLabels

The default value of the ShowValueLabels property is false. When set to true, it displays the label for all the ticks based on the ValuePlacement property.



[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100"   Maximum="200" TickFrequency="20" TickPlacement="BottomRight" ShowValueLabels="True"/&gt;



{ ![](Label-Support_images/Label-Support_img5.png) | markdownify }
{:.image }


_ShowValueLabels property_

## ValuePlacement

The ValuePlacement property describes the position of the labels for all the ticks. Available options for this property are:

1. BottomRight
2. TopLeft



The following code example illustrates the usage of ValuePlacement property. The output is displayed in the corresponding images.



[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" ValuePlacement="TopLeft"/&gt;



{ ![](Label-Support_images/Label-Support_img6.png) | markdownify }
{:.image }


_ValuePlacement in Bottom Right_



[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" ValuePlacement="BottomRight"/&gt;



{ ![](Label-Support_images/Label-Support_img7.png) | markdownify }
{:.image }


_ValuePlacement in TopLeft_

## LabelOrientation

The LabelOrientation property describes the orientation of the labels for both ticks and custom labels. Available options for this property are:

1. Horizontal
2. Vertical



The following code example illustrates the usage of LabelOrientation property. The output is displayed in the corresponding images.



[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Horizontal"/&gt;



{ ![](Label-Support_images/Label-Support_img8.png) | markdownify }
{:.image }


_LabelOrientation as Horizontal_



[XAML]



&lt;editors:SfRangeSlider Width="200" Minimum="100" Maximum="200" TickFrequency="20" TickPlacement="Outside" ShowValueLabels="True" LabelOrientation="Vertical"/&gt;



{ ![](Label-Support_images/Label-Support_img9.png) | markdownify }
{:.image }


_LabelOrientation as Vertical_

