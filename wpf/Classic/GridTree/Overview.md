---
layout: post
title: About WPF GridTree Control | Syncfusion
description: Learn here all about introduction of Syncfusion WPF GridTreeControl (Classic) control, its elements and more details.
platform: wpf
control: GridTree 
documentation: ug
---

# Overview in WPF GridTreeControl (Classic)

The grid at its core functions as a very efficient display engine for tabular data that can be customized down to the cell level. It does not make any assumptions on the structure of the data (many grid controls implemented as straight data-bound controls make such explicit assumptions). This leads to a very flexible design that can be easily adapted to a variety of tasks including the display of completely unstructured data and the display of structured data from a database. 

The display system also hosts a powerful and complete styles architecture. Settings can be specified at the cell level or higher levels using parent styles that are referred to as base styles. Base styles can affect groups of cells. Cell level settings override any higher-level settings and enable easy customization right down to the cell level.

With this version, our core focus has been on the underlying architecture for displaying cells with virtualized cell editors in a manner that enables good performance characteristics. The core display system also supports several building-block features such as nested grids, virtual modes, and support for a virtually unlimited number of rows and columns.

### Use Case Scenarios

EssentialGrid for WPF can be applied to a variety of industries such as finance, banking, software, etc. Some of its important features are:

Excel-Like UI: Essential Grid’s rich feature set allows you to build Excel-like UI applications. 



![Overview of GridTree UI like a excel](Overview_images/Overview_img1.png)



High Performance - EssentialGrid is a great asset to high-performance applications, as it can display large amounts of real-time data that tends to periodic changes without any performance hits. Below is an illustration of a stock portfolio application using the GridData control.



![Overview of GridTree](Overview_images/Overview_img2.png)



File Explorer - Applications that deal with hierarchical data can make use of Essential Grid’s file explorer feature, which allows child items to be displayed on-demand by using the GridTree control.

![Overview of GridTree](Overview_images/Overview_img3.png)



## Key Features

You will find the following features of EssentialGrid for WPF:

* Easy APIs to add, delete, or move rows and columns – You can easily add, delete, or move rows and columns throughout the Grid control using its well-defined APIs.
* Clipboard Support – Essential Grid provides excellent clipboard support that allows users to copy and paste grid cell content to text or any format.
* Frozen Rows and Columns – Essential Grid allows users to freeze grid columns to the left or right or freeze rows to the top or bottom of the grid.
* Resize Rows and Columns – Essential Grid provides options for resizing rows and columns. 
* Hide Rows and Columns – Essential Grid provides support for hiding or displaying a range of rows and columns.
* Keyboard Interface – Essential Grid provides extensive support for keyboard handling. The following list contains some supported keys and actions:
* Arrow keys – To move cell focus.
* PageUp/PageDown – To scroll a grid by page.
* F2  – To activate/deactivate a current cell.
* F4+ALT – To open/close the pop-up of a drop-down cell.
* CTRL + Arrow – To move to the first or last row or column.
* SHIFT + Arrow keys – To select cells.
* DELETE – To delete an entire row in the GridData control.
* CTRL+X, CTRL+V, CTRL+C – For common clipboard operations.
* All keyboard operations can be customized. 
* Selection Modes - Essential Grid offers different kinds of selection modes such as row only, column only, and cell only for selecting a particular row, column, or cell, respectively.
* Drag-Drop Support - Essential Grid lets you drag any column and drop it at any position in the grid. This allows columns to be repositioned as required.
* Virtual Mode - Essential Grid for WPF supports a virtual mode, which lets you dynamically provide data to the grid from an external data source through an event. This means the grid does not store any data in its internal data structure.

## User Guide Organization

EssentialGrid for WPF comes with numerous samples as well as extensive documentation for your reference. This user guide provides detailed information on features and functionalities. It is organized into the following sections:

* Overview – This section provides a brief introduction to Essential Grid and its key features.
* Getting Started – This section guides you on getting started with a WPF application and WPF controls.
* Concepts and Features –Under this section, the features of individual controls are illustrated with use-case scenarios, code examples, and screen shots.
* Frequently Asked Questions – This section contains answers to frequently asked questions about Essential Grid.

## Document Conventions 

The conventions below will help you quickly identify important sections of information when using this user guide:

Document Conventions
{:.caption}

<table>
<tr>
<th>
Convention</th><th>
Description of the Icon</th></tr>
<tr>
<td>
Note</td><td>
Represents important information to be noted.</td></tr>
<tr>
<td>
Example</td><td>
Represents an example.</td></tr>
<tr>
<td>
Tip</td><td>
Represents useful hints that will help you use the controls and features.</td></tr>
<tr>
<td>
Additional information</td><td>
Represents additional information on the corresponding topic.</td></tr>
</table>

## Feature Summary

This section provides basic information, such as definitions and usage, regarding important features of EssentialGrid.

## Overview in WPF GridTreeControl (Classic)Control 

The GridTree control is a dynamic data-bound control used to present hierarchical data.

### Data Binding

The GridTree control supports all popular data sources including observable collections, data tables, and binding lists.

Data sources can be bound to the GridTree control by either directly binding ItemsSource with the relational information or by retrieving node elements dynamically with the RequestTreeItems event. RequestTreeItems will load the data in an on-demand basis.

For instance, a database may have 100,000 records in it; in the first approach (binding ItemSource) you have to set ItemsSource of GridTreeControl, and it will take care of populating root and child nodes. But in the second approach, you have to dynamically pass the source of the root and child by handling the RequestTreeItems event. The child element will load only when the parent node expands. 

Data Presentation: Cell Types

Several built-in cell types can be used to display and edit any underlying data type. The following cell types are available:

* Static-text cells.
* Check-box cells. 
* Button cells.
* Image cells.
* Combo-box cells. 
* Drop-down list cells. 
* Currency cells.
* Date-time cells.
* Double edit cells.
* Integer edit cells.
* Mask edit cells.
* Percent edit cells.
* Rich-text-box cells.
* Up-down edit cells.



![Overview of GridTree](Overview_images/Overview_img4.png)



## Interactive Features

The GridTree control provides an effective option for sorting. Also, its appearance can easily be customized through an API that can be used to set different types of glyphs such as triangles, plus and minus signs, and tree lines in various brush styles. By handling the GlyphDrawing event on the cell renderer, you can draw custom expand-and-collapse glyphs. The GridTree control also supports placing images next to expand-and-collapse glyphs.



![Overview of GridTree](Overview_images/Overview_img5.png)



## Serialization

The GridTree control supports XML serialization to preserve and restore a grid’s schema and style settings. All styles and properties that reflect the state of the Grid can be serialized.

