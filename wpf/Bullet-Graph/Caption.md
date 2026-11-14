---
layout: post
title: Caption in WPF Bullet Graph | Syncfusion®
description: Caption in the WPF Bullet Graph displays descriptive text for the graph, helping users understand displayed metrics and data context.
platform: wpf
control: SfBulletGraph
documentation: ug
---

# Caption in WPF Bullet Graph

The [`Caption`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_Caption) property of the bullet graph is used to specify a unique label describing the value represented in the bullet graph. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph>
            <syncfusion:SfBulletGraph.Caption>
                <StackPanel Margin="0,0,10,0">
                    <TextBlock Text="Revenue YTD" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                    <TextBlock Text="$ in Thousands" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                </StackPanel>
            </syncfusion:SfBulletGraph.Caption>
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    TextBlock textBlock = new TextBlock() { Text = "Revenue YTD" };
    TextBlock textBlock1 = new TextBlock() { Text = "$ in Thousands" };
    StackPanel stackPanel = new StackPanel();
    stackPanel.Children.Add(textBlock);
    stackPanel.Children.Add(textBlock1);
    bulletgraph.Caption = stackPanel;
    grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![Caption_img1](Caption_images/Caption.png)

## Caption Position

The caption in the bullet graph can be placed at the start or end of the quantitative scale using the [`CaptionPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_CaptionPosition) property, which supports the following options:

1. Near (Default)
2. Far

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph CaptionPosition="Far">
            <syncfusion:SfBulletGraph.Caption>
                <StackPanel Margin="0,0,10,0">
                    <TextBlock Text="Revenue YTD" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                    <TextBlock Text="$ in Thousands" Foreground="Black"
                               FontSize="13" HorizontalAlignment="Center"/>
                </StackPanel>
            </syncfusion:SfBulletGraph.Caption>
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

   SfBulletGraph bulletgraph = new SfBulletGraph();
            bulletgraph.CaptionPosition = BulletGraphCaptionPosition.Far;
            TextBlock textBlock = new TextBlock() { Text = "Revenue YTD" };
            TextBlock textBlock1 = new TextBlock() { Text = "$ in Thousands" };
            StackPanel stackPanel = new StackPanel();
            stackPanel.Children.Add(textBlock);
            stackPanel.Children.Add(textBlock1);
            bulletgraph.Caption = stackPanel;
            grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

![Caption_img2](Caption_images/CaptionPosition.png)
