---
layout: post
title: Edit Commands in WPF Syntax Editor control | Syncfusion
description: Learn about Edit Commands support in Syncfusion WPF Syntax Editor control and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Edit Commands in WPF Syntax Editor

Essential edit for WPF contains built-in RoutedUICommands for all editing and file operations such as select all, cut, copy, paste, new, open, save, save as and so on. The built-in RoutedUICommands can be bound to the edit control by using the **Command** property of the external controls such as button, menu item, and so on. The following lines of code can be used to bind the RoutedUICommands with external controls.

{% tabs %}

{% highlight XAML %}

<Menu BorderBrush="LightGray" BorderThickness="0,0,1,2" Grid.ColumnSpan="1">

<MenuItem Header="_File" Background="Transparent" Width="{Binding}" >

<MenuItem Command="{x:Static sfedit:EditCommands.New}" CommandTarget="{Binding ElementName=Edit1}"/>

<MenuItem Command="{x:Static sfedit:EditCommands.Open}" CommandTarget="{Binding ElementName=Edit1}"/>

<MenuItem Command="{x:Static sfedit:EditCommands.Save}" CommandTarget="{Binding ElementName=Edit1}"/>

<MenuItem Command="{x:Static sfedit:EditCommands.SaveAs}" CommandTarget="{Binding ElementName=Edit1}"/>

</MenuItem>

</Menu>

<Border BorderThickness="1" BorderBrush="Gray"  Grid.Row="1" Grid.ColumnSpan="2">

<sfedit:EditControl Name="Edit1" EnableOutlining="False" Background="white" AllowDrop="True" BorderBrush="Black" BorderThickness="0" Margin="0" ShowLineNumber="True"



Grid.Row="1" >

</sfedit:EditControl>

</Border>



{% endhighlight %}

{% endtabs %}


The following image displays **Open** edit command window.

![Edit Commands enabled in Syntax Editor](Edit-Commands_images/Edit-Commands_img1.png)


