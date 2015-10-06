---
layout: post
title: KeyTips for Ribbon Backstage | Ribbon | WPF | Syncfusion
description: keytips for ribbon backstage
platform: wpf
control: Ribbon
documentation: ug
---

# KeyTips for Ribbon Backstage

The backstage feature of the Ribbon control provides KeyTip support to display KeyTips when users press the Alt key.

## To display KeyTips for Ribbon Backstage

{% highlight xml %}

   

<syncfusion:Backstage x:Name="RibbonBackStage" syncfusion:Ribbon.KeyTip="B">



 <syncfusion:BackStageCommandButton Header="Save" syncfusion:Ribbon.KeyTip="S"   Command="Save"/>

 <syncfusion:BackStageCommandButton Header="SaveAs" syncfusion:Ribbon.KeyTip="A" Command="SaveAs"/> 



 <syncfusion:BackstageTabItem syncfusion:Ribbon.KeyTip="I" Header="Info"/>                      

 <syncfusion:BackstageTabItem syncfusion:Ribbon.KeyTip="R" Header="Recent"/>



</syncfusion:Backstage>

 {% endhighlight %}







![](KeyTips-for-Ribbon-Backstage_images/KeyTips-for-Ribbon-Backstage_img1.png)


