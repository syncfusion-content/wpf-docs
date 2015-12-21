---
layout: post
title: 146-Display-the-Count-of-Records-which-are-Current
description:Display the count of records which are currently visible in pivot engine?
platform: wpf
control: PivotGridControl
documentation: ug
---

# Display the Count of Records which are Currently Visible in Pivot Engine?

It is possible to get the count of records which are currently visible in PivotGrid by using **VisibleRecords** property.

After defining PivotGrid control, raise the Loaded event of PivotGrid. Inside the PivotGrid_Loaded() event, you can get the list of **VisibleRecords** from PivotEngine and store it as a seperate collection.

Please refer the below code snippet. 

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
            List<object> visbleRecords = pivotGrid.PivotEngine.VisibleRecords;
            int _count = visbleRecords.Count;
        }

    }

{% endhighlight %}
