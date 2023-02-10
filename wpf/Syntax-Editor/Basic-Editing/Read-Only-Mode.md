---
layout: post
title: Read Only Mode in WPF Syntax Editor control | Syncfusion
description: Learn about Read Only Mode support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Read Only Mode support

Edit WPF can also be used as a static control in order to view only the contents of the file. ReadOnly mode is enabled/disabled by using the [IsReadOnly](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_IsReadOnlyProperty) property of the EditControl class. The following code is used to set the ReadOnly mode for EditControl.

{% tabs %}

{% highlight XAML %}


<Window x:Class="UGDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:UGDemo"
        mc:Ignorable="d"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:EditControl x:Name="editControl"
                                Text="This is Syncfusion's EditControl"
                                IsReadOnly="True"/>
    </Grid>
</Window>



{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        EditControl editControl = new EditControl();
        editControl.Text = "This is Syncfusion's EditControl";
        editControl.IsReadOnly = true;
        this.Content = editControl;           
    }
}

{% endhighlight %}

{% endtabs %}