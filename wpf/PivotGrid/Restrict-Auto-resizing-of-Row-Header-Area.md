---
layout: post
title: Restrict Auto-resizing of Row Header Area
description: Restrict Auto-resizing of Row Header Area
platform: wpf
control: PivotGrid
documentation: ug
---


## Restrict Auto-resizing of Row Header Area


The PivotGrid control provides support for restricting the row header items from being stretched when there are too many items in the computation area. When the Computation button (Show List button) located in the DataHeaderArea of the grouping bar is clicked, the Computation List window appears with the computation fields. 

#### Use Case Scenarios

This feature will restrict the row header items from being stretched and maintains its size with the fixed one so that users can view most of the data in the viewable area instead of scrolling to view the data.

Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td></tr>
<tr>
<td>
AllowRowHeaderAreaAutoSizing</td><td>
Shows the ComputationButton (Show Field List Button) whose click event opens the Computation List Window with the calculation fields of the PivotGrid and restricts the stretching of row header items in the grouping bar.</td><td>
Dependency</td><td>
Boolean </td></tr>
</table>


### Enabling Resizing Pivot Grid

Users can enable or disable this feature by using the AllowRowHeaderAreaAutoSizing__property. To show the Computation button (Show Fields button) and to restrict the row header items from being stretched when more items are added to the computation area, set this property to false. To hide the Computation button (Show Fields Button) and to allow the row header items to stretch when more items are added to the computation area, set this property to true. By default the property is set to true.

The following code illustrates how to restrict the items from stretching and how to show the Computation List window through Computation button click:

{% highlight C# %} 



this.pivotGrid1.AllowRowHeaderAreaAutoSizing = false;

 {% endhighlight %} 

{% highlight vbnet %} 



Me.pivotGrid1.AllowRowHeaderAreaAutoSizing = False

{% endhighlight %} 

![C:/Users/maheswarir/Desktop/When property = true in wpf.PNG](Features_images/Features_img21.png)



The following code illustrates how to allow the items to stretch and how to hide the Computation button:

{% highlight C# %}  



this.pivotGrid1.AllowRowHeaderAreaAutoSizing = true;

{% endhighlight %} 

{% highlight vbnet %} 



Me.pivotGrid1.AllowRowHeaderAreaAutoSizing = True 

{% endhighlight %} 

![C:/Users/maheswarir/Desktop/when false.PNG](Features_images/Features_img22.png)


###  Sample Link
Follow the steps given below to view a sample of this feature. 

1. Select Start > Programs > Syncfusion > Essential Studio x.x.xx > Dashboard
2. Click Run Samples for WPF under BI edition
3. Select PivotGrid
4. Navigate to Product Showcase > PivotGrid Demo


