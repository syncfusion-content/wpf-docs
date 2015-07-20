---
layout: post
title: Real-Time-Applications
description: real time applications
platform: wpf
control: Grid Control
documentation: ug
---

# Real Time Applications

This section discusses about the real time application called Excel-like UI, which describes the different excel-like features in a grid.

## Excel-like UI

Grids can be adopted in many real time applications where the database is of crucial importance. As such applications are widely spread; the grids are indispensably used world-wide.  This section elaborates on some of the real time applications which can use Essential Grid.

Real-time Applications

Some real time applications which can use Essential Grid are listed below:

* Applications with high frequency updates
* Excel like UI applications



1. Applications with High Frequency Updates 

Grid can be used in applications with frequent updates, for example stock values in share market. When grid is switched over to virtual mode, it reforms itself as a light weight control that consumes a very little memory and processing power, and provides a very small latency under heavy load. Such virtual grids are typically useful when there is a need to display enormous data very quickly.  

Sample

A sample which demonstrates such an application is available in the following sample installation location:

_...\My Documents\Syncfusion\EssentialStudio\<Version Number>\WPF\Grid.WPF\Samples\3.5\WindowsSamples\Performance\Trader Grid Test Demo_

> _Note: Refer Performance Optimization section which elaborates on this sample._

2. Excel-like UI Applications

Another important application is Excel like UI that simulates MS Excel 2007 and gives an appearance that resembles excel. This application exhibits the following excel characteristics:

* Excel like Current Cell
* Formula Cells
* Excel like Selection Frame
* Markup Headers
* Workbook of sheets

a. Excel-like Current Cell

You can select a current cell in the Grid, similar to the current cell behavior in MS Excel. This feature can be enabled, by setting GridModelOptions.ExcelLikeCurrentCell property to _true_, as follows:  



[C#]



grid.Model.Options.ExcelLikeCurrentCell = true;





{{ '![](Real-Time-Applications_images/Real-Time-Applications_img1.jpeg)' | markdownify }}
{:.image }


> _Note:  If you have selected a current cell within a specified range, and when you move the current cell selection out of this range, the range will be cleared._



b. Excel-like Selection Frame

The active selection can be outlined with a selection frame by setting the GridModelOptions.ExcelLikeSelectionFrame property to true, as follows:



[C#]



grid.Model.Options.ExcelLikeSelectionFrame = true;





{{ '![](Real-Time-Applications_images/Real-Time-Applications_img2.jpeg)' | markdownify }}
{:.image }


c. Formula Cells

As we discussed in the previous chapter, Grid control provides complete support to formula cells. It can be enabled for the grid by setting the format string, FormulaCell to the TableStyle.CellType property, as follows: 



[C#]



grid.Model.TableStyle.CellType = "FormulaCell";





{{ '![](Real-Time-Applications_images/Real-Time-Applications_img3.jpeg)' | markdownify }}
{:.image }




d. Markup Headers

In Excel, whenever a selection is made, the headers of those rows and columns which are involved in the selection will be highlighted. You can get a similar behavior in the Grid using the OnPrepareRenderCell event.  

OnPrepareRenderCell event-This event will be triggered for every cell when they are about to be rendered. Hence, using this event, the cells that are going to be rendered are identified and their headers are highlighted.

The following code illustrates how to handle this event:



[C#]



protected override void OnPrepareRenderCell(GridPrepareRenderCellEventArgs e)

{

    base.OnPrepareRenderCell(e);

    if (e.Cell.RowIndex == 0 && Model.SelectedRanges.AnyRangeIntersects(GridRangeInfo.Col(e.Cell.ColumnIndex)))

    {

        e.Style.Background = this.excelOrange;

    }

    else if (e.Cell.ColumnIndex == 0 && Model.SelectedRanges.AnyRangeIntersects(GridRangeInfo.Row(e.Cell.RowIndex)))

    {

        e.Style.Background = this.excelOrange;

    }

}



{{ '![](Real-Time-Applications_images/Real-Time-Applications_img4.jpeg)' | markdownify }}
{:.image }




e. Workbook of Sheets

You can create a workbook with multiple sheets similar to excel, using a Tab control, where individual tab represents a worksheet embedded within a Grid control.



{{ '![](Real-Time-Applications_images/Real-Time-Applications_img5.jpeg)' | markdownify }}
{:.image }


Complete Sample Output



{{ '![](Real-Time-Applications_images/Real-Time-Applications_img6.jpeg)' | markdownify }}
{:.image }


> _Note: For the complete code for this example, refer the following browser sample:_ 

> _...\My Documents\Syncfusion\EssentialStudio\<Version Number>\WPF\Grid.WPF\Samples\3.5\WindowsSamples\Product Showcase\Excel Like UI Demo_



