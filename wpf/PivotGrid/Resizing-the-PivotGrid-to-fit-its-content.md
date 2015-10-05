---
layout: post
title: Resizing the PivotGrid to fit its content| PivotGrid | Wpf | Syncfusion
description: Resizing the PivotGrid to fit its content
platform: wpf
control: PivotGrid
documentation: ug
---

# Resizing the PivotGrid to fit its content

PivotGrid provides support for resizing the grid to fit its content while group expanding and collapsing the groups. The grid will be resized after refreshing the page. 

### Use Case Scenarios

This feature will be useful to provide more space to display the controls sharing its parent control during group collapse operation. 

### Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
ResizePivotGridToFit </td><td>
Resizes the PivotGrid according to the content of the grid. </td><td>
Dependency</td><td>
Boolean </td><td>
NA </td></tr>
</table>


### Enabling Resizing Pivot Grid

You can enable or disable this feature using the _ResizePivotGridToFit_ property.  To enable resizing, set this property to true. To disable resizing, set this property to false.  By default this is set to false.

The following code illustrates how to enable resizing to fit the content, when you expand or collapse the PivotGrid group:

{% tabs %}
{% highlight C# %}  





this.pivotGrid1.ResizePivotGridToFit = true; 

{% endhighlight %} 

{% highlight vbnet %} 





Me.pivotGrid1.ResizePivotGridToFit = True 

{% endhighlight %} 
{% endtabs %}

![](Features_images/Features_img32.png)



The following code illustrates how to disable resizing to fit the content, when you expand or collapse the PivotGrid group:

{% tabs %}
{% highlight C# %}  




this.pivotGrid1.ResizePivotGridToFit = false;

{% endhighlight %} 

{% highlight vbnet %} 





Me.pivotGrid1.ResizePivotGridToFit = False

{% endhighlight %} 
{% endtabs %}

![](Features_images/Features_img33.png)



### Sample Link

To view samples: 

1.Open Syncfusion Dashboard.

2.Select BI > WPF.

3.Click Run Samples.

4.Navigate to PivotGrid > Product Showcase > Pivot Grid Demo.


