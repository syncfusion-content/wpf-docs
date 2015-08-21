---
layout: post
title: Asynchronous Data Loading
description: Asynchronous Data Loading
platform: wpf
control: PivotGrid
documentation: ug
---

## Asynchronous Data Loading

The PivotGrid control provides support for loading data in a unique UI thread. That is, the PivotGrid control can perform long running operations asynchronously on a background thread so that users can access other UI controls while the grid is loading. It also loads asynchronously for every layout change operation, such as filtering, sorting, drag and drop, manipulating the field list, or changing the Pivot Schema Designer. This can be achieved by setting the LoadInBackground property to true.

Property Table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
LoadInBackground</td><td>
This property enables the PivotGrid control to perform loading operations asynchronously on a background thread.</td></tr>
</table>


#### To enable asynchronous loading

{% highlight C# %}   


         // Loading asynchronously on a background thread.



          this.pivotGrid1.InternalGrid.LoadInBackground = true;

{% endhighlight %}

{% highlight vbnet %} 


         ’ Loading asynchronously on a background thread.



          Me.pivotGrid1.InternalGrid.LoadInBackground = True 

{% endhighlight %} 

![](Features_images/Features_img52.png)



PivotGrid Control Loading Asynchronously

![](Features_images/Features_img53.png)



PivotGrid after Loading

#### Sample Link

To access the UI threading demo:

1.Open the Syncfusion Dashboard.

2.Click Business Intelligence.

3.Click the WPF drop-down list, and select Explore Samples.
 
4.Navigate to PivotAnalysis.WPF > Samples >Product Showcase >UIThreading Demo.



