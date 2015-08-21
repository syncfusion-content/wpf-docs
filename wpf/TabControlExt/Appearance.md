---
layout: post
title: Appearance
description: appearance
platform: wpf
control: TabControlExt
documentation: ug
---

# Appearance

This section deals with the appearance of TabControlExt control and contains the following topic:



![](Appearance_images/Appearance_img1.jpeg)





## Setting Visual Styles

The appearance of the TabControlExt control is customized by using the VisualStyle property. This is an attached property which gets or sets the visual style for the control.



Property table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the TabControlExt control. The options provided are as follows.
{{ '* Blend* Office2003* Office2007Blue* Office2007Black* Office2007Silver* ShinyBlue* ShinyRed* SyncOrange* VS2010* Metro* Transparent' | markdownify }}<br></td></tr>
</table>


The following code example illustrates how to set the visual style for the TabControlExt.


{% highlight xml %}



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




![C:/Users/ramalakshmim/Desktop/ugss/tab/7blue.png](Appearance_images/Appearance_img2.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/7black.png](Appearance_images/Appearance_img3.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/7silver.png](Appearance_images/Appearance_img4.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/10blue.png](Appearance_images/Appearance_img5.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/10black.png](Appearance_images/Appearance_img6.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/10silver.png](Appearance_images/Appearance_img7.png)





![C:/Users/ramalakshmim/Desktop/ugss/tab/vs2010.png](Appearance_images/Appearance_img8.png)





![](Appearance_images/Appearance_img9.jpeg)





![C:/Users/ramalakshmim/Desktop/ugss/tab/metro.png](Appearance_images/Appearance_img10.png)







![](Appearance_images/Appearance_img11.png)





## Customization

The style of the TabControlExt control can be customized by the customization properties. The following table lists the details of the customization properties.



Customization Properties

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
TabItemSelectedBackground</td><td>
Used to set the background color of the selected tab item.</td><td>
Dependency property</td><td>
Brush</td></tr>
<tr>
<td>
TabItemSelectedBorderBrush</td><td>
Used to set the border color of the selected tab item.</td><td>
Dependency property</td><td>
Brush</td></tr>
<tr>
<td>
TabItemSelectedForeground</td><td>
Used to set the foreground color of the selected tab item.</td><td>
Dependency property</td><td>
Brush</td></tr>
<tr>
<td>
TabItemHoverBackground</td><td>
Used to set the background color of the tab item in Hover state.</td><td>
Dependency property</td><td>
Brush</td></tr>
<tr>
<td>
TabItemHoverBorderBrush</td><td>
Used to set the border color of the tab item in Hover state.</td><td>
Dependency property</td><td>
Brush</td></tr>
<tr>
<td>
TabItemHoverForeground</td><td>
Used to set the foreground color of the tab item in Hover state.</td><td>
Dependency property</td><td>
Brush</td></tr>
</table>


The following code example shows how to use the customization properties in the TabControlExt control.


{% highlight xml %}

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



![](Appearance_images/Appearance_img12.png)









