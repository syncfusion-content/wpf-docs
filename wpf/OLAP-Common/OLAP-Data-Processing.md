---
layout: post
title: OLAP Data Processing in WPF OLAP Common control | Syncfusion
description: Learn about OLAP Data Processing support in Syncfusion WPF OLAP Common control, its elements and more details.
platform: wpf
control: OLAP Common
documentation: ug
---

# OLAP Data Processing in WPF OLAP Common

The OlapDataManager accepts an input from a user and processes the data based on the supplied input and generates the formatted output which Syncfusion OLAP controls can understand. The OlapDataManager can process the OLAP data (cube).

## Steps in processing OLAP data

To process the OLAP data:

1. Provide an input to establish a connection to the specified data source. The connection information can be given as a connection string that contains information about the data source.

   Example connection string: “DataSource = localhost; Initial Catalog = AdventureWorksDW”;

2. Connect to a server or an offline cube as a data source.
3. After the connection is established, provide the input for data processing. You can give two types of inputs to process the OLAP data. They are:
   * MDX Query: You can write a MDX Query for the database and give that query as an input.
   * OlapReport: You can create an OLAP report and give that report as an input to the OlapDataManager.
4. The output will not differ, based on the input type. The processing method will differ in OLAP base, based on the input type.
5. If MDX query is given as an input then the query will be executed on the connected database.
6. If OlapReport is given as an input:
   1. MDX query specification will be created based on the OlapReport.
   2. From the MDX query specification, the MDX query will be generated with the help of OlapQueryBuilderEngine.
   3. The generated query will be executed on the connection database.
7. After the query is executed either from the MDX query input or from the OlapReport input, the result is obtained.
8. This result set will be formatted to provide input for the controls. The formatted input should be passed to the controls.
9. The output will be displayed in the controls.



## In Silverlight

1. The OlapDataManager requires an OlapReport and a virtual channel in the form of _OlapDataManager_.
2. The _OlapDataManager_ is a set to control and in the _DataBind_ method, the control will make an asynchronous call with the help of a virtual channel provided in _OlapDataManager._
3. Now, with the help of WCF Service, the control communicates with OLAP base to retrieve _CellSet_.
4. The control passes the obtained _CellSet_ to the _OlapDataManager_ and in turn the _OlapDataManager_ returns the _PivotEngine_ to the control.
5. The output will reflect in the controls.



