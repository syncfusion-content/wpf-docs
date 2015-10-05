---
layout: post
title: Data Source| OLAP Chart | Wpf | Syncfusion
description: Data Source
platform: wpf
control: OLAP Chart
documentation: ug
---

# Data Source

## Definition

Olap Grid controls use ADO-MD, which is Microsoft's data access technology of choice for retrieving data from OLAP servers. While ADO-MD was built primarily to retrieve OLAP data from SQL Server Analysis Services (Microsoft's OLAP Server), ADO MD's adherence to industry standards like XML/A, now allows you to access any OLAP server (SAP, SAS, Hyperion, etc.) through ADO MD. Therefore, it provides you the ability to visualize by using the Syncfusion OLAP control, OLAP data from many of the data sources including Microsoft's SSAS.

## Binding to OLAP Data

OlapData can be bound to the OlapGrid with the help of the OlapDataManager. The OlapDataManager requires the OlapReport, which contains the Dimension and the Measure Elements.

## Relational Data Support

OlapGrid control supports binding of Relational Data Source like DataTable or IList for data analysis. It organizes the data into a cross-tabulated form based on the parameters defined in the OlapData Manager. It sorts and sums independently of the original data layout in the grid.
