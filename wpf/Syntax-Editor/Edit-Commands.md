---
layout: post
title: Edit Commands in WPF Syntax Editor control | Syncfusion
description: Learn about Edit Commands support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Edit Commands in WPF Syntax Editor

Essential edit for WPF contains built-in RoutedUICommands for all editing and file operations such as select all, cut, copy, paste, new, open, save, save as and so on. The built-in RoutedUICommands can be bound to the edit control by using the **Command** property of the external controls such as button, menu item, and so on. The following lines of code can be used to bind the RoutedUICommands with external controls.

{% tabs %}

{% highlight XAML %}

<StackPanel>
    <Menu Background="Transparent" BorderThickness="0,0,1,2">
        <MenuItem Header="_File" Background="Transparent" Width="{Binding}" >
            <MenuItem Command="{x:Static sfedit:EditCommands.New}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Open}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Find}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Save}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.SaveAs}" CommandTarget="{Binding ElementName=Edit1}"/>
        </MenuItem>
        <MenuItem Header="_Edit" Background="Transparent" Width="{Binding}" >
            <MenuItem Command="{x:Static sfedit:EditCommands.Copy}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Cut}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Find}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Paste}" CommandTarget="{Binding ElementName=Edit1}"/>
            <MenuItem Command="{x:Static sfedit:EditCommands.Undo}" CommandTarget="{Binding ElementName=Edit1}"/>
        </MenuItem>
    </Menu>
    <sfedit:EditControl Name="Edit1" EnableOutlining="False" Height="270"
                        Background="white" AllowDrop="True" ShowLineNumber="True"/>
</StackPanel>

{% endhighlight %}

{% endtabs %}


The following image displays **Open** edit command window.

![Edit Commands enabled in Syntax Editor](Edit-Commands_images/edit-commands_img1.png)


