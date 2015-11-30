---
layout: post
title: Working with Spreadsheet | SfSpreadsheet | WPF | Syncfusion
description: working with spreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Working with Spreadsheet

## Working with Worksheet

A __workbook__ is an excel document in the SfSpreadsheet. It is an object that exposes the IWorkbook interface. To access a workbook that is currently loaded in the SpreadsheetControl, “spreadsheet.Workbook” property is used

A workbook consists of one or more worksheets stored within the worksheet collection. Accessing the worksheets in the collection, can be done by the following ways,

{% highlight c# %}

    //By Specifying the index as,
      spreadsheet.Workbook.Worksheets[0]
    //By Specifying the sheet name as,
      spreadsheet.Workbook.Worksheets["sheet1"]
    //Access the Active worksheet as,
      spreadsheet.ActiveSheet
      
{% endhighlight %}

For more information regarding working with worksheets, you can refer the following link

[http://help.syncfusion.com/file-formats/xlsio/overview](http://help.syncfusion.com/file-formats/xlsio/overview# "")

## Working with Grid

Each worksheet in the workbook is loaded into the view as SpreadsheetGrid in the SfSpreadsheet.

{% highlight c# %}

    //Access the Active SpreadsheetGrid as,
      spreadsheet.ActiveGrid

{% endhighlight %}

When the workbook is loaded in the SfSpreadsheet, the WorkbookLoaded Event is invoked and when the workbook is removed from SfSpreadsheet, the WorkbookUnloaded Event is invoked.

You can also access the each SpreadsheetGrid in the SfSpreadsheet by invoking WorkbookLoaded Event of SfSpreadsheet. 

{% highlight c# %}

    spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

    spreadsheet.WorkbookUnloaded += spreadsheet_WorkbookUnloaded;

    void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)

    {

      //Hook the events here

         foreach (var grid in args.GridCollection)

           grid.QueryRange += grid_QueryRange; 

    }

    void spreadsheet_WorkbookUnloaded(object sender, WorkbookUnloadedEventArgs args)

    {

      //Unhook the events here

         foreach (var grid in args.GridCollection)

           grid.QueryRange -= grid_QueryRange; 

    }

{% endhighlight %}

SfSpreadsheet supports virtual mode, which lets you dynamically provide data to the grid by handling an event, QueryRange, for example. In virtual mode, data will be dynamically loaded into the SpreadsheetGrid on demand or when users need to view the data.

When the worksheet is added into the SfSpreadsheet, the WorksheetAdded Event is invoked and when the worksheet is removed in the SfSpreadsheet, WorksheetRemoved Event is invoked.

You can hook the events in WorksheetAdded Event and unhook or remove the objects, in WorksheetRemoved Event in SfSpreadsheet.

{% highlight c# %}

    spreadsheet.WorksheetAdded += spreadsheet_WorksheetAdded;

    spreadsheet.WorksheetRemoved += spreadsheet_WorksheetRemoved;

    void spreadsheet_WorksheetRemoved(object sender, WorksheetRemovedEventArgs args)

    {

       //Unhook the events

       var grid = spreadsheet.ActiveGrid;

       grid.CurrentCellActivated -= grid_CurrentCellActivated;

    }

    void spreadsheet_WorksheetAdded(object sender, WorksheetAddedEventArgs args)

    {

       //hook the events

       var grid = spreadsheet.ActiveGrid;

       grid.CurrentCellActivated += grid_CurrentCellActivated;

    }

{% endhighlight %}

