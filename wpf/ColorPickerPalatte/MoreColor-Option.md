---
layout: post
title: MoreColor Option| ColorPickerPalette | Wpf | Syncfusion
description: morecolor option
platform: wpf
control: ColorPickerPalette
documentation: ug
---

# MoreColor Option

In addition to colors in Theme colors and Standard colors, MoreColor feature allows you to select wide range of color options. MoreColor feature includes two categories namely Standard Colors and Custom Colors. The Standard Colors includes 140 colors clustered in the shape of a Hexagon. The color chosen from this cluster will also be added in the RecentlyUsedPanel. You can also set the visibility of the MoreColor Option by using the MoreColorOptionVisibility property.

## Use Case Scenarios

MoreColor Option can be used when you want to select colors using standard and custom colors.

## Adding MoreColor Option to an Application 

MoreColor Option can be added to an application by using XAML or C# code.

The following code example illustrates how to add the MoreColor Option to an Application through XAML.

{% tabs %}

{% highlight xaml %}

<sync:ColorPickerPalette x:Name="ColorPicker" 

MoreColorOptionVisibility="Visible" />

{% endhighlight %}
{% endtabs %}

The following code example illustrates how to add the MoreColor Option to an Application through C#.

{% tabs %}
{% highlight C# %}


ColorPickerPalette colorpicker = new ColorPickerPalette();

colorpicker.MoreColorOptionVisibility = System.Visibility.Visible;

{% endhighlight %}

{% endtabs %}

![](MoreColor-Option_images/MoreColor-Option_img1.png)





![](MoreColor-Option_images/MoreColor-Option_img2.png)



## MoreColorIcon

The MoreColorIcon property used to set the Icon left to the More Color option . 

{% tabs %}

{% highlight XAML %}

<syncfusion:ColorPickerPalette x:Name="ColorPicker" MoreColorsIcon="More color.png"  MoreColorOptionVisibility="Visible"  Width="100" Height="23" />

{% endhighlight %}

{% highlight C# %}

ColorPicker.Icon = new BitmapImage(new Uri(@"color.png", UriKind.RelativeOrAbsolute));

{% endhighlight %}

{% highlight VB %}


ColorPicker.Icon = New BitmapImage(New Uri("color.png", UriKind.RelativeOrAbsolute))

{% endhighlight %}

{% endtabs %}

![](MoreColor-Option_images/MoreColor-Option_img3.png)

## MoreColorsIconSize

The MoreColorsIconSize property used to set the Size for the icon to be used for the MoreColorsIcon.  Please find the code for the same:

{% tabs %}

{% highlight C# %}

ColorPicker.MoreColorsIconSize = new Size(100,100);

{% endhighlight %}

{% highlight VB %}

ColorPicker.MoreColorsIconSize = new Size(100,100)

{% endhighlight %}

{% endtabs %}



## Properties

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
MoreColorOptionVisibility</td><td>
Enables or disables the visibility of the MoreColor Window.</td><td>
Dependency Property</td><td>
Visibility.Visible</td><td>
N/A </td>
</tr>
</table>


### Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now Search ColorPickerPalette sample and launch it. 



