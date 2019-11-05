---
layout: post
title: Expanded Mode| ColorPickerPalette | Wpf | Syncfusion
description: expanded mode
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# Expanded Mode

Expanded Mode allows you to pick colors from the ColorPickerPalette. By setting IsExpanded Property to True, the ColorPickerPalette control can be hosted in Expanded Mode. By default, this mode is set to False.

### Use Case Scenarios

Expanded Mode can be used when you want to have the ColorPickerPalette without drop down.

## Adding Expanded Mode to an Application 

Expanded Mode can be added to an application by using XAML or C# code.

The following code example illustrates how to add the Expanded Mode to an application.


{% tabs %}

{% highlight xaml %}

<sync:ColorPickerPalette IsExpanded="True"/>

{% endhighlight %}

{% highlight C# %}

    
 ColorPickerPalette colorpicker = new ColorPickerPalette();
      
 colorpicker.IsExpanded = true;
 
{% endhighlight %}


{% highlight VB %}

    
 ColorPickerPalette colorpicker = new ColorPickerPalette()
      
 colorpicker.IsExpanded = true
 
{% endhighlight %}

{% endtabs %}

![](Expanded-Mode_images/Expanded-Mode_img1.png)





### Properties


<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th>
</tr>
<tr>
<td>
IsExpanded</td><td>
Enables or disables the Expanded Mode property of ColorPickerPalette</td><td>
DependencyProperty</td><td>
False</td><td>
</td></tr>
</table>


### Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now Search ColorPickerPalette sample and launch it.



