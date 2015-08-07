---
layout: post
title: Freeze-Headers
description: freeze headers
platform: wpf
control: OLAP Grid
documentation: ug
---

# Freeze Headers

OlapGrid for WPF provides built-in support to freeze the Column and Row Headers. This is achieved by setting the FreezeHeaders property of OlapGrid to true. This feature also enables scrolling through the value cells.

  {% highlight c# %}

    [C#]



// To Freeze Grid Headers

this.OlapGrid1.FreezeHeaders = true;

    {% endhighlight %}





  {% highlight vbnet %}

    [VB]



' To Freeze Grid Headers

Me.OlapGrid1.FreezeHeaders = True

    {% endhighlight %}







![](Freeze-Headers_images/Freeze-Headers_img1.png)


## Sample Location

A sample demo is available at the following location:

..\Syncfusion\EssentialStudio\<Versionnumber>\BI\WPF\OlapGrid.WPF\Samples\Appearance\Frozen Header Demo

