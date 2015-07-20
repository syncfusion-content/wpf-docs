---
layout: post
title: Events
description: events
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Events

The IntegerTextBox exposes the following events:

## ValueChanged

ValueChanged – The event occurs when the Value property of the IntegerTextBox is changed.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox ValueChanged="IntegerTextBox_ValueChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.ValueChanged+=new PropertyChangedCallback(IntegerTextBox_ValueChanged);</td></tr>
</table>


You can handle the event as follows:

C#



private void IntegerTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of IntegerTextBox changes.

        }

## TextChanged

TextChanged – The event occurs when the Value property of the IntegerTextBox is changed.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox  TextChanged="integerTextBox_TextChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.TextChanged+=new TextChangedEventHandler(IntegerTextBox_TextChanged);</td></tr>
</table>


You can handle the TextChanged event as follows:

C#



private void IntegerTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of IntegerTextBox changes.

        }

## CultureChanged

CultureChanged – The event occurs when the Culture property of the IntegerTextBox is changed. When the Culture property is changed the value is formatted based on the new Culture.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox  CultureChanged="IntegerTextBox_CultureChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.CultureChanged+=new                                                PropertyChangedCallback(IntegerTextBox_CultureChanged);</td></tr>
</table>


You can handle the CultureChanged event as follows:

C#



private void IntegerTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }

## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the IntegerTextBox is changed. When the MaxValue is changed the Value and the MinValue properties are formatted.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox  MaxValueChanged="IntegerTextBox_MaxValueChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MaxValueChanged+=new                           PropertyChangedCallback(IntegerTextBox_MaxValueChanged);</td></tr>
</table>


You can handle the MaxValueChanged event as follows:

C#



private void IntegerTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the IntegerTextBox is changed. When the MinValue is changed the Value and the MaxValue properties are formatted.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox  MinValueChanged="IntegerTextBox_MinValueChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.MinValueChanged+=new                            PropertyChangedCallback(IntegerTextBox_MinValueChanged);</td></tr>
</table>


You can handle the MinValueChanged event as follows:

C#



private void IntegerTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }



## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox  SelectionChanged="IntegerTextBox_SelectionChanged"/></td></tr>
<tr>
<td>
C#IntegerTextBox integerTextBox = new IntegerTextBox();integerTextBox.SelectionChanged+=new RoutedEventHandler(IntegerTextBox_SelectionChanged);</td></tr>
</table>


You can handle the SelectionChanged event as follows:

C#



private void IntegerTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }



