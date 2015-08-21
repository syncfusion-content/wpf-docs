---
layout: post
title: Overview
description: overview
platform: wpf
control: XlsIO	
documentation: ug
---

# Overview

Essential XlsIO is a 100% native .NET library that generates fully functional Microsoft Excel Spreadsheets in native Excel format without depending on Microsoft Excel. Essential XlsIO is a perfect solution for those who need to read and write Microsoft Excel files from code. It does not require MS Excel to be installed in the report generation machine or server.

Essential XlsIO library can be used in any .NET environment including C#, VB.NET, and managed C++. It is a Non-UI component that can be used in ASP.NET, WindowsForms, WPF, Silverlight, ASP.NET MVC, WinRT, Windows Phone 8 applications, without any change in the API. The usage is common for all the environments, except for the part where the created spreadsheet is saved to disk or stream in the case of a Windows Forms/WPF application and streamed to the client browser in the case of Web applications; there are no temporary Excel files created on the server in an ASP.NET application and async opened/saved as stream in the case of a WinRT/Windows Phone 8 application. Essential XlsIO comes with support for working with formulas in the cells and provides data and worksheet manipulation support. It is known for its high performance with less memory usage for generating Excel files with large number of rows and columns. It is possible to create and modify Excel charts inside a workbook and also has options to secure its contents.

XlsIO can read and write Excel files that are compatible with Excel 97 to Excel 2013. The same Excel file created by using XlsIO can be opened by the following versions of MS Excel. There is no need to create separate files for different versions of Excel.

* Excel 97 (.xls)
* Excel 2000 (.xls)
* Excel 2002 (.xls)
* Excel 2003 (.xls)
* SpreadsheetML (.xml)
* CSV (.csv)
* Excel 2007 (.xlsx)
* Excel 2010 (.xlsx)
* Excel 2013 (.xlsx)



The following image shows a sample worksheet.

![](Overview_images/Overview_img1.png)



Use Case Scenario

* Desktop Application-A sales tracking application generating a report on sales figures for the past year. 
* Web Application-A banking website allowing customers to download monthly statements in MS Excel format.



## Advantages of Using Excel Reports

Microsoft Excel is the most widely used Spreadsheet application in the world that makes XLS/XLSX an ideal reporting format for .NET applications. Some of the advantages of using Excel reports over other alternatives like HTML, PDF, etc. are:

* The report generated may contain rich formats like Charts, Pictures, Multiple Worksheets, Formulae, Tables, PivotTables, Shapes, and so on.
* The end-user can use the Data Visualization power of MS Excel to manipulate the generated reports. For example, the end-user can generate several charts to analyze and understand the sales numbers in a product sales report.
* The popularity of MS Excel guarantees that the end-user is already familiar with MS Excel.



## Problems of Using MS Excel

MS Excel is not designed to be a report generation library, so it has several disadvantages compared to XlsIO. Here is a list of some problems in using Excel as a reporting component:

* Microsoft, themselves do not recommend using Excel as a report generation server-side component. The reasons are clearly explained in the following Knowledge Base article from Microsoft: [http://support.microsoft.com](http://support.microsoft.com/default.aspx?scid=kb;EN-US;q257757). 
* Here is a quote from the article, "Microsoft does not currently recommend, and does not support Automation of Microsoft Office applications from any unattended, non-interactive client application or component (including ASP, DCOM, and NT Services), because Office may exhibit unstable behavior and/or deadlock when run in this environment."
* Speed-Excel automation is about 100 times slower than Essential XlsIO while generating reports.
* Cost-Licensing XlsIO is much cheaper than MS Excel licensing options. Here is a link to a Knowledge Base article from Microsoft-[http://support.microsoft.com.](http://support.microsoft.com/default.aspx?scid=kb;EN-US;q243006)
* Usability-Essential XlsIO has a very intuitive object model that is modeled after the Excel object model, making it easy to work. XlsIO also includes some additional helper functionalities like ImportDataTable method that makes programming with XlsIO much easier than by using COM automation. Intellisense comments also make the job of programming with XlsIO much easier than Excel automation.



