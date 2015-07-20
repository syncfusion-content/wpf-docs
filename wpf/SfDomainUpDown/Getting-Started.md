---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: DomainUpDown
documentation: ug
---

# Getting Started

Namespace:  Syncfusion.Windows.Controls.Input
Assembly:  Syncfusion.SfInput.WPF (in Syncfusion.SfInput.WPF.dll)

The following code sample shows how to create the DomainUpDown from code-behind and XAML:



[XAML]



&lt;Page xmlns:editors="clr-namespace:Syncfusion.Windows.Controls.Input;assembly=Syncfusion.SfInput.Wpf"&gt;

    &lt;Grid&gt;



        <editors:SfDomainUpDown x:Name="domainUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"/>

    &lt;/Grid&gt;

&lt;/Page&gt;





[C#]

SfDomainUpDown domainUpDown = new SfDomainUpDown();





