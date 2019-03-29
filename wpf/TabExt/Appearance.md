---
layout: post
title: Appearance | TabControlExt | wpf | Syncfusion
description: appearance
platform: wpf
control: TabControlExt
documentation: ug
---

# Appearance

This section deals with the appearance of TabControlExt control and contains the following topic:

![Appearance](Appearance_images/Appearance_img1.jpeg)

## Setting Visual Styles

The appearance of the TabControlExt control is customized by using the VisualStyle property. This is an attached property which gets or sets the visual style for the control.

### Property table

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the TabControlExt control. The options provided are as follows.
<ul>
<li>Blend</li>
<li>Office2003</li>
<li>Office2007Blue</li>
<li>Office2007Black</li>
<li>Office2007Silver</li>
<li>ShinyBlue</li>
<li>ShinyRed</li>
<li>SyncOrange</li>
<li>VS2010</li>
<li>Metro</li>
<li>Transparent</li>
</ul>
</td></tr>
</table>


The following code example illustrates how to set the visual style for the TabControlExt.

{% tabs %}

{% highlight xaml %}

<!-- Adding TabControlExt -->

<syncfusion:TabControlExt Name="tabControlExt" syncfusion:SkinStorage.VisualStyle="Office2007Blue">

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

// Setting the visual style

// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();

// Creating the instance of StackPanel.

StackPanel stackPanel = new StackPanel();

// Creating instance of the TabItemExt

TabItemExt tabItemExt1 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";

// Adding TabItemExt to TabControlExt.

tabControlExt.Items.Add(tabItemExt1);

// Creating instance of the TabItemExt2

TabItemExt tabItemExt2 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt2.Header = "TabItemExt2";

// Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt2);

// Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 

// Setting the visual style as Office2007Blue

SkinStorage.SetVisualStyle(tabControlExt, "Office2007Blue");

{% endhighlight %}

{% endtabs %}

![Office2007 blue theme](Appearance_images/Appearance_img2.png)

![Office2007 black theme](Appearance_images/Appearance_img3.png)

![Office2007 silver theme](Appearance_images/Appearance_img4.png)

![Office2010 blue theme](Appearance_images/Appearance_img5.png)

![Office2010 black thee](Appearance_images/Appearance_img6.png)

![Office2010 silver theme](Appearance_images/Appearance_img7.png)

![VS2010 theme](Appearance_images/Appearance_img8.png)

![Blend theme](Appearance_images/Appearance_img9.jpeg)

![Metro theme](Appearance_images/Appearance_img10.png)

![Custom theme](Appearance_images/Appearance_img11.png)

## Customization

The style of the TabControlExt control can be customized by the customization properties. The following table lists the details of the customization properties.

### Customization Properties

* [TabItemSelectedBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemSelectedBackground.html)
* [TabItemSelectedBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemSelectedBorderBrush.html)
* [TabItemSelectedForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemSelectedForeground.html)
* [TabItemHoverBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemHoverBackground.html)
* [TabItemHoverBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemHoverBorderBrush.html)
* [TabItemHoverForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabControlExt~TabItemHoverForeground.html)


The following code example shows how to use the customization properties in the TabControlExt control.


{% highlight xaml %}

<sync:TabControlExt TabItemSelectedBackground="Gold" Height="100" Margin="100"

                            TabItemSelectedBorderBrush="BlueViolet" 

                            TabItemSelectedForeground="Black" 

                            TabItemHoverBackground="Goldenrod" 

                            TabItemHoverBorderBrush="BlueViolet" 

                            TabItemHoverForeground="Yellow">

                <sync:TabItemExt Header="TabItem1"/>

                <sync:TabItemExt Header="TabItem2"/>

                <sync:TabItemExt Header="TabItem3"/>              

</sync:TabControlExt>

{% endhighlight %}

The following screenshot is the sample output for the above code example.

![TabControl customization](Appearance_images/Appearance_img12.png)