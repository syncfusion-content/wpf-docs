---
layout: post
title: Animation Speed | UpDownControl | wpf | Syncfusion
description: animation speed
platform: wpf
control: UpDown Control
documentation: ug
---

# Animation Speed

When you change a value in the UpDown by using the repeat buttons, the transition from the current value to the new value is animated in the TextBox. You can control the speed of the animation by using the AnimationSpeed property.

### Use of Animation Speed

The AnimationSpeed can be set for the UpDown control as shown in the following code example.


{%tabs%}
{%highlight xml%}


<syncfusion:UpDown Name="upDown" AnimationSpeed="30"/>

{%endhighlight%}


{%highlight c#%}

UpDown upDown = new UpDown();

upDown. AnimationSpeed = 30;

{%endhighlight%}
{%endtabs%}

### Properties



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
AnimationSpeed</td><td>
Gets or sets the MaxValidation.</td><td>
DependencyProperty</td><td>
double</td><td>
Not applicable.</td></tr>
</table>


