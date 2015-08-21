---
layout: post
title: LineBreak-Support
description: linebreak support
platform: wpf
control: Ribbon
documentation: ug
---

# LineBreak Support

LineBreak Support in RibbonButton, SplitButton, DropDownButton Label using Hyphen(-) Character

A Hyphen can now be used as delimiter for displaying the RibbonButton, SplitButton and DropDownButton labels in multiple lines. 

Following code sample illustrates how to use Hyphen (-) to display the labels in multiple lines.



<table>
<tr>
<td>
{% highlight xml %}<syncfusion:RibbonButton Name="ribbonButton" Label="Ribbon-Button" ></syncfusion:RibbonButton><syncfusion:SplitButton Name="splitButton" Label="Split-Button" ></syncfusion:SplitButton><syncfusion:DropDownButton  Name="dropdownButton" Label="DropDown-Button" ></syncfusion:DropDownButton>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %}ribbonButton.Label = "Ribbon-Button";splitButton.Label = "Split-Button";dropdownButton.Label = "DropDown-Button";{% endhighlight %}</td></tr>
</table>

![](LineBreak-Support_images/LineBreak-Support_img1.jpeg)



