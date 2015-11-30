---
layout: post
title: Conversion | SfSpreadsheet | WPF | Syncfusion
description: shapes
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Shapes

## Charts

SfSpreadsheet provides support to import charts from excel which are used to represent numeric data in graphical format to make it easier to understand large quantities of data.

To import the charts into SfSpreadsheet, need to create an instance of __GraphicChartCellRenderer__ and add that renderer into GraphicCellRenderers collection. The __GraphicChartCellRenderer__ is available under the this assembly “Syncfusion.SfSpreadsheetHelper.WPF.dll “

Add the GraphicChartCellRenderer into the GraphicCellRenderers collection by using the extension method “AddGraphicChartCellRenderer” of SfSpreadsheet which method is available under the namespace “Syncfusion.UI.Xaml.Spreadsheet.Helpers”.

{% highlight c# %}

    this.spreadsheet.AddGraphicChartCellRenderer(new GraphicChartCellRenderer());

{% endhighlight %}

## Sparklines

To import the Sparklines into SfSpreadsheet, need to create an instance of __SparklineCellRenderer__ and add that renderer into GraphicCellRenderers collection. The __SparklineCellRenderer__ is available under the this assembly “Syncfusion.SfSpreadsheetHelper.WPF.dll”

Add the SparklineCellRenderer into the GraphicCellRenderers collection by using the extension method “AddSparklineCellRenderer” of SfSpreadsheet which method is available under the namespace “Syncfusion.UI.Xaml.Spreadsheet.Helpers”.

{% highlight c# %}

    this.spreadsheet.AddSparklineCellRenderer(new SparklineCellRenderer());

{% endhighlight %}

