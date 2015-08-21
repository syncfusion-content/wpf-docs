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

### Use of Culture

Culture can be set to en-US for the UpDown control as shown in the following code example. The U.S. culture uses “.” as the NumberGroupSeparator.

{%highlight xml%}


<syncfusion:UpDown Name="upDown" Culture="en-US"/>

{%endhighlight%}


{%highlight c#%}


UpDown upDown = new UpDown();


upDown. Culture = new CultureInfo("en-US");

{%endhighlight%}

![](Culture_images/Culture_img1.jpeg)



Culture can also be set to bs-Latn for the UpDown control as shown in the following code example. The Latin culture uses “,” as the NumberGroupSeparator.

{%highlight xml%}


<syncfusion:UpDown Name="upDown" Culture="bs-Latn"/>

{%endhighlight%}

{%highlight c#%}


UpDown upDown = new UpDown();

upDown. Culture = new CultureInfo("bs-Latn");

{%endhighlight%}

![](Culture_images/Culture_img2.jpeg)



_Culture Property_

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
Culture</td><td>
Gets or sets the CultureInfo.</td><td>
DependencyProperty</td><td>
CultureInfo</td><td>
Not applicable.</td></tr>
</table>


