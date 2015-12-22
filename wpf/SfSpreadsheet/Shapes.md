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
<br/>

## Sparklines

To import the Sparklines into SfSpreadsheet, need to create an instance of [SparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9649.html) and add that renderer into [GraphicCellRenderers](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8157.html) collection. The [SparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9649.html) is available under the this assembly “Syncfusion.SfSpreadsheetHelper.WPF.dll”

Add the SparklineCellRenderer into the GraphicCellRenderers collection by using the extension method [AddSparklineCellRenderer](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheethelper/topic9264.html) of SfSpreadsheet which method is available under the namespace “Syncfusion.UI.Xaml.Spreadsheet.Helpers”.

{% tabs %}
{% highlight c# %}

    this.spreadsheet.AddSparklineCellRenderer(new SparklineCellRenderer());

{% endhighlight %}
{% endtabs %}

