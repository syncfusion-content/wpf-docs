---
layout: post
title: Events
description: events
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Events

The DoubleTextBox exposes the following events:

## ValueChanged

ValueChanged – The event occurs when the Value property of the DoubleTextBox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox ValueChanged="DoubleTextBox_ValueChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.ValueChanged += new PropertyChangedCallback(DoubleTextBox_ValueChanged);</td></tr>
</table>


You can handle the ValueChanged event as follows:



C#



private void DoubleTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of DoubleTextBox changes.

        }



## TextChanged

TextChanged – The event occurs when the Value property of the DoubleTextBox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox TextChanged="DoubleTextBox_TextChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.TextChanged+=new TextChangedEventHandler(DoubleTextBox_TextChanged);</td></tr>
</table>


You can handle the TextChanged event as follows:



C#



private void DoubleTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of DoubleTextBox changes.

        }

## CultureChanged

CultureChanged – The event occurs when the Culture property of the DoubleTextBox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox CultureChanged="DoubleTextBox_CultureChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.CultureChanged+=new PropertyChangedCallback(DoubleTextBox_CultureChanged);</td></tr>
</table>


You can handle the CultureChanged event as follows:



C#



private void DoubleTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }



## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the DoubleTextBox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox MaxValueChanged="DoubleTextBox_MaxValueChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.MaxValueChanged+=new               PropertyChangedCallback(DoubleTextBox_MaxValueChanged);</td></tr>
</table>


You can handle the MaxValueChanged event as follows:



C#



private void DoubleTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the DoubleTextBox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox MinValueChanged="DoubleTextBox_MinValueChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.MinValueChanged+=new              PropertyChangedCallback(DoubleTextBox_MinValueChanged);</td></tr>
</table>


You can handle the MinValueChanged event as follows:



C#



private void DoubleTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }

## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.



<table>
<tr>
<td>
XAML&lt;syncfusion:DoubleTextBox SelectionChanged="DoubleTextBox_SelectionChanged"/&gt;</td></tr>
<tr>
<td>
C#DoubleTextBox doubleTextBox = new DoubleTextBox();doubleTextBox.SelectionChanged+=new RoutedEventHandler(DoubleTextBox_SelectionChanged);</td></tr>
</table>


You can handle the SelectionChanged event as follows:



C#



private void DoubleTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }



