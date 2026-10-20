---
layout: post
title: Label Customization in WPF Bullet Graph | Syncfusion®
description: Learn Label Customization in WPF Bullet Graph using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Label Customization in WPF Bullet Graph

A quantitative scale label specifies the numeric value according to the major ticks in the range of the scale.

## Customizing Labels

The labels can be positioned far away from the quantitative scale by using the [`LabelOffset`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_LabelOffset) property, and the default value is 0. The foreground of the label is customized by setting the [`LabelStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_LabelStroke) property. By setting the [`LabelSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_LabelSize) property, the font size of the labels is modified. The label content can be formatted by using the [`LabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_LabelFormat) property.

{% tabs %}
{% highlight xaml %}

     <syncfusion:SfBulletGraph  LabelSize="20" Minimum="0" Maximum="10"
                              LabelOffset="5"  Interval="2"
                              LabelStroke="Red"
                              LabelFormat="C" >
        </syncfusion:SfBulletGraph>


{% endhighlight %}

{% highlight c# %}

      SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.LabelOffset = 5;
            bulletgraph.LabelSize = 20;
            bulletgraph.LabelFormat = "C";
            bulletgraph.Minimum = 0;
            bulletgraph.Maximum = 10;
            bulletgraph.Interval = 2;
            bulletgraph.LabelStroke = new SolidColorBrush(Colors.Red);
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Labels_img1](Labels_images/Labels_img1.png)

## Label Position

The labels in the scale can be placed above or below the qualitative ranges using the [`LabelPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_LabelPosition) property, which supports the following options:

1. Below (Default)
2. Above

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

     <syncfusion:SfBulletGraph LabelPosition="Above" TickPosition="Cross">
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    bulletgraph.LabelPosition = BulletGraphLabelsPosition.Above;
    this.Grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![Labels_img2](Labels_images/Labels_img2.png)
