---
layout: post
title: Sorting in WPF Olap Client control | Syncfusion
description: Learn about Sorting support in Syncfusion Essential Studio WPF Olap Client control, its elements and more details.
platform: wpf
control: OLAP Client
 documentation: ug
---

# Sorting in WPF Olap Client

The sorting tab in the Filtering and Sorting dialog box provides an option to sort the results by rows or columns in ascending or descending order.

* **Column sorting**: Sorts the columns in the result set based on the column total of each column.
* **Row sorting**: Sorts the rows in the result set based on the row total of each row.

Filtering and Sorting dialog box for rows or columns can be opened by clicking the corresponding icon in the toolbar.

![Row sorting option is selected in OlapClient toolbar](Sorting_images/Sorting_img1.png)

Sorting by row
{:.caption}

![Column sorting option is selected in OlapClient toolbar](Sorting_images/Sorting_img2.png)

Sorting by column
{:.caption}

The following screenshot displays the sorting tab in the Filtering and Sorting dialog box.

![Sorting tab is selected in filtering and sorting dialog](Sorting_images/Sorting_img3.png)

The options in the sorting tab are as follows:

* **Sorting on**: Displays the list of measure elements to choose one to set as the key field.
* **Ascending or descending**: Specifies the sorting order.
* **Preserve hierarchy**: Sorts the records without changing the hierarchy order.

To toggle the visibility of the filter and sort buttons in the OLAP client toolbar, use the `ShowFilterSortButtons` property.

{% tabs %} 

{% highlight c# %}  

this.olapClient1.ShowFilterSortButtons = false;

{% endhighlight %} 

{% highlight vbnet %} 

Me.olapClient1.ShowFilterSortButtons = False

{% endhighlight %}
 
{% endtabs %}
