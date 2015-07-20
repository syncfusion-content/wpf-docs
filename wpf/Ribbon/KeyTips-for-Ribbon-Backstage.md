---
layout: post
title: KeyTips-for-Ribbon-Backstage
description: keytips for ribbon backstage
platform: wpf
control: Ribbon
documentation: ug
---

# KeyTips for Ribbon Backstage

The backstage feature of the Ribbon control provides KeyTip support to display KeyTips when users press the Alt key.

To display KeyTips for Ribbon Backstage



[XAML]

&lt;syncfusion:Backstage x:Name="RibbonBackStage" syncfusion:Ribbon.KeyTip="B"&gt;



 &lt;syncfusion:BackStageCommandButton Header="Save" syncfusion:Ribbon.KeyTip="S"   Command="Save"/&gt;

 &lt;syncfusion:BackStageCommandButton Header="SaveAs" syncfusion:Ribbon.KeyTip="A" Command="SaveAs"/&gt; 



 &lt;syncfusion:BackstageTabItem syncfusion:Ribbon.KeyTip="I" Header="Info"/&gt;                      

 &lt;syncfusion:BackstageTabItem syncfusion:Ribbon.KeyTip="R" Header="Recent"/&gt;



&lt;/syncfusion:Backstage&gt;





{ ![](KeyTips-for-Ribbon-Backstage_images/KeyTips-for-Ribbon-Backstage_img1.png) | markdownify }
{:.image }


