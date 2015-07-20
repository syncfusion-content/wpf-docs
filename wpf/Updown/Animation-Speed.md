---
layout: post
title: Animation-Speed
description: animation speed
platform: wpf
control: UpDown Control
documentation: ug
---

# Animation Speed

When you change a value in the UpDown by using the repeat buttons, the transition from the current value to the new value is animated in the TextBox. You can control the speed of the animation by using the AnimationSpeed property.

Use of Animation Speed

The AnimationSpeed can be set for the UpDown control as shown in the following code example.

[XAML]

<syncfusion:UpDown Name="upDown" AnimationSpeed="30"/>



[C#]

UpDown upDown = new UpDown();

upDown. AnimationSpeed = 30;



Properties__

_AnimationSpeed Property_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
AnimationSpeed</td><td>
Gets or sets the MaxValidation.</td><td>
DependencyProperty</td><td>
double</td><td>
Not applicable.</td></tr>
</table>


