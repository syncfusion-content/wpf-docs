---
layout: post
title: Performance in WPF GridControl | Syncfusion
description: Learn about Performance support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: GridControl
documentation: ug
---

# Performance in WPF GridControl

Essential Grid is well known for its optimized performance. This section points out a sample that illustrates how to do high frequency updates in Grid control.

## Sample Architecture

Inside SampleGridControl.cs file, you can define various test scenarios. The basic test will load a data table with values and then modify the records inside a timer (timer is used to keep changing the grid values at regular intervals in order to illustrate run time updates) at run time. This will trigger ListChanged event. FlatDataViewGrid control listens to these events and updates the data displayed, by highlighting the cells that were changed, and also updates the resulting summaries.

## Sample Features

The features of this sample are listed below:

* This FlatDataViewGrid control is implemented using a virtual grid approach by wiring the grid to the data view using the QueryCellInfo and CommitCellInfo event handlers.
* Blinking behavior in the sample is implemented by handling OnPrepareRenderCell event using the PrepareRenderCellInfo handler.

N> Blinking Behavior-You cud see random values get updated frequently and those changed fields are highlighted by colors. For ex., increase in value is indicated in green color and decrease in value in red color. It also highlights the insertion of new records.

* The grid handles all ListChanged notifications including ItemAdded, ItemMoved, ItemDeleted, Reset, PropertyDescriptorAdded, PropertyDescriptorDeleted and PropertyDescriptorChanged.
* When the current cell is active, you can continue editing and modify the contents of the currently active cell even while rows are re-arranged. This is often a requirement in applications that wish to maintain editing compatibility even while processing a large number of updates.


![Trader Grid Test Demo in WPF GridControl](Performance_images/Performance_img1.jpeg)


N> Download demo application from [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/gridcontrol/Performance/TraderGridTest)

### Example 

Let us consider a sample using a FlatDataViewGrid control, which is a regular grid that is bound to a flat data view (flat table, which is not nested and without relations) and is customized to handle refresh updates (refreshing the grid values, which in turn replaces old values with new values). It has a header row with field names and a footer row with summaries. 
