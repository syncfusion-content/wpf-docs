---
layout: post
title: Restrict the editing of value in the TextBox | UpDownControl | wpf | Syncfusion
description: restrict the editing of value in the textbox
platform: wpf
control: UpDown Control
documentation: ug
---

# Restrict the editing of value in the TextBox

You can restrict the editing of value in the TextBox by setting the AllowEdit property to false as shown in the following code example.
{%tabs%}
{%highlight xml%}

<syncfusion:UpDown Name="upDown" AllowEdit="false">
 </ syncfusion:UpDown>

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.AllowEdit = false;


{%endhighlight%}

{%endtabs%}




