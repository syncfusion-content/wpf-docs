---
layout: post
title: GridDataControl  in WPF Wizard Control control | Syncfusion
description: Learn here all about GridDataControl  support in Syncfusion WPF GridDataControl (Classic) control and more.
platform: wpf
control: GridData (Classic)
 documentation: ug
---
# GridDataControl  in WPF GridDataControl (Classic)


The GridData control is specifically designed for the scenarios, where you need to bound the grid to an external data source and customize the data view by performing the operations such as grouping, sorting, summarizing, filtering, conditional formats and unbound fields. It attains the fundamental features by deriving from the GridControlBase class and hence adapts most of the features of Grid control, which are discussed in the previous sections. It can display nested grids with hierarchical data and can also display multiple unrelated tables in one grid.

## Major Control Classes

* GridDataControl (GDC) is the main control class of this control. It is templated with GridDataControlBaseImpl class that is based on GridControlBase class. GDC exposes numerous properties and methods that are available for the end-user to setup the grid in the desired manner.
* The GridDataTableModel serves as the model class for GDC. It stores all the data information of the grid and provides methods to completely initialize the grid.  It also provides methods to attach the grid later to the GDC, for rendering.
* The GridDataTableProperties defines property values for the Grid Table that lets you customize the appearance and behavior of the GDC.
* As a data bound grid, GDC displays tabular data where each row corresponds to a data record and every column stands for data field of the data source. You wrap all the columns in a group together and manipulate them. The GridDataVisibleColumn class is used for this purpose. It groups the columns that are visible in the screen and holds information about each column.
* The GridDataStyleInfo class, which is derived from GridStyleInfo, provides user-friendly access to all the cell level properties that control the appearance of the cell. It holds all the information  of the cell.
* GridDataTable provides the virtual representation of the entity set and manages all the underlying records in the data source.
* GridDataGroupDropAreaGridImpl is the class that defines the group drop area for a GDC. It displays a panel on the top of the GDC, where the user can drag-and-drop any column header in order to group the grid against that column. GridDataGroupDropAreaModel is the model class for this purpose.



N> There are several other classes that assist the user in creating groups, summaries, filters, sorted columns, etc.

The following sections elaborate the properties of the GridData control:

* Data Binding-Elaborates on the data binding concept in GDC
* Data Presentation-Discusses different data presentation techniques
* Events- Events that are handled in GDC are discusses here
* Look and Feel-Different appearance settings are elaborated here
* Exporting GDC to Excel-Discusses the steps to export a GDC into the Excel
* Performance-High performance of the Grid with large amount of data is discussed in this section
* Real Time Application-Illustrates how to employ the grid in portfolio applications

