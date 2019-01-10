---
layout: post
title: Customizing columns in WPF Kanban board | Syncfusion
description: This documentation explains the options available to customize the column, including custom size, categorizing the cards, etc. in WPF Kanban board. 
platform: wpf
control: SfKanban
documentation: ug
---

# Column

## Customizing column size

By default, the columns are sized smartly to arrange the default elements of the cards with better readability. You can also define the minimum and maximum widths for the columns in [`SfKanban`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban.html) using the [`SfKanban.MinColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~MinColumnWidth.html) and [`SfKanban.MaxColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~MaxColumnWidth.html) properties, respectively.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban MinColumnWidth="300" MaxColumnWidth="340"/>

{% endhighlight %}

{% highlight C# %} 

kanban.MinColumnWidth = 300;
kanban.MaxColumnWidth = 340;

{% endhighlight %}

{% endtabs %}


You can also define the exact column width using the [`SfKanban.ColumnWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ColumnWidth.html) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnWidth="250"/>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnWidth = 250;

{% endhighlight %}

{% endtabs %}

## Categorizing columns

The cards are categorized and added into the respective columns using the value of the [`KanbanModel.Category`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanModel~Category.html) property if the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ItemsSource.html) is the collection of KanbanModel. But, if the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ItemsSource.html) is populated with custom objects, the property from the custom object used to categorize the card should be defined explicitly using the [`ColumnMappingPath`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ColumnMappingPath.html) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ColumnMappingPath="Group"/>

{% endhighlight %}

{% highlight C# %} 

kanban.ColumnMappingPath = "Group";

{% endhighlight %}

{% endtabs %}

### Populate the column with cards from different categories

More than one category can be mapped to a column by assigning multiple values to the ['Categories'](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~Categories.html) collection of [`KanbanColumn`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn.html). For example, you can map the “In Progress" and "Validated" types under the “In progress” column.

{% highlight C# %} 

progressColumn.Categories = new List<object>() { "In Progress", "Validated" };

{% endhighlight %}

![Multiple category support for a column in WPF Kanban](SfKanban_images/kanban_board_multiple_category_column.png)

## Headers

Header shows the category [`Title`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~Title.html), items count, min and max informations of a column. The UI of the header can be replaced entirely using [`SfKanban.ColumnHeaderTemplate`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.SfKanban~ColumnHeaderTemplate.html) property. The following code snippet and screenshot illustrates this.

{% highlight xaml %}

<kanban:SfKanban.ColumnHeaderTemplate>
    <DataTemplate>
      
        <StackPanel Width="300" Height="40"  Background="Silver">
            <TextBlock Margin="10" Text="{Binding  Header}" Foreground="Purple" HorizontalAlignment="Left"/>
        </StackPanel>
               
    </DataTemplate>
</kanban:SfKanban.ColumnHeaderTemplate>

{% endhighlight %}

![Customization of column header in WPF Kanban](SfKanban_images/ColumnHeaderTemplate.png)

## Column Tags

The [`Tags`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~Tags.html) property is used to customize the header of kanban column. 
The following properties of the tags can be used to customize the column header:

* [`CardCount`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColumnTag~CardCount.html) - Gets or sets the count of Cards available in that column.
* [`Maximum`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColumnTag~Maximum.html) - Gets or sets a value that indicates cards collection's maximum limit of KanbanColumn.
* [`Minimum`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColumnTag~Minimum.html) - Gets or sets a value that indicates cards collection's minimum limit of KanbanColumn. 
* [`IsExpanded`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.ColumnTag~IsExpanded.html) - Gets or sets a value indicating whether the KanbanColumn is in expanded or not.

## Expand/Collapse Column

Columns can be expanded/collapsed by tapping the toggle button which is placed at top right corner of the Kanban header. [`KanbanColumn.IsExpanded`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~IsExpanded.html) property is used to programmatically expand/collapse the Kanban column.

{% tabs %}

{% highlight xaml %}

<kanban:KanbanColumn Categories="In Progress,Validated" Title="In Progress" IsExpanded="False"></kanban:KanbanColumn>

{% endhighlight %}

{% highlight C# %} 

KanbanColumn kanbanColumn = new KanbanColumn();
kanbanColumn.IsExpanded = false;

{% endhighlight %}

{% endtabs %}

![Expand and Collapse support for a column in WPF Kanban](SfKanban_images/CollapsingColumn.png)

## Enable/Disable Drag & Drop

You can enable and disable the drag and drop operation of the cards for particular column using [`KanbanColumn.AllowDrag`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfKanban.WPF~Syncfusion.UI.Xaml.Kanban.KanbanColumn~AllowDrag.html) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:KanbanColumn  AllowDrag="false"></syncfusion:KanbanColumn>

{% endhighlight %}

{% highlight C# %} 

KanbanColumn kanbanColumn = new KanbanColumn();
kanbanColumn.AllowDrag = false;

{% endhighlight %}

{% endtabs %}