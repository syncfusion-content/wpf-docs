---
layout: post
title: Touch UI| SkinManager | Wpf | Syncfusion
description: touch ui 
platform: wpf
control: SkinManager
documentation: ug
---

# Touch UI 

The touch support allows users to interact with some Syncfusion WPF controls with finger gestures on touchscreen devices.

The following controls have touch styles implemented:

* Editors
* ComboBox
* ListBox Controls
* TreeView
* TabControl
* Menu
* GroupBar
* RangeSlider



## How To Apply Touch Styles

Touch styles can be applied to a control by setting the EnableTouch property defined in the SkinStorage class to True. This property can be set in either XAML or C#.

### Setting the EnableTouch Property in XAML



{% highlight xml %}



<syncfusion:IntegerTextBox 

         syncfusion:SkinStorage.EnableTouch="True" >

</syncfusion:IntegerTextBox >

{% endhighlight %}

##  Setting the EnableTouch Property in C#



{% highlight C# %}

SkinStorage.SetEnableTouch(this, true);


{% endhighlight %}


## Controls with Touch UI



![C:/Users/ramalakshmim/Desktop/New folder/New folder/screenshot008.png](Touch-UI_images/Touch-UI_img1.png)





![C:/Users/ramalakshmim/Desktop/New folder/New folder/Tree-touch.png](Touch-UI_images/Touch-UI_img2.png)



![C:/Users/ramalakshmim/Desktop/New folder/New folder/Menu-touch.png](Touch-UI_images/Touch-UI_img3.png)







