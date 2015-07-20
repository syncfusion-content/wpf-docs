---
layout: post
title: Culture
description: culture
platform: wpf
control: UpDown Control
documentation: ug
---

# Culture

The UpDown control provides globalization support by enabling you to change the culture of the control by using the Culture property.

Use of Culture

Culture can be set to en-US for the UpDown control as shown in the following code example. The U.S. culture uses “.” as the NumberGroupSeparator.

 [XAML]

<syncfusion:UpDown Name="upDown" Culture="en-US"/>



[C#]

UpDown upDown = new UpDown();

upDown. Culture = new CultureInfo("en-US");

{{ '![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1273.jpg](Culture_images/Culture_img1.jpeg)' | markdownify }}
{:.image }


Culture can also be set to bs-Latn for the UpDown control as shown in the following code example. The Latin culture uses “,” as the NumberGroupSeparator.

[XAML]

<syncfusion:UpDown Name="upDown" Culture="bs-Latn"/>



[C#]

UpDown upDown = new UpDown();

upDown. Culture = new CultureInfo("bs-Latn");



{{ '![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1274.jpg](Culture_images/Culture_img2.jpeg)' | markdownify }}
{:.image }


_Culture Property_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference Links</td></tr>
<tr>
<td>
Culture</td><td>
Gets or sets the CultureInfo.</td><td>
DependencyProperty</td><td>
CultureInfo</td><td>
Not applicable.</td></tr>
</table>


