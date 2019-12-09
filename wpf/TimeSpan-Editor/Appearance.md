---
layout: post
title: Appearance in WPF TimeSpanEdit control | Syncfusion
description:  Learn about Appearance support in Syncfusion WPF TimeSpanEdit control and more details about the control features.
platform: wpf
control: TimeSpanEdit
documentation: ug
---

# Appearance in WPF TimeSpanEdit

Appearance of TimeSpanEdit can be changed using different Styles.

### Visual Styles

`SkinManager` provides rich and professional look and feel UI for the TimeSpanEdit Control. Some of the available visual styles are as follows:

* Blend
* Office2007Blue
* Office2007Black
* Office2007Silver
* Office2010Blue
* Office2010Black
* Office2010Silver
* VS2010
* Metro
* Transparent

The visual style can be applied for the TimeSpanEdit using the `VisualStyle` property of the `SkinStorage`.

{% tabs %}

{% highlight XAML %}

<!--TimeSpanEdit Visual Style -->
<syncfusion:TimeSpanEdit x:Name="Tiem1"  Width="200" Height="23"  Value="10.2:25:52"  syncfusion:SkinStorage.VisualStyle="Blend" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

//Set Visual Style
SkinStorage.SetVisualStyle(timespan,"Blend");

{% endhighlight %}

{% highlight VB %}

'Set Visual Style
SkinStorage.SetVisualStyle(timespan,"Blend")

{% endhighlight %}

{% endtabs %}


**Blend Theme**

![](Style-images/Blend.png)


**Office2007Blue Theme**

![](Style-images/Office2007Blue.png)


**Office2007Black Theme**

![](Style-images/Office2007Black.png)


**Office2007Silver Theme**

![](Style-images/Office2007Silver.png)


**Office2010Blue Theme**

![](Style-images/Office2010Blue.png)


**Office2010Black Theme**

![](Style-images/Office2010Black.png)


**Office2010Silver Theme**

![](Style-images/Office2010Silver.png)

**VS2010 Theme**

![](Style-images/VS2010.png)

**Metro Theme**

![](Style-images/Metro.png)

**Transparent Theme**

![](Style-images/Transparent.png)