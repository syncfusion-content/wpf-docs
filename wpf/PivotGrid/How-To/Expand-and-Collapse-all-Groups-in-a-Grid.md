---
layout: post
title: 141-Expand-and-Collapse-all-Groups-in-a-Grid
description:         1.4.1 expand and collapse all groups in a grid?
platform: wpf
control: PivotGridControl
documentation: ug
---

# Expand and Collapse all Groups in a Grid?

## Expand all the groups in a PivotGrid

After defining PivotGrid control, invoke the method **ExpandAllGroup()** to expand all the groups in the PivotGrid control.

Please refer the below code snippet.
 
{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();
            // To Expand all groups in a grid
            pivotGrid.ExpandAllGroup();
        }
{% endhighlight %}

## Collapse all the groups in a PivotGrid

After defining PivotGrid control, invoke the method **CollapseAllGroup()** to collapse all the groups in the PivotGrid control.

Please refer the below code snippet.

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();   
            // Collapse all group in Grid
            pivotGrid.CollapseAllGroup();
        }

{% endhighlight %}
