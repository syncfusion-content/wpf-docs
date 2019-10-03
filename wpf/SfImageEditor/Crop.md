---
layout: post
title: Image cropping in SfImageEditor WPF.
description: Image cropping
platform: wpf
control: SfImageEditor
documentation: ug
---

# Crop

Image can be cropped both via toolbar and propgrammatically.

## Toolbar cropping

To crop the image click on the Crop icon in the toolbar. Cropping handles will be added on the image, you can resize the handles to crop the required portion.

Upon clicking the crop icon, sub toolbar will be displayed below the main toolbar. After selecting the croping portion click Ok in the sub toolbar to crop that selected portion.

Sub toolbar contains the folling the icons.

* Width - You can specify the width of the cropping area.
* Height - You can specify the height of the cropping area.
* Ok - Clicking on this icon selected portion will be cropped.
* Cancel - On clicking this icon cropping handles will be removed.

N> On specifying width and height cropping area is located from the left top corner.

You can also perform continous cropping on the image.

Below image describes the area selected for cropping.

![ImageEditor](Images/ToolbarCropArea.png) 

Below is the image taken after performing cropping on the selected area.

![ImageEditor](Images/CroppedImage.jpg) 

## Programmatical cropping

Cropping can be done programmatically using  the following two methods in image editor.

* ToggleCropping - Used to select the cropping area.
* Crop - Crops the selected area in teh image.

### Toggle cropping

Toggle cropping mathos takes 3 paramters.

### Crop area selection

Below method will select the full image area for cropping and you can resize as per your wish

% tabs %} 

{% highlight C# %} 

editor.ToggleCropping();

{% endhighlight %}

{% endtabs %} 

Below method with get the ratio as the paramter to select the cropping area.

% tabs %} 

{% highlight C# %} 

editor.ToggleCropping(25,25);

{% endhighlight %}

{% endtabs %} 

![ImageEditor](Images/CroppingRatio.png) 

Below method with get the rect in terms of percentage to select the cropping area.

% tabs %} 

{% highlight C# %} 

Rect rect = new Rect(20, 20, 50, 50);
editor.ToggleCropping(rect);

{% endhighlight %}

{% endtabs %} 

![ImageEditor](Images/CroppingRect.png) 

### Crop

After selecting the crop area use Crop method in the image editor to crop the selected portion as in the below method.

% tabs %} 

{% highlight C# %} 

editor.Crop(new Rect(0, 0, 0, 0)

{% endhighlight %}

{% endtabs %} 

### Manual cropping

To manually select and crop the location use the same Crop method but specify the portion to br cropped in terms of rect as in the below code.

% tabs %} 

{% highlight C# %} 

editor.Crop(new Rect(0, 0, 0, 0)

{% endhighlight %}

{% endtabs %} 

![ImageEditor](Images/ManualCrop.png) 
