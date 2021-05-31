---
layout: post
title: Text of Syncfusion SfImageEditor WPF.
description: This section explains how the image can be annotated by adding the required text on it and also it can be customized.
platform: wpf
control: SfImageEditor
 documentation: ug
---

# Text in SfImageEditor

You can annotate an image by adding the desired text to it. This can be done in the following two ways:

1. Adding text using built-in toolbar
2. Adding text programmatically

## Toolbar

To add text, click the Text icon (T) in the toolbar. Now, the text will be added at the center of the image along with the selection handle, which helps in resizing. By default, the added text will be in pan mode, so you can position the text anywhere by dragging it. By clicking the text, it will change into typing mode, and you can edit the text directly. Click outside to exit from typing mode.

## Customization

The following properties of the added text can be customized:

* Font family
* Font size
* Font color
* Alignment (center, left, and right)
* Text effects (bold, italic, and underline)

Upon selecting the Text icon in the toolbar, a sub toolbar will be generated below the main toolbar for providing the text customizing options. 

>N Text needs to be selected to apply the customization from the sub toolbar.

### Font family

Font family icon lists out the predefined system font families. You can select the required font family.

### Font size

You can select the size from the listed-out font sizes.

### Font color

Color picker will be opened by clicking this icon. You can pick the required color from it.

### Text effects

You can make the text bold, italic, or underline by clicking the corresponding icons in the toolbar. By default, no effects will be applied.

### Alignment

Text can be aligned to the left, center, or right by clicking the corresponding icon. By default, text will be aligned at the left.


## Adding text programmatically

You can add text to an image using the AddText method programmatically. This method requires the following parameters:

* Text – Specifies the content you need to add on the image.
* TextSettings - Customizes the text.

{% tabs %} 

{% highlight C# %} 

editor.AddText("Hello", new TextSettings());

{% endhighlight %}

{% endtabs %} 

## Text settings

Using the following properties in TextSettings, text can be customized.

* [`FontFamily`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_FontFamily) - Changes the font family of the text.
* [`FontSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_FontSize) - Changes the font size of the text.
* [`Color`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_Color) - Modifies the font color of the text.
* [`TextAlignment`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_TextAlignment) - Text alignment such as left, top, and center can be applied.
* [`TextEffects`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_TextEffects) - Text effects such as bold, italic, and underline can be applied.
* [`Opacity`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_Opacity) - Modifies the opacity of the text.
* [`Angle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_Angle) - Rotates the text to the specified angle.
* [`Bounds`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ImageEditor.TextSettings.html#Syncfusion_UI_Xaml_ImageEditor_TextSettings_Bounds) - Rect used to position the text. 

>N Values of bounds will be in percentage. For example (25, 25, 25, 25) will take the position of 25 percent from the left and top.

{% tabs %} 

{% highlight C# %} 

            TextSettings textSettings = new TextSettings();
            textSettings.FontFamily = new FontFamily("Century Schoolbook");
            textSettings.FontSize = 30;
            textSettings.Color = new SolidColorBrush(Colors.Red);
            textSettings.TextEffects = TextEffects.Bold | TextEffects.Italic;
            textSettings.Bounds = new Rect(50, 10, 50, 15);
            editor.AddText("Good morning", textSettings);

            textSettings = new TextSettings();
            textSettings.FontFamily = new FontFamily("Bell MT");
            textSettings.FontSize = 22;
            textSettings.Color = new SolidColorBrush(Colors.DarkGreen);
            textSettings.TextEffects =  TextEffects.Italic;
            textSettings.Bounds = new Rect(50, 23, 30, 15);
            textSettings.TextAlignment = TextAlignment.Center;
            editor.AddText("The happiness of your \nlife depend upon the \nquality of your thoughts.", textSettings);


{% endhighlight %}

{% endtabs %} 

![Text](Images/Text.jpg)   

## See also

[How to load the image annotated with shapes and text on the image editor](https://www.syncfusion.com/kb/11215/how-to-load-the-image-annotated-with-shapes-and-text-on-the-image-editor)

