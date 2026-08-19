---
layout: post
title: Expand and Collapse Entire Groups in WPF Pivot Grid | Syncfusion®
description: Expand or collapse all groups programmatically in Syncfusion® WPF Pivot Grid control using ExpandAllGroup and CollapseAllGroup methods.
platform: wpf
control: Pivot Grid
documentation: ug
---

# How to Expand and Collapse Entire Groups in WPF Pivot Grid
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
