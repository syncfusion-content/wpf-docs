---
layout: post
title: Editing Text of the Edit Control for WPF
description: Editing Text of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

## Editing Text in EditControl

EditControl supports displaying or editing string values with any number of lines. It also supports all basic editing operations such as typing, cut, copy, paste, delete, backspace, undo and redo operations.

EditControl supports performing edit operations through keyboard and mouse. It supports shortcut keys for basic editing operations such as cut, copy, paste, undo and redo operations. EditControl also has a built-in context menu to perform common editing operations such undo, redo, cut, copy, paste, select all operations using mouse. User can enable/ disable the built- in context menu. For more information refer to [Default Context Menu](#_Default_Context_Menu ).

`Text` property of the EditControl contains the text available in the EditControl at any point of time. The Text property of EditControl gets updated when you edit the text in the control by typing, editing the text by cut, paste, delete, undo or redo operations or by setting the Text property exclusively at runtime. The TextChanged event of EditControl gets raised when the Text property gets changed. Refer to [EditControl Events](#_Events ) section to know more about TextChanged and other events available in EditControl.

Set a simple string as EditControl’s Text by using the following line of code.

{% tabs %}

{% highlight XAML %}

<sfedit:EditControl x:Name="editControl" Text="This is Syncfusion's EditControl"/>



{% endhighlight %}

{% highlight C# %}

editControl.Text = "Setting Text property from code behind (C#)";

{% endhighlight %}

{% endtabs %}

To set a multi-line string as Text property through **XAML**, String class in **mscorlib**.**dll** can be used with **xml**:**space**=”**preserve**”. The following lines of code can be used to set a multiline text from **XAML**.

{% tabs %}

{% highlight XAML %}
<sfedit:EditControl x:Name="editControl">

<library:String xml:space="preserve" xmlns:library="clr-namespace:System;assembly=mscorlib">Setting multiline

Text using String class in mscorlib.dll.

When preserve is used, XAML considers the indentation spaces as empty spaces.

</library:String>

</sfedit:EditControl>



{% endhighlight %}

{% endtabs %}

The following image displays the multi-line text set from XAML.

![](Editing-Text-in-EditControl_images/Editing-Text-in-EditControl_img1.jpeg)

{% tabs %}

{% highlight C# %}

editControl.Text = @"Setting multi-line text" + Environment.NewLine + "from C# using" + Environment.NewLine + "Environment.NewLine.";





{% endhighlight %}

{% endtabs %}

The following image displays the multi-line text set from C#.

![](Editing-Text-in-EditControl_images/Editing-Text-in-EditControl_img2.jpeg)


