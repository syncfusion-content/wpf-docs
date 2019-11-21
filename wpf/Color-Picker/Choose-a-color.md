---
layout: post
title: Choose a color | ColorPicker | wpf | Syncfusion
description: This section explains basic color editing options, such as different color modes, eye dropper support, and tooltip support.
platform: wpf
control: ColorPicker
documentation: ug
---

## Selection Mode

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) and [ColorEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit.html) controls can be displayed in two different modes. They are HSV and RGB modes. The [VisualizationStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~VisualizationStyle.html) property is used to switch between these modes.


## RGB

To set the [ColorSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.ColorSelectionMode.html) as "RGB" for ColorEdit control, use the below code.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorEdit  Margin="20" VisualizationStyle="RGB" Name="colorEdit"/>

{% endhighlight %}

{% highlight C# %}

ColorEdit colorEdit = new ColorEdit();

colorEdit.VisualizationStyle = ColorSelectionMode.RGB; 

this.Content = colorEdit;

{% endhighlight %}
{% endtabs %}

![ColorEdit with RGB selection mode](Selection-Mode_images/ColorEdit_RGB_ColorSelectionMode.png)



To set the [ColorSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.ColorSelectionMode.html) as "RGB" for ColorPicker control, use the below code.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker  Margin="20" VisualizationStyle="RGB" Name="colorpicker"/>

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();

colorPicker.VisualizationStyle = ColorSelectionMode.RGB;

this.Content = colorPicker;

{% endhighlight %}
{% endtabs %}

![ColorPicker with RGB selection mode](Selection-Mode_images/ColorPicker_RGB_ColorSelection_Mode.png)

## HSV

To set the [ColorSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.ColorSelectionMode.html) as "HSV" for ColorEdit control, use the below code.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorEdit  Margin="20" VisualizationStyle="HSV" Name="colorEdit"/><

{% endhighlight %}

{% highlight C# %}

ColorEdit colorEdit = new ColorEdit();

VisualizationStyle = ColorSelectionMode.HSV;    

//Adding control to the window
this.Content = colorEdit;

{% endhighlight %}
{% endtabs %}

![ColorEdit with HSV selection mode](Selection-Mode_images/ColorEdit_HSV_ColorSelection_Mode.png)

To set the [ColorSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.ColorSelectionMode.html) as "HSV" for ColorPicker control, use the below code.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker  Margin="20" VisualizationStyle="HSV" Name="colorpicker"/><

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();

colorPicker.VisualizationStyle = ColorSelectionMode.HSV;    

this.Content = colorPicker;

{% endhighlight %}
{% endtabs %}

![ColorPicker with HSV selection mode](Selection-Mode_images/ColorPicker_HSV_ColorSelectionMode.png)


## Eye Dropper

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) consist of `eye-dropper` which can be dragged across the anywhere on the screen,picks the color it is currently hovering above, along with the associated hexadecimal (HEX) color value.

![ColorPicker with Eye-Dropper](Selection-Mode_images/ColorPicker_Eyedropper.gif)

## Get color name from color property

[ColorPicker](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker.html) come along with method which returns the nearest names of color property, this can be obtained by [SuchColor](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorEdit~SuchColor.html) method.

{% tabs %}
{% highlight C# %}

  private void ColorPicker_SelectedBrushChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
        {
            ColorPicker colorPicker = d as ColorPicker;
            textBlock.Text = Syncfusion.Windows.Shared.ColorEdit.SuchColor(colorPicker.Color)[0];
        }

{% endhighlight %}
{% endtabs %}

## Tooltip

ColorPicker support to show selected color via Tooltip while hovering through the color palette, this can be enabled using [EnableToolTip](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.ColorPicker~EnableToolTip.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:ColorPicker  Width="300" EnableToolTip="True"  Name="colorpicker"/>

{% endhighlight %}

{% highlight C# %}

ColorPicker colorPicker = new ColorPicker();

colorPicker.EnableToolTip = true;

this.Content = colorPicker;

{% endhighlight %}
{% endtabs %}

![ColorPicker with TooTip support](Selection-Mode_images/ColorPicker_Tooltip.png)