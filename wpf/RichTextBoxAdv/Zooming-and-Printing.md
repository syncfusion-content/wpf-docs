---
layout: post
title: Zooming-and-Printing
description: zooming and printing
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Zooming and Printing

RichTextBoxAdv allows you to zoom in and out on the content of the document. CTRL + mouse wheel will zoom in and zoom out the content of the RichTextBoxAdv control.



![](Zooming-and-Printing_images/Zooming-and-Printing_img1.png)





The printing feature permits users to print the content of the document using PrintDocument().

We can also use the Print command which will execute the PrintDocument method whenever it is hooked to the command property.


{% highlight C# %}

[C#]

__RichTextBox.PrintDocument();

{% endhighlight %}



## Properties



_Property Table_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td></tr>
<tr>
<td>
IsZoomEnabled</td><td>
Decides whether the content of the RichTextBoxAdv can be zoomed or not.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ZoomFactor</td><td>
Factor to show the zoomed value. It ranges from 0.1 to 1.</td><td>
Dependency Property</td><td>
Double</td></tr>
</table>


## Methods



_Property Table_

<table>
<tr>
<td>
Method</td><td>
Description</td><td>
Parameters</td><td>
Type</td><td>
Return Type</td></tr>
<tr>
<td>
ResetZooming()</td><td>
Resets the zoom.</td><td>
NA</td><td>
NA</td><td>
Void</td></tr>
<tr>
<td>
PrintDocument()</td><td>
Prints the content of the RichTextBoxAdv.</td><td>
NA</td><td>
NA</td><td>
Void</td></tr>
</table>


