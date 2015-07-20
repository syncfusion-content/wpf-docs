---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: ButtonAdv
documentation: ug
---

# Getting Started

This section guides you on getting started with the ButtonAdv control. It describes you about the control structure, basic settings, implementation and members.

## Control Structure

{{ '![](Getting-Started_images/Getting-Started_img1.png)' | markdownify }}
{:.image }


_Control Structure_

## Add ButtonAdv Control to an application:

The ButtonAdv control is available in the following assembly:

*  Syncfusion.Shared.WPF
### Setting Label


The following code explains how to declare the ButtonAdv control using XAML.

[XAML]

<sync:ButtonAdv Label="Hello World"/>



The ButtonAdv control can be created using the C# code as follows:

[C#]

ButtonAdv button = new ButtonAdv()

button.Label = "Hello World";



{{ '![](Getting-Started_images/Getting-Started_img2.png)' | markdownify }}
{:.image }


### Set Size Mode

The size mode of the ButtonAdv control can be easily modified by using the property SizeMode. The SizeMode property contains the following values:

* Small
* Normal
* Large

Small Mode

When the SizeMode is set to Small, the icon of the ButtonAdv control is displayed without the label.

Use the following code example to set the SizeMode to Small:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Small" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Small;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img3.png)' | markdownify }}
{:.image }




Normal Mode

The ButtonAdv control retains the default appearance, when the SizeMode is set to Normal.

Use the following code example to set the SizeMode to Normal:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Normal" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Normal;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img4.png)' | markdownify }}
{:.image }


Large Mode

When the SizeMode is set to Large, the ButtonAdv control is displayed with large icon and provides multiline support.

Use the following code example to set the SizeMode to Large:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Large" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Large;</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img5.png)' | markdownify }}
{:.image }


### Setting Image

The image displayed on the control can be set using the following two properties:

* SmallIcon—To set the mage when SizeMode is Normal or Small.
* LargeIcon—To set the image when SizeMode is Large.



The SmallIcon property can be set as follows:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Small" Label="Hello World" SmallIcon="employee.png"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Small;button.SmallIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img6.png)' | markdownify }}
{:.image }




The SmallIcon property can be set even when the SizeMode is Normal:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Normal" SmallIcon="employee.png" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Normal;button.SmallIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img7.png)' | markdownify }}
{:.image }




The LargeIcon property can be set as follows:

<table>
<tr>
<td>
[XAML]<sync:ButtonAdv SizeMode="Large" LargeIcon="employee.png" Label="Hello World"/></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.SizeMode = SizeMode.Large;button.SmallIcon = new BitmapImage(new Uri("employee.png"));</td></tr>
</table>


{{ '![](Getting-Started_images/Getting-Started_img8.png)' | markdownify }}
{:.image }


### Set Icon Width and Height

The Iconsize can be set using the following two properties:

* IconWidth
* IconHeight

{{ '![](Getting-Started_images/Getting-Started_img9.png)' | markdownify }}
{:.image }




{{ '![](Getting-Started_images/Getting-Started_img10.png)' | markdownify }}
{:.image }




The IconWidth and IconHeight can be set as follows:

<table>
<tr>
<td>
[XAML]  <sync:ButtonAdv   SizeMode="Normal" IconHeight="20" IconWidth="20"  Label="Hello World"  SmallIcon ="female.png"  /></td></tr>
<tr>
<td>
[C#]ButtonAdv button = new ButtonAdv()button.Label = "Hello World";button.IconWidth=20;button.IconHeight=20;</td></tr>
</table>


## ButtonAdv Members

Properties

_Properties table_

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
Represents the Size of the element, that can be Normal, Small or Large</td><td>
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
Null</td><td>
LargeIcon</td></tr>
<tr>
<td>
IsCheckable</td><td>
Boolean</td><td>
True or False</td><td>
Button will act as a Checkable item if true</td><td>
False</td><td>
Checkable Support</td></tr>
<tr>
<td>
IsChecked</td><td>
Boolean</td><td>
True or False</td><td>
Represents the Checked state of the element</td><td>
False</td><td>
Checkable Support</td></tr>
<tr>
<td>
IsMultiline</td><td>
Boolean</td><td>
True or False</td><td>
Represents whether the Label displayed in two line or not</td><td>
True</td><td>
MultiLine Support</td></tr>
<tr>
<td>
Command</td><td>
ICommand</td><td>
ICommand</td><td>
Represents the command to invoke when the button is pressed</td><td>
Null</td><td>
Command Binding</td></tr>
<tr>
<td>
CommandParameter</td><td>
Object</td><td>
Object</td><td>
Represents the parameter to pass the Command property.</td><td>
Null</td><td>
Command Binding</td></tr>
<tr>
<td>
IconWidth</td><td>
double</td><td>
double</td><td>
Represents the width of the icon. </td><td>
16.0</td><td>
IconSize</td></tr>
<tr>
<td>
IconHeight</td><td>
double</td><td>
double</td><td>
Represents the height of the icon.</td><td>
16.0</td><td>
IconSize</td></tr>
</table>


Events

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
Click</td><td>
RoutedEventHandler</td><td>
RoutedEvent Args</td><td>
Occurs when ButtonAdv is pressed.</td><td>
Click</td></tr>
<tr>
<td>
Checked</td><td>
RoutedEventHandler</td><td>
RoutedEventArgs</td><td>
Occurs when the Button is Checked.</td><td>
Checked</td></tr>
</table>


