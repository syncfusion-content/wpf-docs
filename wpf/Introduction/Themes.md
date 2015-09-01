---
layout: post
title: Themes
description: themes
platform: wpf
control: Introduction
documentation: ug
---

# Themes

Syncfusion offers enhanced theme support through Skin Manager.

The Skin Manager Framework provides a convenient way to give the appealing appearance to the WPF controls as well as the Syncfusion controls.

## Built In Skins

You can apply Skins to the control by setting the VisualStyle property defined in the Skin Storage class. Set the VisualStyle property to the corresponding theme. You can set this property either in XAML or C#.

_Property Table_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
VisualStyle</td><td>
Used for setting Skins for the controls. The Built-In-Skins are as follows.* Office2003* Office2007Blue* Office2007Black* Office2007Silver* ShinyRed* Blend* ShinyBlue* SyncOrange* VS2010* Office2010Blue* Office2010Black * Office2010Silver* Metro* Transparent</td><td>
<br>Attached Property</td><td>
String</td><td>
{{ '[Setting VisualStyle in XAML](http://docs.syncfusion.com/wpf/hierarchynavigator/skins#built-in-skins)' | markdownify }}{{ '[Setting VisualStyle in C#](http://docs.syncfusion.com/wpf/hierarchynavigator/skins#built-in-skins  )' | markdownify }}</td></tr>
</table>


## Setting VisualStyle in XAML

The following code example explains how to set the VisualStyle property in XAML.

1. Add the following namespace in the sample.

   ~~~ html
         xmlns:yncfusion=”http://schemas.syncfusion.com/wpf”
   ~~~
   {:.prettyprint}


2. Set the VisualStyle property for the control as illustrated in the following code example. 
  
   ~~~ html
           <Syncfusion:CalendarEdit syncfusion:SkinStorage.VisualStyle=”Blend”></Syncfusion:CalendarEdit>  
   ~~~
   {:.prettyprint}


   ### Setting VisualStyle in C&#35;                                     

   You can also set the VisualStyle property in C# by using the SetVisualStyle.

   The following code example explains how to set the VisualStyle property in C#.

3. Name the control by using the Name attribute.

   ~~~ html
         <Syncfusion:CalendarEdit Name=”calendar”></Syncfusion:CalendarEdit> 
   ~~~
   {:.prettyprint}




4. Add the following line in code behind file.

   ~~~ cs
         SkinStorage.SetVisualStyle(calendar, “Blend”);
   ~~~
   {:.prettyprint}

The output is displayed as follows.

![](Themes_images/Themes_img1.jpeg)


_Visual Style property for setting Skins_

## Customization

### Active Color Scheme

You can set the custom color for the WPF controls by using the ActiveColorScheme property defined in the Skin Manager class. You can set this property either in XAML or C#.

_Property Table_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
ActiveColorScheme  </td><td>
Sets the custom color for the controls. </td><td>
Attached Property</td><td>
SolidColorBrush</td><td>
{{ '[Setting ActiveColorScheme property in XAML](http://docs.syncfusion.com/wpf/ribbon/appearance#active-color-scheme)' | markdownify }}
{{ '[Setting ActiveColorScheme property in C#](http://docs.syncfusion.com/wpf/ribbon/appearance#active-color-scheme)' | markdownify }}</td></tr>
</table>


#### Setting ActiveColorScheme property in XAML

The following code example explains how to set the ActiveColorScheme property in XAML.

1. Add the following namespace in the sample.

   ~~~ html
  

           xmlns:Syncfusion=http://schemas.syncfusion.com/wpf

   ~~~
   {:.prettyprint}
2. Set the ActiveColorScheme property for the control as illustrated in the following code example.

   ~~~ html


          <Syncfusion:CalendarEdit Name=”calendar” Syncfusion:SkinManager.ActiveColorScheme=”Red”></Syncfusion:CalendarEdit> 

   ~~~
   {:.prettyprint}

   #### Setting ActiveColorScheme property in C&#35;

   You can also set the custom color for the WPF controls in C# by using _SetActiveColorScheme._

   The following code example explains how to set the ActiveColorScheme property in C#.

3. Name the control by using the Name attribute.

   ~~~ html
   
          <Syncfusion:CalendarEdit Name=”calendar”></Syncfusion:CalendarEdit> 

   ~~~
   {:.prettyprint}

4. Add the following line in code behind file.
   
   ~~~ cs


		SkinManager.SetActiveColorScheme(calendar, Brushes.Red);

   ~~~
   {:.prettyprint}

The output is displayed as follows.

![](Themes_images/Themes_img2.png)

_Custom color using ActiveColorScheme_

### Metro theme

The Metro theme is a well sophisticated theme that supports a complete customization over the brushes and fonts. You can change and customize each and every brushes of Metro Theme according to your requirement.

You can customize the following brushes in Metro Theme.

* MetroBrush
* MetroBackgroundBrush
* MetroPanelBackgroundBrush
* MetroBorderBrush
* MetroForegroundBrush
* MetroFontFamily
* MetroHoverBrush
* MetroFocusedBorderBrush
* MetroHighlightedForegroundBrush



#### Setting MetroBackgroundBrush property in XAML

{% highlight html %}


<yncfusion:ChromelessWindow x:Class=”WpfApplication18.MainWindow”       

        Title=”Window1” Height=”350” Width=”525” xmlns:yncfusion=”http://schemas.syncfusion.com/wpf” yncfusion:SkinStorage.VisualStyle=”Metro” yncfusion:SkinStorage.MetroBackgroundBrush=”Green”>

</yncfusion:ChromelessWindow>

{% endhighlight %}


#### Setting MetroBackgroundBrush property in C#
{% highlight c# %}


SkinStorage.SetMetroBrush(this, Brushes.Green);

{% endhighlight %}

![](Themes_images/Themes_img3.jpeg)

_Metro theme customization_

