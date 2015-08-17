---
layout: post
title: LineBreaks-in-RibbonButton-Label
description: linebreaks in ribbonbutton label
platform: wpf
control: Ribbon
documentation: ug
---

# LineBreaks in RibbonButton Label

It is now possible to display the RibbonButton Label in multiple lines. It provides the following option to insert line breaks in RibbonButton Label.

Setting RibbonButton label in multiple lines:



<table>
<tr>
<td>
[XAML] <!--RibbonButton with IsMultiLine set to true-->        <syncfusion:RibbonButton Name="ribbonButton"  IsMultiLine="True" Label="Ribbon Button Label \nwill be displayed in \nmultiple lines"/></td></tr>
<tr>
<td>
[C#]//RibbonButton with IsMultiline set to trueribbonButton.IsMultiLine = true;ribbonButton.Label = "Ribbon Button Label \nwill be displayed in \nmultiple lines";</td></tr>
</table>


