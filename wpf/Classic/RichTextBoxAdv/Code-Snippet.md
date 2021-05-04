---
layout: post
title: Code-Snippet in WPF Wizard Control control | Syncfusion
description: Learn here all about Code-Snippet support in Syncfusion WPF RichTextBoxAdv (Classic) control and more.
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Code-Snippet in WPF RichTextBoxAdv (Classic)


{% highlight xaml %}





	<Window x:Class="Testing.MainWindow"

	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

	xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

	Title="MainWindow" Height="350" Width="525">

	<Grid>

	<DockPanel>

	<Menu DockPanel.Dock="Top">

	<MenuItem Command="{x:Static syncfusion:RichTextBoxAdv.ToggleBold}" 

	Header="Bold"/>

	</Menu>

	<syncfusion:RichTextBoxAdv x:Name="richtextbox">

	<syncfusion:DocumentAdv>

	<syncfusion:SectionAdv>

	<syncfusion:ParagraphAdv>

	<syncfusion:SpanAdv Text="I am the Text...."/>

	</syncfusion:ParagraphAdv>

	</syncfusion:SectionAdv>

	</syncfusion:DocumentAdv>

	</syncfusion:RichTextBoxAdv>

	</DockPanel>

	</Grid>

</Window>
{% endhighlight %}


