---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# Getting Started

This section guides you on getting started with the DropDownButtonAdv control. It describes you about the control structure, basic settings, implementation and members of the DropDownButtonAdv control.



{{ '![](Getting-Started_images/Getting-Started_img1.png)' | markdownify }}
{:.image }


## Adding DropDownButtonAdv to an application

The DropDownButtonAdv control is available in the following assembly:

*  Syncfusion.Shared.WPF
### Setting Label


The following code explains how to add a DropDownButtonAdv control using XAML:



 [XAML]

<sync:DropDownButtonAdv Label="Hello World"/>



The DropDownButtonAdv control can be created using C# as follows:



 [C#]

DropDownButtonAdv button = new DropDownButtonAdv()

button.Label = "Hello World";



{{ '![](Getting-Started_images/Getting-Started_img2.png)' | markdownify }}
{:.image }


### Setting Size Mode

The size mode of the DropDownButtonAdv can be easily modified using the property SizeMode. The SizeMode property contains the following values:

* Small
* Normal
* Large

Small Mode

When the SizeMode is set to Small, the icon of the DropDownButtonAdv control is displayed without the label.

Use the following code snippet to set the SizeMode to Small:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Small" Label="Hello World"/></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Small;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img3.png)' | markdownify }}
{:.image }


Normal Mode

The DropDownButtonAdv control retains the default appearance, when the SizeMode is set to Normal, 

Use the following code snippet to set the SizeMode to Normal:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Normal" Label="Hello World"/></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Normal;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img4.png)' | markdownify }}
{:.image }


Large Mode

When the SizeMode is set to Large, the DropDownButtonAdv control is displayed with large icon and provides multiline support.

Use the following code snippet to set the SizeMode to Large:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Large" Label="Hello World"/></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Large;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img5.png)' | markdownify }}
{:.image }


### Setting Image

The Image displayed in the control can be set using two properties:

* SmallIcon – To set the image when SizeMode is Normal or Small.
* LargeIcon – To set the image when SizeMode is Large.

The SmallIcon property can be set as follows:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Small" Label="Hello World" SmallIcon="employee.png"/></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Small;button.SmallIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img6.png)' | markdownify }}
{:.image }


The SmallIcon property can be set even when the SizeMode is Normal:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Normal" SmallIcon="employee.png" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]DropDownButtonAdv button = new DropDownButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Normal;button.SmallIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img7.png)' | markdownify }}
{:.image }


The LargeIcon property can be set as follows:



<table>
<tr>
<td>
 [XAML]<sync:DropDownButtonAdv SizeMode="Large" LargeIcon="employee.png" Label="Hello World"/></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv();button.Label = "Hello World";button.SizeMode = SizeMode.Large;button.LargeIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img8.png)' | markdownify }}
{:.image }


### Adding Items to DropDownButtonAdv

The DropDownMenuGroup acts as a container for the DropDownButtonAdv control, which provides customization such as Resizing, Header and Scrollbar support.

Adding DropDownMenuItems to DropDownButtonAdv:



<table>
<tr>
<td>
 [XAML]<shared:DropDownButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">   <shared:DropDownMenuGroup>       <shared:DropDownMenuItem Header="Menu Item 1"/>       <shared:DropDownMenuItem Header="Menu Item 2"/>       <shared:DropDownMenuItem Header="Menu Item 3"/>   </shared:DropDownMenuGroup></shared:DropDownButtonAdv></td></tr>
<tr>
<td>
 [C#]DropDownButtonAdv button = new DropDownButtonAdv();DropDownMenuGroup menu = new DropDownMenuGroup();DropDownMenuItem menuItem1 = new DropDownMenuItem();DropDownMenuItem menuItem2 = new DropDownMenuItem();DropDownMenuItem menuItem3 = new DropDownMenuItem();menu.Items.Add(menuItem1);menu.Items.Add(menuItem2);menu.Items.Add(menuItem3);button.Content = menu;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img9.png)' | markdownify }}
{:.image }


## DropDownButtonAdv Members

### Properties

_Property table_

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Value it accepts</td><td>
Description</td><td>
Default Value</td><td>
Reference Link</td></tr>
<tr>
<td>
Label</td><td>
String</td><td>
String</td><td>
The Label Property of this element can be set to any string value</td><td>
Null</td><td>
Label</td></tr>
<tr>
<td>
SizeMode</td><td>
SizeMode</td><td>
Normal,Small,        Large</td><td>
Represents the Size of the element, which may be Normal, Small or Large</td><td>
Normal</td><td>
SizeMode</td></tr>
<tr>
<td>
SmallIcon</td><td>
ImageSource</td><td>
Image URL</td><td>
Represents the Image displayed in the element, when size form is Small or Normal</td><td>
-</td><td>
SmallIcon</td></tr>
<tr>
<td>
LargeIcon</td><td>
ImageSource</td><td>
Image URL</td><td>
Represents the Image displayed in the element, when size form is Large</td><td>
-</td><td>
LargeIcon</td></tr>
<tr>
<td>
IsMultiline</td><td>
Boolean</td><td>
True or False</td><td>
Value which represents whether the Label displayed in two line or not.</td><td>
True</td><td>
Multiline Support</td></tr>
</table>
### Events

_Events table_

<table>
<tr>
<td>
Name</td><td>
Event Type</td><td>
Event Args Parameter</td><td>
Description</td><td>
Reference Link</td></tr>
<tr>
<td>
DropDownOpened</td><td>
RoutedEventHandler</td><td>
RoutedEvent Args</td><td>
Occurs after DropDown is opened.</td><td>
DropDownOpened</td></tr>
<tr>
<td>
DropDownOpening</td><td>
CancelEventHandler</td><td>
CancelEventArgs</td><td>
Occurs before DropDown is opened.</td><td>
DropDownOpening</td></tr>
<tr>
<td>
DropDownClosed</td><td>
RoutedEventHandler</td><td>
RoutedEvent Args</td><td>
Occurs after DropDown is closed.</td><td>
DropDownClosed</td></tr>
<tr>
<td>
DropDownClosing</td><td>
CancelEventHandler</td><td>
CancelEventArgs</td><td>
Occurs before DropDown is closed.</td><td>
DropDownClosing</td></tr>
</table>


