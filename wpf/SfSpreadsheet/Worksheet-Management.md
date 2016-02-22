---
layout: post
title: Worksheet Management
description: How to insert, delete and other operations related with worksheet in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Worksheet Management
 This section explains about the operations that are performed with the worksheet.
<br/>
<br/>

## Insert and Delete

SfSpreadsheet provides support to insert and delete the worksheets in a workbook.

{% tabs %}
{% highlight c# %}

//Insert Sheet

 spreadsheet.AddSheet();
	
//Insert sheet with name

 spreadsheet.AddSheet("Sheet4", 3);

//Delete Sheet

 spreadsheet.RemoveSheet("Sheet2");

{% endhighlight %}
{% endtabs %}
<br/>

## Hide and Unhide

SfSpreadsheet provides support to hide and unhide the worksheets in a workbook.

{% tabs %}
{% highlight c# %}

//Hide Sheet

 spreadsheet.HideSheet("Sheet 2");

//Unhide Sheet

 spreadsheet.UnhideSheet("Sheet 2");

{% endhighlight %}
{% endtabs %}
<br/>

## Gridlines

SfSpreadsheet provides support to control the visibility and color of the Gridlines in a worksheet.

{% tabs %}
{% highlight c# %}

//To show GridLines

spreadsheet.SetGridLinesVisibility(true);

//To hide GridLines

spreadsheet.SetGridLinesVisibility(false);

{% endhighlight %}
{% endtabs %}
<br/>

## Headings

SfSpreadsheet provides support to control the visibility of row and column headers in a worksheet

{% tabs %}
{% highlight c# %}

//To hide the Header cells visibility

spreadsheet.SetRowColumnHeadersVisibility(false);

{% endhighlight %}
{% endtabs %}
<br/>

## Zooming

SfSpreadsheet provides support to zoom in and zoom out of a worksheet view. The property [AllowZooming](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~AllowZooming.html) determines whether to allow zooming or not.

{% tabs %}
{% highlight c# %}

//zoomfactor
 spreadsheet.SetZoomFactor("Sheet1", 200);

{% endhighlight %}
{% endtabs %}

The Events associated with the Zooming are 

. [ZoomFactorChanged](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanged_EV.html)

. [ZoomFactorChanging](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfSpreadsheet.WPF~Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet~ZoomFactorChanging_EV.html)

<br/>
<br/>

## Protection
<br/>

### Workbook Protection

SfSpreadsheet provides support to protect the structure and windows of a workbook. By protecting the structure, prevent a user from adding or deleting worksheets or from displaying hidden worksheets. By protecting the windows in the workbook, you can control the size of the workbook, etc.

{% tabs %}
{% highlight c# %}

// To Protect the Workbook 

spreadsheet.Protect(true, true, "123");

//To Unprotect the Workbook

spreadsheet.Unprotect("123");

{% endhighlight %}
{% endtabs %}
<br/>

### Worksheet Protection

SfSpreadsheet provides support to protect the worksheet with or without password. This helps to prevent a user from modifying the contents of the worksheet. The protection of worksheet can be done with protection options also.

{% tabs %}
{% highlight c# %}

//Protect the sheet with password

spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123");

//Protect the sheet with Protection options

spreadsheet.ProtectSheet(spreadsheet.ActiveSheet, "123", ExcelSheetProtection.All);

//Unprotect the sheet

spreadsheet.UnProtectSheet(spreadsheet.ActiveSheet, "123");

{% endhighlight %}
{% endtabs %}

