---
layout: post
title: Code-Snippet
description: code snippet
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Code Snippet



[XAML]



        <Window x:Class="Testing.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow" Height="350" Width="525">

    &lt;Grid&gt;

        &lt;DockPanel&gt;

            &lt;Menu DockPanel.Dock="Top"&gt;

                <MenuItem Command="{x:Static syncfusion:RichTextBoxAdv.ToggleBold}" 

                          Header="Bold"/>

            &lt;/Menu&gt;

            &lt;syncfusion:RichTextBoxAdv x:Name="richtextbox"&gt;

                &lt;syncfusion:DocumentAdv&gt;

                    &lt;syncfusion:SectionAdv&gt;

                        &lt;syncfusion:ParagraphAdv&gt;

                            &lt;syncfusion:SpanAdv Text="I am the Text...."/&gt;

                        &lt;/syncfusion:ParagraphAdv&gt;

                    &lt;/syncfusion:SectionAdv&gt;

                &lt;/syncfusion:DocumentAdv&gt;

            &lt;/syncfusion:RichTextBoxAdv&gt;

        &lt;/DockPanel&gt;

    &lt;/Grid&gt;

&lt;/Window&gt;



