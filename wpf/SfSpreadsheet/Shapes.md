---
layout: post
title: Conversion | SfSpreadsheet | WPF | Syncfusion
description: shapes
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Shapes
 This section explains how to import charts and sparklines in SfSpreadsheet
<br/>

## Charts

SfSpreadsheet provides support to import charts from excel which are used to represent numeric data in graphical format to make it easier to understand large quantities of data.

To import the charts into SfSpreadsheet, need to create an instance of [GraphicChartCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9639.html) and add that renderer into [GraphicCellRenderers](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8157.html) collection. The [GraphicChartCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9639.html) is available under the this assembly “Syncfusion.SfSpreadsheetHelper.WPF.dll “

Add the GraphicChartCellRenderer into the GraphicCellRenderers collection by using the extension method [AddGraphicChartCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9263.html) of SfSpreadsheet which method is available under the namespace “Syncfusion.UI.Xaml.Spreadsheet.Helpers”.

{% tabs %}
{% highlight c# %}

    this.spreadsheet.AddGraphicChartCellRenderer(new GraphicChartCellRenderer());

{% endhighlight %}
{% endtabs %}

For adding the Charts in SfSpreadsheet at runtime, use **AddChart** method, also you can resize and reposition the chart.

{% tabs %}
{% highlight c# %}

var chart = spreadsheet.AddChart(spreadsheet.ActiveSheet);

object[] Yvalues = new object[] { 200, 100, 100 };
object[] Xvalues = new object[] { "Total Income", "Expenses", "Profit" };

IChartSerie series = chart.Series.Add(ExcelChartType.Pie);

// Enters the X and Y values directly
series.EnteredDirectlyValues = Yvalues;
series.EnteredDirectlyCategoryLabels = Xvalues;

var shape = chart as ShapeImpl;

// Re-Positioning Chart
shape.Top = 200;
shape.Left = 200;

//Re-sizing a Chart
shape.Height = 300;
shape.Width = 300;
{% endhighlight %}
{% endtabs %}
<br/>

## Sparklines

To import the Sparklines into SfSpreadsheet, need to create an instance of [SparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9649.html) and add that renderer into [GraphicCellRenderers](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8157.html) collection. The [SparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9649.html) is available under the this assembly “Syncfusion.SfSpreadsheetHelper.WPF.dll”

Add the SparklineCellRenderer into the GraphicCellRenderers collection by using the extension method [AddSparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9264.html) of SfSpreadsheet which method is available under the namespace “Syncfusion.UI.Xaml.Spreadsheet.Helpers”.

{% tabs %}
{% highlight c# %}

    this.spreadsheet.AddSparklineCellRenderer(new SparklineCellRenderer());

{% endhighlight %}
{% endtabs %}
<br/>

## Image

SfSpreadsheet provides support to import images in SpreadsheetGrid and to add an image at run time, use **AddImage** method and also you can resize and reposition the image.

{% tabs %}
{% highlight c# %}

var worksheet = spreadsheet.ActiveSheet;
var stream = typeof(MainWindow).Assembly.GetManifestResourceStream("GraphicCellDemo.Data.Sample.jpg");
var shape = spreadsheet.AddImage(worksheet, new RowColumnIndex(5, 5), stream);

// Re-Positioning Picture
shape.Top = 200;
shape.Left = 200;

 //Re-sizing a Picture
shape.Height = 200;
shape.Width = 200;

{% endhighlight %}
{% endtabs %}
<br/>

## Text Box

SfSpreadsheet provides support to import RichText Box in SpreadsheetGrid and to add the richtext box at run time, use **AddTextBox** method

{% tabs %}
{% highlight c# %}

var rtfText = "{\\rtf1\\ansi\\ansicpg1252\\deff0\\deflang1033{\\fonttbl{\\f0\\fnil\\fcharset1 Calibri;}{\\f1\\fnil\\fcharset1 Calibri;}}{\\colortbl;\\red0\\green0\\blue0;\\red255\\green0\\blue0;}{\\f0\\fs22\\b\\cf1\\u83*\\u121*\\u110*\\u99*\\u102*\\u117*\\u115*\\u105*\\u111*\\u110*\\u32*\\b0}                           {\\f1\\fs22\\cf2\\u83*\\u111*\\u102*\\u116*\\u119*\\u97*\\u114*\\u101*\\u32*}{\\f1\\fs22\\cf1\\u80*\\u118*\\u116*\\u46*\\u32*\\u76*\\u116*\\u100*}}";
  
var textBox = spreadsheet.AddTextBox(spreadsheet.ActiveSheet, new RowColumnIndex(5, 5), new Size(200, 200), rtfText) as TextBoxShapeImpl;

// Re-positioning RichTextBox
textBox.Left = 200;
textBox.Top = 200;
         
{% endhighlight %}
{% endtabs %}
