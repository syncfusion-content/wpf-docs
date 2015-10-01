---
layout: post
title: Online-Analytical-Processing-OLAP
description: online analytical processing (olap)
platform: wpf
control: OLAPCommon 
documentation: ug
---

# Online Analytical Processing (OLAP)

Online Analytical Processing (OLAP) is a service that performs a real time, multi-dimensional analysis of complex data stored in a database. The OLAP typically consists of a server component that uses specialized algorithms, indexing tools to efficiently process data mining tasks and an OLAP client that efficiently lets you visualize the OLAP data pertaining to your business needs.

Here is how Wikipedia defines [OLAP](http://en.wikipedia.org/wiki/Online_analytical_processing).

## ADOMD.NET

The Syncfusion OLAP controls use the [ADOMD.NET](http://msdn.microsoft.com/en-us/library/ms123483(v=sql.90).aspx), which is a Microsoft .NET framework provider for retrieving data from OLAP servers in .NET platform. While ADOMD.NET primarily retrieves OLAP data from SQL Server Analysis Services (Microsoft's OLAP Server), it's adherence to industry standards like XML/A allows you to access any OLAP server (SAP, SAS, Hyperion, etc.) through it and hence provides you the ability to visualize using Syncfusion OLAP control, OLAP data from myriads of data sources including Microsoft's SSAS.

## ADOMD.NET assembly and setup files information

The following assembly is required to run Syncfusion’ OLAP samples:

* Microsoft.AnalysisServices.AdomdClient.dll

Install the following setup files for the above assembly:

* SQLServer2005_ADOMD.msi and SQLServer2005_ASOLEDB9.msi 

Or 

* SQLSERVER2008_ASADOMD10.msi and SQLSERVER2008_ASOLEDB10.msi

These setup files can be downloaded at [Microsoft download center](http://www.microsoft.com/download/en/details.aspx?displaylang=en&id=8824).

N>  By default the below setup files will be installed while installing Syncfusion’ Essential studio setup for BI edition:
N> SQLSERVER2008_ASADOMD10.msi and SQLSERVER2008_ASOLEDB10.msi









