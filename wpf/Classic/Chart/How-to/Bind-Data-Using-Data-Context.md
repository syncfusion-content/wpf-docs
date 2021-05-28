---
layout: post
title: Bind Data Using Data Context | wpf | Syncfusion
description: Learn here all about Bind Data Using Data Context support in Syncfusion WPF Chart (Classic) control, its elements and more details.
platform: wpf
control: Chart (Classic)
 documentation: ug
---

## Bind Data Using Data Context

When using multiple series' in the Chart, it might be convenient to set the Data Contexts at the Chart or Chart Area levels and refer to that context from the Chart Series.
{% highlight xaml %}

<sfchart:Chart Name="chart1" DataContext="{Binding Source={StaticResource myXmlData}, XPath=Products/Product}" >

    <sfchart:ChartArea View3DMode="True" >

        <sfchart:ChartSeries Label="Sales" DataSource="{Binding}" BindingPathX="Month" BindingPathsY="Sales" Type="Column">

        </sfchart:ChartSeries>

        <sfchart:ChartSeries Label="Projected Sales" DataSource="{Binding}" BindingPathX="Month" BindingPathsY="Projected" Type="Column">

        </sfchart:ChartSeries>

    </sfchart:ChartArea>

</sfchart:Chart>
{% endhighlight  %}
