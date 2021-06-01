---
layout: post
title: 141-Expand-and-Collapse-all-Groups-in-a-Grid | Syncfusion
description: Section that helps to know how to expand or collapse the entire groups programmatically in pivot grid control.
platform: wpf
control: PivotGridControl
 documentation: ug
---

# How to expand and collapse entire group in PivotGrid?

## Expanding entire group in PivotGrid

After defining PivotGrid control, invoke the method `ExpandAllGroup()` to expand entire group in the PivotGrid control.

Please refer the below code sample.
 
{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();
            //To expand entire group in PivotGrid
            pivotGrid.ExpandAllGroup();
        }
{% endhighlight %}

## Collapsing entire group in PivotGrid

After defining PivotGrid control, invoke the method `CollapseAllGroup()` to collapse entire group in the PivotGrid control.

Please refer the below code sample.

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();   
            //To collapse entire group in PivotGrid
            pivotGrid.CollapseAllGroup();
        }

{% endhighlight %}
