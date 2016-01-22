---
layout: post
title: Appearance | OLAPGauge | wpf | Syncfusion
description: appearance
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Appearance

## How to set gauge radius?

The OLAP Gauge control provides support to adjust its radius. This is achieved by assigning a proper value to the radius property of OLAP Gauge.


{%tabs%}
{% highlight c# %}
 
this.olapGauge1.Radius = 100;

this.olapGauge1.DataBind();

 {% endhighlight %}

 {% highlight vbnet %}
 
Me.olapGauge1.Radius = 100

Me.olapGauge1.DataBind()

 {% endhighlight %}

{%endtabs%}




![](Appearance_images/Appearance_img1.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

## Explain the built-in frame types available for gauge control

OLAP Gauge supports built-in frame types to provide effective rim styles. The FrameType property is used to set the frame type for the Gauge control.

The following are the frame types supported by OLAP Gauge. 

* CircularWithInnerLeftGradient (Default)
* CircularWithDarkOuterFrames
* CircularCenterGradient
* CircularWithInnerTopGradient
* Full Circle 
* HalfCircle 



The following code example illustrates how to set the frame type for the OLAP Gauge control.


{%tabs%}

{% highlight c# %}
 
    



this.olapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient;

 {% endhighlight %}




 {% highlight vbnet %}
  
    



Me.olapGauge1.FrameType = GaugeFrameType.CircularWithInnerLeftGradient

 {% endhighlight %}





{%endtabs%}



The following screen shots illustrate the various frame types.

![](Appearance_images/Appearance_img2.png)


![](Appearance_images/Appearance_img3.png)




![](Appearance_images/Appearance_img4.png)


![](Appearance_images/Appearance_img5.png)


![](Appearance_images/Appearance_img6.png)




![](Appearance_images/Appearance_img7.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

## Explain the skin types that are available for Gauge control

The OLAP Gauge control allows you to present your data using different built-in-skins. These skins allow you to theme and style the look and feel of the control in various rich color schemes. You can use Skin Manager Framework to apply a wide range of skins to the Essential OLAP Gauge. These skins have been designed to suit the needs of a wide range of audience. The following are the types of skins available:

* Default-The visual style of this skin depends upon the operating System used. 
* Office2007Blue-This skin is similar to the Microsoft Office2007Blue skin. 
* Office2007Black-This skin is similar to the Microsoft Office2007Black skin. 
* Office2007Silver-This skin is similar to the Microsoft Office2007Silver skin. 
* Office2003Blue-This skin is similar to the Microsoft Office2003 skin. 
* Blend-This skin is similar to the Microsoft Blend skin. 
* Metro -This skin is similar to the Windows 8 Metro Style.



![](Appearance_images/Appearance_img8.png)


![](Appearance_images/Appearance_img9.png)


![](Appearance_images/Appearance_img10.png)


![](Appearance_images/Appearance_img11.png)


![](Appearance_images/Appearance_img12.png)


![](Appearance_images/Appearance_img13.png)


![C:/Users/manimala.paramasivam/Desktop/OlapGauge.png](Appearance_images/Appearance_img14.png)


## Applying Skins

The various skin themes available can be applied to the control using the SkinStorage.VisualStyle property. 

To set the visual style for the controls, use the code given below.


{%tabs%}

 {% highlight xaml %}

    



<!—To set Office2007Blue visual style for OLAP Gauge-->

<gauge:OlapGauge Name="olapGauge1" Radius="120" syncfusion:SkinStorage.VisualStyle="Office2007Blue"/>

 {% endhighlight %}



 {% highlight c# %}
 
    



//To set Office2007Blue visual style for Olap Gauge

SkinStorage.SetVisualStyle(olapGauge1, "Office2007Blue");

 {% endhighlight %}




 {% highlight vbnet %}
  
    



'To set Office2007Blue visual style for Olap Gauge

SkinStorage.SetVisualStyle(olapGauge1, "Office2007Blue");

 {% endhighlight %}
 
 {%endtabs%}


Run the code. The following output is obtained.

![](Appearance_images/Appearance_img15.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Version Number>\BI\WPF\OlapGauge.WPF\Samples\Gauge Customization\Customization Demo\

