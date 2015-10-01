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

  
<syncfusion:ColorPickerPalette  x:Name="ColorPickerPalette1" MouseOverBackground="Green">       
</syncfusion:ColorPickerPalette>
{% endhighlight %}

{% highlight C#%}


ColorPickerPalette ColorPickerPalette1 = new ColorPickerPalette();
ColorPickerPalette1.MouseOverBackground = Brushes.Green;
{% endhighlight %}


### Properties

  

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
MouseOverBackgroundBrush </td><td>
Gets or sets the MouseOver BackgroundBrush value of the ColorPickerPalette.</td><td>
Brush </td><td>
N/A </td></tr>
</table>


