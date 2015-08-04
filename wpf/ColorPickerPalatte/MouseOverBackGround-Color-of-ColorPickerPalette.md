---
layout: post
title: MouseOverBackGround-Color-of-ColorPickerPalette
description: mouseoverbackground color of colorpickerpalette
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# MouseOverBackGround Color of ColorPickerPalette

You can change the background color of the ColorPickerPalette at mouse over, based on the brush color set in the MouseOverBackground property.



{% highlight xml %}

[XAML]   
<syncfusion:ColorPickerPalette  x:Name="ColorPickerPalette1" MouseOverBackground="Green">       
</syncfusion:ColorPickerPalette>
{% endhighlight %}

{% highlight C#%}

[C#]
ColorPickerPalette ColorPickerPalette1 = new ColorPickerPalette();
ColorPickerPalette1.MouseOverBackground = Brushes.Green;
{% endhighlight %}


## Properties

  _Property Table_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
MouseOverBackgroundBrush </td><td>
Gets or sets the MouseOver BackgroundBrush value of the ColorPickerPalette.</td><td>
Brush </td><td>
N/A </td></tr>
</table>


