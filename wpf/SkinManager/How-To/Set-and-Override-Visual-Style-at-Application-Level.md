---
layout: post
title: Set-and-Override-Visual-Style-at-Application-Level
description: set and override visual style at application level
platform: wpf
control: SkinManager
documentation: ug
---

### Set and Override Visual Style at Application Level

The Visual Styles can also be defined at application level. The VisualStyle property cannot be set at the application level. You have to merge the appropriate Resource Dictionary on Application resources which will cause all the controls to pick up the particular style.

The following code snippet explains how to override the Syncfusion Blend Style for the Ribbon Control at the application level.



[XAML]



<Application x:Class="WpfApplication2.App"

             xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

             StartupUri="MainWindow.xaml">



        &lt;Application.Resources&gt;

            &lt;ResourceDictionary&gt;

                &lt;ResourceDictionary.MergedDictionaries&gt;

                    &lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/BlendStyle.xaml"/&gt;

                &lt;/ResourceDictionary.MergedDictionaries&gt;

                &lt;Style TargetType="syncfusion:Ribbon" BasedOn="{StaticResource BlendRibbonStyle}"&gt;

                    &lt;Setter Property="FontSize" Value="19"/&gt;

                &lt;/Style&gt;

            &lt;/ResourceDictionary&gt;

        &lt;/Application.Resources&gt;

&lt;/Application&gt;



The output is displayed as shown below.



![](Set-and-Override-Visual-Style-at-Application-Level_images/Set-and-Override-Visual-Style-at-Application-Level_img1.png)
{:.image }


