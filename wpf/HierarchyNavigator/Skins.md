---
layout: post
title: Skins| Hierarchical Navigator | Wpf | Syncfusion
description: skins
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Skins

Hierarchy Navigator supports different skins such as Windows 7, Office2010Blue, Office2010Black, Office2010Silver, Office2007Blue, Office2007Black, Office2007Silver, and Expression Blend. 

## Built-in skins

The Windows 7 theme is applied to the HierarchyNavigator control by default.

Add the following assemblies to apply the corresponding theme for Hierarchy Navigator control. SkinStorage class is used to apply a different visual style for a control, which is available in Syncfusion.Shared.WPF project.

1. Create HierarchyNavigator instance either in XAML or code behind, as shown below.

{% tabs %}
{% highlight xaml %}

 <syncfusion:HierarchyNavigator x:Name="hierarchyNavigator"/>

{% endhighlight %}

{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

{% endhighlight %}
{% endtabs %}

2. Apply Visual Style as shown below in code behind by calling the static method in SkinStorage class in Syncfusion.Shared.WPF.

## Window7

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Default");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img1.png)



## Office2007Blue 

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Office2007Blue");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img2.png)



## Office2007Black

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Office2007Black");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img3.png)



## Office2007Silver

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Office2007Silver");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img4.png)




## Expression blend

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, "Blend");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img5.png)



## Metro theme

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, “Metro");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img6.png)



## Transparent theme

{% tabs %}
{% highlight C# %}

SkinStorage.SetVisualStyle(this, “Transparent");

{% endhighlight %}
{% endtabs %}

![](Skins_images/Skins_img7.png)



