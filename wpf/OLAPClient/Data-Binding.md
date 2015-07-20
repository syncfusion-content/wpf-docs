---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: OLAP Client 
documentation: ug
---

# Data Binding

You can bind the OLAP Client control to the Server or Offline Cube. To do so, you have to create an OlapDataManager and initialize it by passing a valid connection string.

## Binding OLAP Client to the Server

The following code example illustrates the binding of the OLAP Client control to a server.

[C#]



OlapDataManager olapDataManager = new OlapDataManager("Data  source=localhost; Initial Catalog=Adventure Works DW");

this.olapClient1.OlapDataManager = olapDataManager;

this.olapClient1.DataBind();





[VB]



Dim olapDataManager As OlapDataManager = New OlapDataManager("Data source=localhost; Initial Catalog=Adventure Works DW")

Me.olapClient1.OlapDataManager = olapDataManager

Me.olapClient1.DataBind()

## Binding OLAP Client to the Offline Cube

The following code example illustrates how to bind the OLAP Client control to an offline cube.

[C#]



OlapDataManager olapDataManager = new OlapDataManager("Datasource=AdventureWorks.cub; Provider=msolap;");

this.olapClient1.OlapDataManager = olapDataManager;

this.olapClient1.DataBind();





[VB]



Dim olapDataManager As OlapDataManager = New OlapDataManager("Datasource=AdventureWorks.cub; Provider=msolap;")

Me.olapClient1.OlapDataManager = olapDataManager

Me.olapClient1.DataBind()





