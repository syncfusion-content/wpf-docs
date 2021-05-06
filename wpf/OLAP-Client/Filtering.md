---
layout: post
title: Filtering in WPF Olap Client control | Syncfusion
description: Learn about Filtering support in Syncfusion WPF Olap Client control and more.
platform: wpf
control: OLAP Client
documentation: ug
---

# Filtering in WPF Olap Client

## Filtering by member

After clicking the split button of a dimension, the member editor dialog opens through which members are filtered by checking and unchecking the check boxes corresponding to members. By clicking OK, the OLAP report gets updated and refreshes the OLAP grid and OLAP chart controls based on the selected members in the member editor dialog. The Cancel button is used for canceling the selection.

![Member editor dialog to filter the elements](Filtering_images/Filtering_img1.png)

The above filter illustrates that the members "France" and "Germany" along with "New South Wales" and "Queensland" are filtered from the grid and chart views.

## Filtering by value

The filter tab in the filtering and sorting dialog box provides the options to specify custom filters on the multidimensional data. It enables users to filter the rows and columns of the selected measure.

* **Column filter**: Column filter checks each and every row of a column against the filter condition. The column will be included in the result set only if all the rows of that column satisfy the condition; otherwise, the column will be filtered.

* **Row filter**: Row filter checks each and every column of a row against the filter condition. The row will be included in the result set only if all the columns of that row satisfy the condition; otherwise, the row will be filtered.

Filtering and Sorting dialog for rows/columns can be opened by clicking the corresponding icon in the toolbar.

![Column filter option is selected in OlapClient toolbar](Filtering_images/Filtering_img2.png)

Filtering by row
{:.caption}

![Row filter option is selected in OlapClient toolbar](Filtering_images/Filtering_img3.png)

Filtering by column
{:.caption}

The following screenshot displays the filter tab in Filtering and Sorting dialog.

![Filter tab is selected in filtering and sorting dialog](Filtering_images/Filtering_img4.png)

The options in the filtering tab are as follows:

**Filter empty rows/columns**: Filters the empty rows or columns appeared in the result set.

**Filter 1 and Filter 2**: You can apply two filter expressions to a report at the same time. The options in the filter group box are as follows:

* **Condition**: You can choose any one condition required to appear in the filter expression.
* **Filter on**: You can choose any one measure element from the list, on which you want to apply the filter.
* **Value**: Enter the conditional value for the expression.

You can toggle the visibility of the filter and sort buttons in the OLAP client toolbar by using the `ShowFilterSortButtons` property.

{% tabs %}

{% highlight c# %}  

this.olapClient1.ShowFilterSortButtons = false;

{% endhighlight %} 

{% highlight vbnet %} 

Me.olapClient1.ShowFilterSortButtons = False

{% endhighlight %}
 
{% endtabs %}

## Subset filter

Subset filter is used to filter the number of records in the result set. The subset filter gets a numeric number as input and restricts the number of records within that count. You can specify the subset filter for both the row and column.

![Subset filter](Filtering_images/Filtering_img6.png)

![To filter the number of records in Columns](Filtering_images/Filtering_img5.png)

Users can toggle the visibility of subset filter by using the `ShowSubsetFilters` property.

{% tabs %}

{% highlight c# %}  

    this.olapClient1.ShowSubsetFilters = false;

{% endhighlight %} 

{% highlight vbnet %} 

    Me.olapClient1.ShowSubsetFilters = False

{% endhighlight %}

{% endtabs %}
