---
layout: post
title: User-Configurable Context Menu Support
description: User-Configurable Context Menu Support
platform: wpf
control: PivotGrid
documentation: ug
---

## User-Configurable Context Menu Support

### Description

This feature provides support to reorder the Context Menu Items displayed on right-clicking the Header cells of the Pivot Row and Column of the PivotGrid control. It enhances user-accessibility to frequently used Context Menu Items by providing a User-Configurable Context Menu. You can reorder Context Menu Items according to your preference and ease.

The default Context Menu lists the following Items:

1.Allow Filtering – Enable or disable filtering in the selected pivot computation column.

2.Allow Sorting – Enable or disable sorting in the selected pivot computation column.

3.HideValueColumn – Hides the selected pivot computation column.

4.ClearValueFilters – Disables filtering in all pivot computation columns.

5.ClearValueSorts – Disables sorting in all pivot computation columns.

6.ShowPivotValueChooser – Launches the Pivot Value Chooser window.



![](Features_images/Features_img50.png)



_PivotGrid with User-Configurable Context Menu_

### Enabling the User-Configurable Context Menu

This User-Configurable Context Menu is available only in the RowPivotsOnly mode. The following code is used to enable the user-configurable context menu:

{% highlight C# %} 





this.pivotGridControl1.RowPivotsOnly = true;

this.pivotGridControl1.ColumnHeaderCellStyle.EnableContextMenu = true;

 {% endhighlight %} 
 
### Customizing the User-Configurable Context Menu

This following code illustrates how to reorder the Context Menu Items of the User-Configurable Context Menu in the PivotGrid control

{% highlight C# %}  





void pivotGridControl1_Loaded(object sender, RoutedEventArgs e)

{

this.pivotGridControl1.InternalGrid.ContextMenuOpening += new    

ContextMenuEventHandler(InternalGrid_ContextMenuOpening);

}



void InternalGrid_ContextMenuOpening(object sender, ContextMenuEventArgs e)

{

PivotSortHeaderCell pivotGridSortHeaderCell = e.Source as PivotSortHeaderCell;

if (pivotGridSortHeaderCell != null)

{

ContextMenu contextMenu = pivotGridSortHeaderCell.GetContextMenu();

if (contextMenu != null)

{

ItemCollection itemCollection = contextMenu.Items;

List<object> newItemCollection = new List<object>(itemCollection.Count);

foreach (var item in itemCollection)

{

if (item is MenuItem)

{

MenuItem tempItem = (item as MenuItem);

switch (tempItem.Tag.ToString())

{

case "Allow Sorting":

newItemCollection.Add(tempItem);

break;

case "Allow Filtering":

newItemCollection.Add(tempItem);

break;

case "Hide Column":

newItemCollection.Add(tempItem);

newItemCollection.Add(new Separator());

break;

case "Clear Filters":

newItemCollection.Add(tempItem);

break;

case "Clear Sorts":

newItemCollection.Add(tempItem);

break;

case "Show Pivot Value Chooser":

newItemCollection.Insert(0, tempItem);

newItemCollection.Insert(1, new Separator());

break;

}

}

}

contextMenu.Items.Clear();

foreach (var item in newItemCollection)

{

contextMenu.Items.Add(item);

}

}

}

}

{% endhighlight %} 

#### Sample Link

{InstalledDrive}:\Users\{User_Name}\AppData\Local\Syncfusion\EssentialStudio\{VersionNumber{x.x.x.x}\WPF\PivotAnalysis.WPF\Samples\Product Showcase\RowPivotsOnly Demo



