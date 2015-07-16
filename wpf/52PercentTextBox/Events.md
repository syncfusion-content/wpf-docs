---
layout: post
title: Events
description: events
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Events

The PercentTextBox exposes the following events:

## PercentValueChanged

PercentValueChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox ValueChanged="PercentTextBox_PercentValueChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.PercentValueChanged+=new PropertyChangedCallback(PercentTextBox_PercentValueChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



void PercentTextBox_PercentValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when value of PercentTextBox PercentValue change.

        }

## TextChanged

TextChanged – The event occurs when the PercentValue property of the PercentTextBox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox TextChanged="PercentTextBox_TextChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.TextChanged += new TextChangedEventHandler(PercentTextBox_TextChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



        void PercentTextBox_TextChanged(object sender, TextChangedEventArgs e)

        {

            //Insert code to do some operations when Text of PercentTextBox change.

        }

## CultureChanged

CultureChanged – The event occurs when the Culture property of the PercentTextBox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox CultureChanged="PercentTextBox_CultureChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.CultureChanged+=new                            PropertyChangedCallback(PercentTextBox_CultureChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



void PercentTextBox_CultureChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the Culture property changes.

        }

## MaxValueChanged

MaxValueChanged – The event occurs when the MaxValue property of the PercentTextBox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox MaxValueChanged="PercentTextBox_MaxValueChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.MaxValueChanged+=new                     PropertyChangedCallback(PercentTextBox_MaxValueChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



void PercentTextBox_MaxValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MaxValue changed

        }

## MinValueChanged

MinValueChanged – The event occurs when the MinValue property of the PercentTextBox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox MinValueChanged="PercentTextBox_MinValueChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.MinValueChanged+=new                      PropertyChangedCallback(PercentTextBox_MinValueChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



void PercentTextBox_MinValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)

        {

            //Insert code to do some operations when the MinValue changed

        }

## SelectionChanged

SelectionChanged – The event occurs when the selection in the textbox is changed.

<table>
<tr>
<td>
XAML&lt;syncfusion:PercentTextBox SelectionChanged="PercentTextBox_SelectionChanged"/&gt;</td></tr>
<tr>
<td>
C# PercentTextBox percentTextBox = new PercentTextBox();percentTextBox.SelectionChanged+=new                         RoutedEventHandler(PercentTextBox_SelectionChanged);</td></tr>
</table>


You can handle the event as follows:

C# 



void PercentTextBox_SelectionChanged(object sender, RoutedEventArgs e)

        {

            //Insert code to do some operations when the Selected Text changed.

        }



