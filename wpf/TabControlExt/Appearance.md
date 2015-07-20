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



{{ '![](Appearance_images/Appearance_img1.jpeg)' | markdownify }}
{:.image }




## Setting Visual Styles

The appearance of the TabControlExt control is customized by using the VisualStyle property. This is an attached property which gets or sets the visual style for the control.



_Property table_

<table>
<tr>
<td>
Property</td><td>
Description</td></tr>
<tr>
<td>
VisualStyle</td><td>
Sets the visual style for the TabControlExt control. The options provided are as follows.* Blend* Office2003* Office2007Blue* Office2007Black* Office2007Silver* ShinyBlue* ShinyRed* SyncOrange* VS2010* Metro* Transparent<br></td></tr>
</table>


The following code example illustrates how to set the visual style for the TabControlExt.



[XAML]



<!-- Adding TabControlExt -->

<syncfusion:TabControlExt Name="tabControlExt" syncfusion:SkinStorage.VisualStyle="Office2007Blue">



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>



    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"/>

</syncfusion:TabControlExt>



[C#]



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





{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/7blue.png](Appearance_images/Appearance_img2.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/7black.png](Appearance_images/Appearance_img3.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/7silver.png](Appearance_images/Appearance_img4.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/10blue.png](Appearance_images/Appearance_img5.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/10black.png](Appearance_images/Appearance_img6.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/10silver.png](Appearance_images/Appearance_img7.png)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/vs2010.png](Appearance_images/Appearance_img8.png)' | markdownify }}
{:.image }




{{ '![](Appearance_images/Appearance_img9.jpeg)' | markdownify }}
{:.image }




{{ '![C:/Users/ramalakshmim/Desktop/ugss/tab/metro.png](Appearance_images/Appearance_img10.png)' | markdownify }}
{:.image }






{{ '![](Appearance_images/Appearance_img11.png)' | markdownify }}
{:.image }




## Customization

The style of the TabControlExt control can be customized by the customization properties. The following table lists the details of the customization properties.



_Customization Properties_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<th>
TabItemSelectedBackground</th><th>
Used to set the background color of the selected tab item.</th><th>
Dependency property</th><th>
Brush</th></tr>
<tr>
<th>
TabItemSelectedBorderBrush</th><th>
Used to set the border color of the selected tab item.</th><th>
Dependency property</th><th>
Brush</th></tr>
<tr>
<th>
TabItemSelectedForeground</th><th>
Used to set the foreground color of the selected tab item.</th><th>
Dependency property</th><th>
Brush</th></tr>
<tr>
<th>
TabItemHoverBackground</th><th>
Used to set the background color of the tab item in Hover state.</th><th>
Dependency property</th><th>
Brush</th></tr>
<tr>
<th>
TabItemHoverBorderBrush</th><th>
Used to set the border color of the tab item in Hover state.</th><th>
Dependency property</th><th>
Brush</th></tr>
<tr>
<th>
TabItemHoverForeground</th><th>
Used to set the foreground color of the tab item in Hover state.</th><th>
Dependency property</th><th>
Brush</th></tr>
</table>


The following code example shows how to use the customization properties in the TabControlExt control.



[XAML]

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





The following screenshot is the sample output for the above code example.



{{ '![](Appearance_images/Appearance_img12.png)' | markdownify }}
{:.image }








