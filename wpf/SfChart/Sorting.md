---
layout: post
title: Sorting | SfChart | Wpf | Syncfusion
description: sorting 
platform: wpf
control: SfChart
documentation: ug
---

#Sorting

Chart provides the support for sorting the data point rendering either in ascending or descending based on X or Y axis.

**Properties**

<table>
<tr>
<td>
Name<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
IsSortData<br/><br/></td><td>
Gets or sets the Boolean value indicates whether to sort the data or not.<br/><br/></td></tr>
<tr>
<td>
SortBy<br/><br/></td><td>
Gets or sets the axis for which sorting to be performed.<br/><br/></td></tr>
<tr>
<td>
SortDirection<br/><br/></td><td>
Gets or sets the sorting direction, either '_Ascending__ 'or '__Descending_'<br/><br/></td></tr>
</table>
The following example illustrates a simple chart (without apply sorting):

![](sorting_chart_images/sorting_1.png)


Note: This feature is primarily applicable for indexed (non-linear) axis like CategoryAxis.

For linear axis like NumericalAxis, only the order of rendering will be sorted. i.e., the order in which the data point is being rendered.

SortDirection

This defines the direction of sorting either in Ascending or Descending based on x or y value. This can be explained by combined with SortBy property below.

SortBy

Sorting can be done with respect to X and Y axis. This is an enum property.

**Sorting** **x** **axis** **in** **ascending** **order**:

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  SortDirection="Ascending"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/sorting_2.png)


**Sorting** **x** **axis** **in** **descending** **order**:

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  SortDirection="Descending"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/sorting_3.png)


**Sorting** **y** **axis** **in** **ascending** **order**:

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y"  SortDirection="Ascending"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"  YBindingPath="Year2011"/>





{% endhighlight %}

![](sorting_chart_images/sorting_4.png)


**Sorting** **y** **axis** **in** **descending** **order**:

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y"  SortDirection="Descending"

ItemsSource="{Binding Demands}" Interior="#4A4A4A"

XBindingPath="Demand"  YBindingPath="Year2011"/>





{% endhighlight %}

![](sorting_chart_images/sorting_5.png)


**Sorting** **for** **linear** **axis**

As mentioned above, the sorting for the linear axis is different from CategoryAxis. Here the rendering order of the data point (x or y) will be sorted.

This will be useful especially when we have one or more values added in same data point. Also this rendering order sorting will be captured by applying Palette to each point.

The following example illustrates a simple chart having AutumnBrights palette (without apply sorting):

![](sorting_chart_images/linearaxis_nosort.png)

**Sorting** **x** **axis** **(**NumericalAxis**)** **in** **ascending** **order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X" Palette="AutumnBrights"

SortDirection="Ascending"

ItemsSource="{Binding Demands}" 

XBindingPath="Position"  YBindingPath="Year2011"/>



{% endhighlight %}

![](sorting_chart_images/linearaxis_sort1.png)

**Sorting** **x** **axis** **(**NumericalAxis**)** **in** **descending** **order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X" Palette="AutumnBrights"

SortDirection="Descending"

ItemsSource="{Binding Demands}" 

XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/linearaxis_sort2.png)

**Sorting** **y** **axis** **(**NumericalAxis**)** **in** **ascending** **order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" Palette="AutumnBrights"

SortDirection="Ascending"

ItemsSource="{Binding Demands}" 

XBindingPath="Position"  YBindingPath="Year2011"/>



{% endhighlight %}

![](sorting_chart_images/linearaxis_sort3.png)

**Sorting** **y** **axis** **(**NumericalAxis**)** **in** **descending** **order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" Palette="AutumnBrights"

SortDirection="Descending"

ItemsSource="{Binding Demands}" 

XBindingPath="Position"  YBindingPath="Year2011"/>



{% endhighlight %}

![](sorting_chart_images/linearaxis_sort4.png)


