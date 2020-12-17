---
layout: post
title: Line Numbers property of the Syncfusion Edit Control for WPF
description: Line Numbers property of the Syncfusion Edit Control for WPF used to show the line numbers for the content in the EditControl.
platform: wpf
control: Syntax Editor
documentation: ug
---

## Line Numbers

Edit WPF enables users to display line numbers for the content in the EditControl. Line numbers can be displayed or hidden by using the `ShowLineNumber` property of the EditControl class. The following lines of code can be used to display or hide line numbers in EditControl.

{% tabs %}

{% highlight XAML %}

<sfedit:EditControl Name="editControl" ShowLineNumber="False">

</sfedit:EditControl>




{% endhighlight %}

{% highlight C# %}

editControl.ShowLineNumber = false;

{% endhighlight %}

{% endtabs %}

The following image displays hidden line numbers.



![Line Number](Line-Numbers_images/Line-Numbers_img1.jpeg)

## Events

### CaretPositionChanged

[CaretPositionChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_CaretPositionChanged) event occurs when the caret position of the text in the `EditControl` is changed.
This event receives two arguments namely `sender` that handles `EditControl` and [CaretPositionEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.CaretPositionEventArgs.html) as objects.

The [CaretPositionEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.CaretPositionEventArgs.html) object contains the following properties:

* [LineNumber](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_LineNumber) - Gets the current line number value of the EditControl.
* [CursorIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_CursorIndex) - Gets the current cursor index value of the EditControl.
