---
layout: post
title: 146-Display-the-Count-of-Records-which-are-Current | Syncfusion
description: Section helps to know how to get the count of records which are currently visible in pivot grid control.
platform: wpf
control: PivotGridControl
 documentation: ug
---

# How to get the count of records which are currently visible in PivotGrid?

It is possible to get the count of records which are currently visible in PivotGrid by using `VisibleRecords` property.

After defining the PivotGrid control, raise its loaded event. Inside the `pivotGrid_Loaded` event, you can get the list of `VisibleRecords` from the PivotEngine and store it as a separate collection.

Please refer the below code sample. 

{% highlight C# %}

    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            pivotGrid.Loaded += pivotGrid_Loaded;
        }
        void pivotGrid_Loaded(object sender, RoutedEventArgs e)
        {
            List<object> VisibleRecords = pivotGrid.PivotEngine.VisibleRecords;
            int _count = VisibleRecords.Count;
        }

    }

{% endhighlight %}
