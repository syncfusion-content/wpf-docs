---
layout: post
title: How to Set Defer Layout Update in WPF Pivot Grid | Syncfusion®
description: Set defer layout update in Syncfusion® WPF Pivot Grid control by enabling the DeferLayoutUpdate property.
platform: wpf
control: Pivot Grid
documentation: ug
---

# How to Set Defer Layout Update in WPF Pivot Grid

It can be achieved by setting the property `DeferLayoutUpdate` to true via code or through the DeferLayoutUpdate check-box (UI option) inside PivotSchemaDesigner control. 

If through *XAML*, please refer the below code sample.

{% highlight xaml %}

        <syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" 
                 DeferLayoutUpdate="True" ItemSource="{Binding   Source={StaticResource data}}" >
        </syncfusion:PivotGridControl>
     
{% endhighlight %}

Else if through *Code-behind*, please refer the below code sample.

{% highlight C# %}

        public MainWindow()
        {
            InitializeComponent();
            pivotGrid.DeferLayoutUpdate = true;
        } 
		
{% endhighlight %}

