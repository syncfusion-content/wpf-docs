---
layout: post
title: Process OlapReport Internally| OLAPCommon | Wpf | Syncfusion
description: process olapreport internally
platform: wpf
control: OLAPCommon
 documentation: ug
---

# Process OlapReport Internally

Once the OlapReport is created and bound to the OlapDataManager, the data processing begins. By binding the report, the given report will be set as the current report of the OlapDataManager and it will invoke the two important methods that let the way to generate the MDXQuery and CellSet.

* NotifyReportChanged
* NotifyElementModified



## NotifyReportChanged

After initialization the data processing begins. When the NotifyReportChanged is invoked, it triggers the ReportChanced event, which will be handled by the control level.



## NotifyElementModified



The NotifyElementModified method begins the processing by invoking the ExecuteCellSet() method, which create the CellSet and PivotEngine based on the OlapReport.



The ExecuteCellSet() method checks whether the user has given the MDX query.If the query exists, it will invoke an overloaded method of the ExecuteCellSet(string _query_) which in turn calls the ExecuteCellSet(string query, bool b1, bool b2) of DataProvider class. The given query will be executed in the DataProvider class and the CellSet will be produced. 

If the query does not exist, the overloaded method of ExecuteCellSet (MDXQuerySpecification) will get invoked. This method will invoke the MDXQuerySpecification creation and from there the query creation will be invoked and the query will be returned. The ExecuteCellSet() method receives the query and passes it to the data provider’s ExecuteCellSet method. The query will be executed there on the connected database and a CellSet will be returned.  From the CellSet, the PivotEngine will be created, from which the controls can get their input.

