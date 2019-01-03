---
layout: post
title: Column | SfKanban | wpf | Syncfusion
description: This section describes about column and it's customization. 
platform: wpf
control: SfKanban
documentation: ug
---

# Column

## Customizing Column Size

By default, columns are sized smartly to arrange the default elements of the cards with better readability. However, you can define the minimum and maximum width for the columns in [`SfKanban`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban.html) using [`SfKanban.MinColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~MinColumnWidth.html) and [`SfKanban.MaxColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~MaxColumnWidth.html) properties respectively. 

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban MinColumnWidth ="300" MaxColumnWidth ="340">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban. MinColumnWidth = 300;
kanban. MaxColumnWidth = 340;

{% endhighlight %}

{% endtabs %}


You can also define the exact column width using [`SfKanban.ColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ColumnWidth.html) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnWidth ="250">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnWidth = 250;

{% endhighlight %}

{% endtabs %}

## Categorizing Columns

If [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ItemsSource.html) contains custom objects, the path of the property which can be used to categorize the card should be explicitly defined using [`ColumnMappingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ColumnMappingPath.html) property. By default, [`SfKanban`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban.html) will automatically categorize the items using [`KanbanModel.Category`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Category.html) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnMappingPath="Group">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnMappingPath = "Group";

{% endhighlight %}

{% endtabs %}

### Multiple category for a column

More than one category can be mapped to a column by assigning multiple values to Categories collection of [`KanbanColumn`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn.html). For e.g., you can map “In progress, Validate types under “In progress” column.

{% highlight C# %} 

progressColumn.Categories = new List<object>() { "In Progress", "Validated" };

{% endhighlight %}

![Multiple category support for a column in WPF SfKanban](SfKanban_images/MultipleCategoryMapping.png)

