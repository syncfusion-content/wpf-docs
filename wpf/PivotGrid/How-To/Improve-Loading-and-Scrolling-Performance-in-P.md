---
layout: post
title: 147-Improve-Loading-and-Scrolling-Performance-in-P | Syncfusion
description: Section helps to know how to improve the loading and scrolling performance programmatically in pivot grid control.
platform: wpf
control: PivotGridControl
documentation: ug
---

# How to improve loading and scrolling performance in PivotGrid?

The performance of the PivotGrid control can be improved by enabling the on-demand calculation on the value cells and by disabling the auto-sizing option. This refreshes the calculation only while loading or scrolling the PivotGrid control. This can be achieved by using `EnableOnDemandCalculations` and `AutoSizeOption` properties of PivotGrid control.

Please refer the below code snippet.

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();
            pivotGrid.AutoSizeOption = GridAutoSizeOption.None;
            pivotGrid.PivotEngine.EnableOnDemandCalculations = true;
        }

{% endhighlight %}
