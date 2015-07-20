---
layout: post
title: Events
description: events
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Events

The CurrencyTextBox exposes the following events:

## ValueChanged

ValueChanged – The event occurs when the Value property of the CurrencyTextBox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox ValueChanged="CurrencyTextBox_ValueChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.ValueChanged+=new PropertyChangedCallback(CurrencyTextBox_ValueChanged);</td></tr>
</table>


You can handle the event as follows:



C#

private void CurrencyTextBox_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of CurrencyTextBox changes.

        }

## TextChanged

TextChanged – The event occurs when the Value property of the CurrencyTextBox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox TextChanged="CurrencyTextBox_TextChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.TextChanged += new TextChangedEventHandler(CurrencyTextBox_TextChanged);</td></tr>
</table>


You can handle the event as follows:



C#



private void CurrencyTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of CurrencyTextBox changes.

        }

## CultureChanged

CultureChanged – The event occurs when the Culture property of the CurrencyTextBox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox CultureChanged="CurrencyTextBox_CultureChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.CultureChanged+=new                            PropertyChangedCallback(CurrencyTextBox_CultureChanged);</td></tr>
</table>


You can handle the event as follows:



C#



private void CurrencyTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }

## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the CurrencyTextBox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox MaxValueChanged="CurrencyTextBox_MaxValueChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.MaxValueChanged+=new                     PropertyChangedCallback(CurrencyTextBox_MaxValueChanged);</td></tr>
</table>


You can handle the event as follows:



C#



private void CurrencyTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the CurrencyTextBox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox MinValueChanged="CurrencyTextBox_MinValueChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.MinValueChanged+=new                      PropertyChangedCallback(CurrencyTextBox_MinValueChanged);</td></tr>
</table>


You can handle the event as follows:



C#



private void CurrencyTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }

## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox SelectionChanged="CurrencyTextBox_SelectionChanged"/></td></tr>
<tr>
<td>
C#CurrencyTextBox currencyTextBox = new CurrencyTextBox();currencyTextBox.SelectionChanged+=new                         RoutedEventHandler(CurrencyTextBox_SelectionChanged);</td></tr>
</table>


You can handle the event as follows:



C#



private void CurrencyTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }



