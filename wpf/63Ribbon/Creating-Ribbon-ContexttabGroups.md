---
layout: post
title: Creating-Ribbon-ContexttabGroups
description: creating ribbon contexttabgroups
platform: wpf
control: Ribbon
documentation: ug
---

# Creating Ribbon ContexttabGroups

ContextTabGroups are used to group RibbonTabs in the application for easy navigation. Each ContextTabGroup can have a different background, label, and so on, to differentiate with other ContextTabGroups in the Ribbon window. The following code snippet is used to create a ContextTabGroup.



[XAML]



&lt;syncfusion:Ribbon x:Name="MyRibbon"&gt;

    &lt;syncfusion:Ribbon.ContextTabGroups&gt;

        &lt;syncfusion:ContextTabGroup Name="ContextTabGroup1" IsGroupVisible="True" BackColor="Aqua" Label="Group 1"&gt;

        &lt;/syncfusion:ContextTabGroup&gt;

        &lt;syncfusion::Ribbon.ContextTabGroups&gt;

&lt;/syncfusion:Ribbon&gt;



{ ![](Creating-Ribbon-ContexttabGroups_images/Creating-Ribbon-ContexttabGroups_img1.png) | markdownify }
{:.image }


