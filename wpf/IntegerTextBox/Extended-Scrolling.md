---
layout: post
title: Extended-Scrolling
description: extended scrolling
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Extended Scrolling

The EnableExtendedScrolling property is used to change the values based on the click and drag direction of the mouse movments. The range will increase when the mouse moves to the right or top of the screen, and will decrease when the mouse moves in the direction of the left or bottom of the screen. Before that, the control should be in an unfocused state.

{ ![](Extended-Scrolling_images/Extended-Scrolling_img1.png) | markdownify }
{:.image }


## Adding Extended Scrolling to an Application 

The EnableExtendedScrolling property must be set either in XAML or the code file.

<table>
<tr>
<td>
[XAML]  EnableExtendedScrolling ="True"</td></tr>
<tr>
<td>
[C#]  control.EnableExtendedScrolling = true;</td></tr>
</table>


