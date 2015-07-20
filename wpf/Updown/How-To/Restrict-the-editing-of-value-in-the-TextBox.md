---
layout: post
title: Restrict-the-editing-of-value-in-the-TextBox
description: restrict the editing of value in the textbox
platform: wpf
control: UpDown Control
documentation: ug
---

### Restrict the editing of value in the TextBox

You can restrict the editing of value in the TextBox by setting the AllowEdit property to false as shown in the following code example.

 [XAML]

&lt;syncfusion:UpDown Name="upDown" AllowEdit="false"&gt;
 &lt;/ syncfusion:UpDown&gt;



[C#]

UpDown upDown = new UpDown();

upDown.AllowEdit = false;







