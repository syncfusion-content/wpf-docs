---
layout: post
title: Appearance
description: appearance
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Appearance

# How to set gauge radius?

The OLAP Gauge control provides support to adjust its radius. This is achieved by assigning a proper value to the radius property of OLAP Gauge.

{% highlight c# %}
 
   [C#]



this.olapGauge1.Radius = 100;

this.olapGauge1.DataBind();

 {% endhighlight %}




 {% highlight vbnet %}
  
    [VB]



Me.olapGauge1.Radius = 100

Me.olapGauge1.DataBind()

 {% endhighlight %}









![C:/Users/Hari/Pictures/OlapGauge/Radius.png](Appearance_images/Appearance_img1.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

# Explain the built-in frame types available for gauge control

OLAP Gauge supports built-in frame types to provide effective rim styles. The FrameType property is used to set the frame type for the Gauge control.

The following are the frame types supported by OLAP Gauge. 

* CircularWithInnerLeftGradient (Default)
* CircularWithDarkOuterFrames
* CircularCenterGradient
* CircularWithInnerTopGradient
* Full Circle 
* HalfCircle 



The following code example illustrates how to set the frame type for the OLAP Gauge control.

{% highlight c# %}
 
    [C#]



this.olapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient;

 {% endhighlight %}




 {% highlight vbnet %}
  
    [VB]



Me.olapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient

 {% endhighlight %}









The following screen shots illustrate the various frame types.

![C:/Users/Hari/Pictures/OlapGauge/CircularWithInnerLeftGradient.png](Appearance_images/Appearance_img2.png)


![C:/Users/Hari/Pictures/OlapGauge/CircularWithDarkOuterFrames.png](Appearance_images/Appearance_img3.png)




![C:/Users/Hari/Pictures/OlapGauge/CircularCenterGradient.png](Appearance_images/Appearance_img4.png)


![C:/Users/Hari/Pictures/OlapGauge/CircularWithInnerTopGradient.png](Appearance_images/Appearance_img5.png)


![C:/Users/Hari/Pictures/OlapGauge/Full Circle.png](Appearance_images/Appearance_img6.png)




![C:/Users/Hari/Pictures/OlapGauge/Half Circle.png](Appearance_images/Appearance_img7.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

# Explain the skin types that are available for Gauge control

The OLAP Gauge control allows you to present your data using different built-in-skins. These skins allow you to theme and style the look and feel of the control in various rich color schemes. You can use Skin Manager Framework to apply a wide range of skins to the Essential OLAP Gauge. These skins have been designed to suit the needs of a wide range of audience. The following are the types of skins available:

* Default-The visual style of this skin depends upon the operating System used. 
* Office2007Blue-This skin is similar to the Microsoft Office2007Blue skin. 
* Office2007Black-This skin is similar to the Microsoft Office2007Black skin. 
* Office2007Silver-This skin is similar to the Microsoft Office2007Silver skin. 
* Office2003Blue-This skin is similar to the Microsoft Office2003 skin. 
* Blend-This skin is similar to the Microsoft Blend skin. 
* Metro -This skin is similar to the Windows 8 Metro Style.



![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/Default%20Theme.png](Appearance_images/Appearance_img8.png)


![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/Office2007Blue%20Theme.png](Appearance_images/Appearance_img9.png)


![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/Black%202007%20theme.png](Appearance_images/Appearance_img10.png)


![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/silver%20Theme.png](Appearance_images/Appearance_img11.png)


![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/Blend%20Theme.png](Appearance_images/Appearance_img12.png)


![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/2003%20Blue%20theme.png](Appearance_images/Appearance_img13.png)


![C:/Users/manimala.paramasivam/Desktop/OlapGauge.png](Appearance_images/Appearance_img14.png)


## Applying Skins

The various skin themes available can be applied to the control using the _SkinStorage.VisualStyle_ property. 

To set the visual style for the controls, use the code given below.

 {% highlight xml %}

    [XAML]



<!—To set Office2007Blue visual style for OLAP Gauge-->

<gauge:OlapGauge Name="olapGauge1" Radius="120" syncfusion:SkinStorage.VisualStyle="Office2007Blue"/>

 {% endhighlight %}



 {% highlight c# %}
 
    [C#]



//To set Office2007Blue visual style for Olap Gauge

SkinStorage.SetVisualStyle(olapGauge1, "Office2007Blue");

 {% endhighlight %}




 {% highlight vbnet %}
  
    [VB]



'To set Office2007Blue visual style for Olap Gauge

SkinStorage.SetVisualStyle(olapGauge1, "Office2007Blue");

 {% endhighlight %}


Run the code. The following output is obtained.

![http://help.syncfusion.com/ug_82/WPFBI_Gauge/Images/Office2007Blue%20Theme.png](Appearance_images/Appearance_img15.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

