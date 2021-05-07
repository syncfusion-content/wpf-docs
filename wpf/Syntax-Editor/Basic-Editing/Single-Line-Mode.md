---
layout: post
title: Single Line Mode in WPF Syntax Editor control | Syncfusion
description: Learn about Single Line Mode support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

## Single Line Mode

Single Line Mode interprets all lines of code as a single line. It appears as a regular textbox with syntax highlighting, editing, clipboard operation, etc. by setting the [IsMultiLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_IsMultiLine) property to `false`.The default value is `true`.

{% tabs %}

{% highlight XAML %}

<sfedit:EditControl Name="editControl" IsMultiLine = "False">

</sfedit:EditControl>




{% endhighlight %}

{% highlight C# %}

editControl.IsMultiLine = false;

{% endhighlight %}

{% endtabs %}

![Single Line Mode enabled in Syntax Editor](Single-Line-Mode_images\Single-Line-Mode_img1.png)


