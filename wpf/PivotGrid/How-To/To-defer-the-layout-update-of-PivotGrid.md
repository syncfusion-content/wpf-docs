---
layout: post
title: 145-Display-the-Calculation-Columns-in-Row
description:         1.4.5 display the calculation columns in row?
platform: wpf
control: PivotGridControl
documentation: ug
---

# To defer the layout update of PivotGrid?

It can be achieved by setting the property **DeferLayoutUpdate** to true or through the DeferLayoutUpdate checkbox of PivotGrid control. It can be mentioned either in *XAML* and *Code-Behind*. 

If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" 
                 DeferLayoutUpdate="True" ItemSource="{Binding   Source={StaticResource data}}" >
        </syncfusion:PivotGridControl>
     
{% endhighlight %}

Else of through **Code-behind**, please refer the below code snippet.

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();
            pivotGrid.DeferLayoutUpdate = true;
        } 
		
{% endhighlight %}

