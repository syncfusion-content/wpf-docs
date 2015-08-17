---
layout: post
title: Set-Visual-Style-for-dynamically-added-Derived-Controls
description: set visual style for dynamically added derived controls
platform: wpf
control: SkinManager
documentation: ug
---

### Set Visual Style for dynamically added Derived Controls

Normally, a control added to an application will dynamically pick up the existing style using the Skin Manager. But when an user control derived from the existing control is added to an application, a style based on the Base class should be defined in the application. 

The following code snippet explains the scenario where an user control of Button type is exposed here.



[XAML]



<Button x:Class="WpfApplication2.TestButton"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 

         Height="300" Width="300" xmlns:theme="http://schemas.syncfusion.com/wpf" theme:SkinStorage.VisualStyle="Blend">  

&lt;/Button&gt;





[C#]



public partial class TestButton : Button

    {

        public TestButton()

        {

            InitializeComponent();

        }

    }





Styles based on the button style should be defined in the application as follows. You have to merge the corresponding Resource Dictionary when overriding the style in the application.



[XAML]



&lt;Application.Resources&gt;

        &lt;ResourceDictionary&gt;

            &lt;ResourceDictionary.MergedDictionaries&gt;

                &lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/BlendStyle.xaml"/&gt;

            &lt;/ResourceDictionary.MergedDictionaries&gt;        

        &lt;Style TargetType="local:TestButton" BasedOn="{StaticResource BlendButtonStyle}"&gt;

            &lt;Setter Property="Background" Value="GoldenRod"/&gt;

        &lt;/Style&gt;

        &lt;/ResourceDictionary&gt;

    &lt;/Application.Resources&gt;





The output is displayed as shown below.



![](Set-Visual-Style-for-dynamically-added-Derived-Controls_images/Set-Visual-Style-for-dynamically-added-Derived-Controls_img1.png)
{:.image }




