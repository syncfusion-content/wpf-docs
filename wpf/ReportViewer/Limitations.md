---
layout: post
title: Limitations | ReportViewer | WPF | Syncfusion
description: limitations
platform: wpf
control: ReportViewer
documentation: ug
---

# Limitations

## RDL Specification support

* Report Viewer control supports RDL Specification for SQL Server 2008 and RDL Specification for SQL Server 2008 R2 only. Refer to MSDN for list of available specifications - https://msdn.microsoft.com/library/dd297486(SQL.100).aspx.
* ReportViewer control does not support RDL Specification for SQL Server 2000 and RDL Specification for SQL Server 2005.


## Layout Process

SyncfusionReport Viewer control has some limitations in Tablix Cell split Layout process in comparison with MS ReportViewer. When table cell width value exceeds the page width, the entire cell moves to the next page in order to display the complete cell items. 

## Unsupported expression

* Object function and VB function do not have complete support in Report Viewer.
* VB Code functions are not supported in Silverlight and WinRT Report Viewer.