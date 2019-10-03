---
layout: post
title: Text of Syncfusion SfImageEditor WPF.
description: Annotating image using text.
platform: wpf
control: SfImageEditor
documentation: ug
---

# Text

You can annotate the image by adding the desired text on it. This can be done in the following two ways.

1.	Using in-built toolbar
2.	Programmatically using code.


## Toolbar

To add text, click on the Text icon (T) in the toolbar. Now the text will be added at the center of the image along with the selection handle which helps in resizing. By default, added text will be in pan mode hence you can position the text anywhere by clicking and dragging on the it. By clicking again on the text, it will change into typing mode and you can edit the text directly. Click outside to exit from typing mode.

## Customization

The following properties of the added text can be customized.

* Font family
* Font size
* Font color
* Alignment (Center, Left, Right)
* Text Effects (Bold, Italic, Underline)

Upon selecting the Text icon in the toolbar, a sub toolbar will be generated below the main toolbar for providing the text customizing options. 

>N Text needs to be selected to apply the customization from the sub toolbar.

### Font family

Font family icon list out the predefined system font families. You can select the required font family from that.

### Font size

You can select the size from the listed-out font sizes.

### Font color

Color picker will be opened on clicking on this icon. You can pick the required color from it.

### Text effects

You can make the text Bold, Italic, Underline by clicking on the corresponding icons in the toolbar. By default, no effects will be applied.

### Alignment

Text can be aligned at the Left, Center or Right by clicking on the corresponding icon. By default, text will be aligned at the Left.


## Programmatical approach

Programmatically, you can add text on the image using the AddText method. This method requires the following parameters

* Text – Specify the content you need to add on the image.
* TextSettings - Used for text customization.

% tabs %} 

{% highlight C# %} 

editor.AddText("Hello", new TextSettings());

{% endhighlight %}

{% endtabs %} 

## Text settings

Using the following properties in the TextSettings, text can be customized.

* FontFamily - Font family of the text can be changed.
* FontSize - Font size of the text can be changed
* Color - Modifies the font color of the text.
* TextAlignment - Text alignment such as left, top, center can be applied.
* TextEffects - Text effects such as Bold, Italic, Underline can be applied.
* Opacity - Opacity of the text can be modified.
* Angle - Rotates the text to the specified angle.
* Bounds - Rect used to position the text. 

>N : Values of bounds will be in Percentage. For example (25, 25, 25, 25) will take the position of 25 percent from the left and top.

% tabs %} 

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

![ImageEditor](Images/Text.jpg)   

