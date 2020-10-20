---
layout: post
title: Drag and Drop | Syncfusion | WPF EditControl
description: Learn here about how to dragging and dropping the selected text in the Syncfusion WPF Syntax Editor (EditControl).
platform: wpf
control: Syntax Editor
documentation: ug
---

## Selected Text Drag and Drop

You can drag and drop the selected text in a paragraph by setting the [AllowDragDrop](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_AllowDragDrop) property to true. By default, Dragging the selected text will perform a move operation, while dragging using the <kbd>Ctrl</kbd> key will perform a copy operation.

{% tabs %}

{% highlight XAML %}

<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Syntaxeditor_sample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        x:Class="Syntaxeditor_sample.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:EditControl Name="editControl" BorderThickness="1" AllowDragDrop="True" AllowDrop="True" EnableOutlining="False" DocumentLanguage="Custom" Text="Setting multi-line text from C# using Environment.NewLine." />
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

editControl.AllowDragDrop = true;

editControl.AllowDrop = true;

{% endhighlight %}

{% endtabs %}