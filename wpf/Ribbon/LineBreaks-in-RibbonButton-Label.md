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


{% highlight xml %}


[XAML] 
<!--RibbonButton with IsMultiLine set to true-->        
<syncfusion:RibbonButton Name="ribbonButton"  IsMultiLine="True" Label="Ribbon Button Label \nwill be displayed in \nmultiple lines"/>
{% endhighlight %}

{% highlight C# %}

[C#]
//RibbonButton with IsMultiline set to true
ribbonButton.IsMultiLine = true;
ribbonButton.Label = "Ribbon Button Label \nwill be displayed in \nmultiple lines";

{% endhighlight %}

