---
layout: post
title: VS2010-Designer-support in WPF GridData Control | Syncfusion
description: Learn here all about VS2010-Designer-support in Syncfusion WPF GridDataControl (Classic) control, its elements and more.
platform: wpf
control: GridData (Classic)
 documentation: ug
---

# VS2010-Designer-support in WPF GridDataControl (Classic)

GridDataControl provides rich design time experience by associating a designer. This allows the users to modify the various grid settings to change the look and feel of the grid.

The grid designer is populated with numerous options when ItemsSource assigned to the grid. This enables the users to edit the basic grid properties and the properties of individual column. Changes in any of these properties in the designer have an immediate impact on its XAML code and hence the designer makes the grid more user-friendly.

## Activating Designer

1. Open Design window.

2. Right-click on the grid.

   N> An edit menu opens.

   ![Getting-Started_images149](Getting-Started_images/Getting-Started_img149.jpeg)

3. Select Designer View -> Show Designer. 

   N> Ensure that the grid is assigned with an ItemsSource.

4. Designer Window is displayed.

   Designer Window has two options:

   * Basic Properties - Modify the overall settings of the grid.
   * Visible Columns - Automatically generates a property list for each visible column in the grid.

   ![Getting-Started_images150](Getting-Started_images/Getting-Started_img150.jpeg)

## Basic Properties

This option enables the users to modify the overall settings of the grid. The properties are categorized into three types:

* Column Properties
* Row Properties
* Cell Properties

![Getting-Started_img151](Getting-Started_images/Getting-Started_img151.jpeg)

## Column Properties 

This section explores the various column options such as Auto Populate Columns, Auto Populate Relations, Allow Sort, Allow Drag Columns, Allow Resize Columns, Show Column Options, Show Filters, Show Group Drop Area and Column Sizer combo box.

1. Select as you require in this list.

![Getting-Started_img152](Getting-Started_images/Getting-Started_img152.jpeg)

## Row Properties

This section explores the row-related properties such as Show Add New, Show Group Summaries, Show Row Header, Allow Resize Rows, Allow Delete and List Box Selection Modes combo box.

Select as you require in this list.

![Getting-Started_img153](Getting-Started_images/Getting-Started_img153.jpeg)


## Cell Properties

This section explores cell level properties such as Allow Edit, Show Error Tooltips, Show Tooltips, Allow Selection combo box, Activate Current Cell Behavior combo box and Visual Style combo box.

![Getting-Started_img154](Getting-Started_images/Getting-Started_img154.jpeg)

Select as you require in this list.

## Visible Columns

This section automatically generates a property list for each visible column in the grid. Each list includes the column level properties such as Allow Filter, Allow Sort, Allow Drag, Allow Group, Allow Resize, Is Read Only, Auto fit, Width, Header Text field, Column Format combo box and Cell Type combo box.

* Click Visible Columns.
* Two options are displayed

## Generate Columns

### Clear Columns

![Getting-Started_img155](Getting-Started_images/Getting-Started_img155.jpeg)


## Generate Columns

1. Click Generate Columns to populate the properties for each visible column. 
   
   N> Property list for visible column in the grid displays.

   ![Getting-Started_images156](Getting-Started_images/Getting-Started_img156.jpeg)


2. Select as you require. 

   ![Getting-Started_images157](Getting-Started_images/Getting-Started_img157.jpeg)

## Special Cell Types

This combo box lists the various possible cell types applicable to the column. It also automatically deducts the column type of the grid columns and sets the CellType of it. For example, if the column is of Boolean type, it automatically has a CheckBox.

![Getting-Started_img158](Getting-Started_images/Getting-Started_img158.jpeg)

## Clear Columns

Click Clear Columns to clear the visible column settings.
