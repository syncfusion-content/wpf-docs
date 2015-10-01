---
layout: post
title: Culture | TheappearanceoftheUpDowncontrolcanbecustomizedbyusingtheVisualStyleproperty.Thefollowingarethebuilt-inskinsfortheUpDown | wpf | Syncfusion
description: culture
platform: wpf
control: UpDown Control
documentation: ug
---

# Culture

The UpDown control provides globalization support by enabling you to change the culture of the control by using the Culture property.

### Use of Culture

Culture can be set to en-US for the UpDown control as shown in the following code example. The U.S. culture uses “.” as the NumberGroupSeparator.


{%tabs%}
{%highlight xml%}


<syncfusion:UpDown Name="upDown" Culture="en-US"/>

{%endhighlight%}


{%highlight c#%}


UpDown upDown = new UpDown();


upDown. Culture = new CultureInfo("en-US");

{%endhighlight%}

{%endtabs%}

![](Culture_images/Culture_img1.jpeg)



Culture can also be set to bs-Latn for the UpDown control as shown in the following code example. The Latin culture uses “,” as the NumberGroupSeparator.


{%tabs%}
{%highlight xml%}


<syncfusion:UpDown Name="upDown" Culture="bs-Latn"/>

{%endhighlight%}

{%highlight c#%}


UpDown upDown = new UpDown();

upDown. Culture = new CultureInfo("bs-Latn");

{%endhighlight%}

{%endtabs%}

![](Culture_images/Culture_img2.jpeg)



Culture Property

{:.caption}

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
Culture</td><td>
Gets or sets the CultureInfo.</td><td>
DependencyProperty</td><td>
CultureInfo</td><td>
Not applicable.</td></tr>
</table>


