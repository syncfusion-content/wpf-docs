---
layout: post
title: Load-an-existing-PivotEngine-into-a-PivotGrid
description: load an existing pivotengine into a pivotgrid?
platform: wpf
control: PivotGrid
documentation: ug
---

# Load an existing PivotEngine into a PivotGrid?

After defining the PivotGrid control, set the property **IsExternalEngine** as true. Now create a new PivotEngine using PivotEngine class and assign that to your PivotGrid control's PivotEngine.

Please refer the below code snippet.

{% highlight C# %}

    public MainWindow()
        {
            InitializeComponent();
            PivotGridControl pivotGrid = new PivotGridControl();
            this.grid1.Children.Add(pivotGrid);
            ///Set IsExternalEngine to true to use the external pivot engine.
            pivotGrid.IsExternalEngine = true;
            ///Create a new instance of the pivot engine.
            PivotEngine pivotEngine = new PivotEngine();
            
            ///Assign the new engine to pivot grid control.
            pivotGrid.PivotEngine = pivotEngine;
        }

{% endhighlight %}


