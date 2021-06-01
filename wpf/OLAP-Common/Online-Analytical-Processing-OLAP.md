---
layout: post
title: Online Analytical Processing (OLAP) in WPF OLAP Common | Syncfusion
description: Learn about Online Analytical Processing (OLAP) support in Syncfusion WPF OLAP Common control and more.
platform: wpf
control: OLAP Common
 documentation: ug
---

# Online Analytical Processing (OLAP) in WPF OLAP Common

Online Analytical Processing (OLAP) is a service that performs a real time, multi-dimensional analysis of complex data stored in a database. The OLAP typically consists of a server component that uses specialized algorithms, indexing tools to efficiently process data mining tasks and an OLAP client that efficiently allows you visualize the OLAP data pertaining to your business needs.

Here is how Wikipedia defines [OLAP](http://en.wikipedia.org/wiki/Online_analytical_processing).

## ADOMD.NET

The Syncfusion OLAP controls use the [ADOMD.NET](https://docs.microsoft.com/en-us/previous-versions/sql/sql-server-2005/ms123483(v=sql.90)), which is a Microsoft .NET Framework provider for retrieving data from OLAP servers in .NET platform. While ADOMD.NET primarily retrieves OLAP data from the SQL Server Analysis Services (Microsoft's OLAP Server), it is adherence to industry standards like XML/A, which allows you access any OLAP server (SAP, SAS, Hyperion, etc.) using it. This provides you the ability to visualize the OLAP data from myriads of data sources including Microsoft's SSAS using the Syncfusion OLAP control.

## ADOMD.NET assembly and setup files information

The following assembly is required to run the Syncfusion’ OLAP samples.

* Microsoft.AnalysisServices.AdomdClient.dll

Install the following setup files for the above assembly.

* SQLServer2005_ADOMD.msi and SQLServer2005_ASOLEDB9.msi 

Or 

* SQLSERVER2008_ASADOMD10.msi and SQLSERVER2008_ASOLEDB10.msi

These setup files can be downloaded at [Microsoft download center](http://www.microsoft.com/en-us/download/details.aspx?id=23089).

N>  By default, the following setup files will be installed while installing the Syncfusion’ Essential Studio setup for BI edition.
N> SQLSERVER2008_ASADOMD10.msi and SQLSERVER2008_ASOLEDB10.msi









