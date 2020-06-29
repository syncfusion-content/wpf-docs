---
layout: post
title: WPF TreeView Sorting | Syncfusion
description: This section describes about how to sort treeview items in WPF treeview and also explains about performing custom sorting in Wpf Treeview(TreeViewAdv).
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Sorting in Wpf TreeView(TreeViewAdv).

TreeViewAdv has the advanced ability to sort the TreeViewItemAdv items at run time. The `Sorting` property of the control allows you to specify the direction of sorting. The sorting options are as follows.

* Ascending
* Descending
* None (__default__)

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" Sorting="Ascending"  >
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Name="treeViewItemAdv"    Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information">
<syncfusion:TreeViewItemAdv Header="Canada"/>
<syncfusion:TreeViewItemAdv Header="France"/>
<syncfusion:TreeViewItemAdv Header="Germany"/>
<syncfusion:TreeViewItemAdv Header="UK"/>
<syncfusion:TreeViewItemAdv Header="USA"/>
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}
//Sort the item
treeViewAdv.Sorting = SortDirection.Ascending;

{% endhighlight %}

{% highlight VB %}

'Sort the item
treeViewAdv.Sorting = SortDirection.Ascending

{% endhighlight %}

{% endtabs %}

## Sorting field

Using `SortingField` property, you can specify a sorting criteria. This is dependency property, which gets or sets the property name being used as the sorting criteria. The default value is __Header__.

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv Name="treeViewAdv" Sorting="Ascending" SortingField="Header"  >
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Name="treeViewItemAdv"    Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information">
<syncfusion:TreeViewItemAdv Header="Canada"/>
<syncfusion:TreeViewItemAdv Header="France"/>
<syncfusion:TreeViewItemAdv Header="Germany"/>
<syncfusion:TreeViewItemAdv Header="UK"/>
<syncfusion:TreeViewItemAdv Header="USA"/>
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//Sort the item based on criteria
treeViewAdv.SortingField = "Header";

{% endhighlight %}

{% highlight VB %}

'Sort the item based on criteria
treeViewAdv.SortingField = "Header"

{% endhighlight %}

{% endtabs %}

![Show the sorted WPF TreeView items](Sorting_treeviewitemadv_images/Sorting_treeviewitemadv_img1.jpeg)


