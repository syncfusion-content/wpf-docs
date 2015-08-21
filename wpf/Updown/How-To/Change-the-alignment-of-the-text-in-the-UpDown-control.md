---
layout: post
title: Change-the-alignment-of-the-text-in-the-UpDown-control
description: change the alignment of the text in the updown control
platform: wpf
control: UpDown Control
documentation: ug
---

# Change the alignment of the text in the UpDown control

You can change the alignment of the text in the UpDown control by using the TextAlignment property. The following code can be used to set the TextAlignment for the UpDown control. 

The TextAlignment can set to the left in the UpDown control as shown in the following code example.

{%highlight xml%}
<syncfusion:UpDown Name="upDown" TextAlignment="Left"

>
 </ syncfusion:UpDown> 

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.TextAlignment = TextAlignment.Left;

{%endhighlight%}

![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1276.png](Change-the-alignment-of-the-text-in-the-UpDown-control_images/Change-the-alignment-of-the-text-in-the-UpDown-control_img1.png)





The TextAlignment can be set to the right in the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown Name="upDown" TextAlignment="Right"

>
 </ syncfusion:UpDown> 

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.TextAlignment = TextAlignment.Right;
{%endhighlight%}

![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1277.png](Change-the-alignment-of-the-text-in-the-UpDown-control_images/Change-the-alignment-of-the-text-in-the-UpDown-control_img2.png)



The TextAlignment can be set to the center in the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown Name="upDown" TextAlignment="Center"> 
</ syncfusion:UpDown> 

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.TextAlignment = TextAlignment.Center;

{%endhighlight%}

![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1278.png](Change-the-alignment-of-the-text-in-the-UpDown-control_images/Change-the-alignment-of-the-text-in-the-UpDown-control_img3.png)



The TextAlignment can be set to Justify in the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown Name="upDown" TextAlignment=" Justify "> 
</ syncfusion:UpDown>

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.TextAlignment = TextAlignment.Justify;

{%endhighlight%}

![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1276.png](Change-the-alignment-of-the-text-in-the-UpDown-control_images/Change-the-alignment-of-the-text-in-the-UpDown-control_img4.png)



