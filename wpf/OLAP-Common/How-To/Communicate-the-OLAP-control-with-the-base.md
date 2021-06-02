---
layout: post
title: Communicate the OLAPCommon control with the base in WPF | Syncfusion
description: Communicate the OLAPCommon control with the base in Syncfusion Essential Studio for WPF, its elements and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Communicate the OLAP control with the base

Each and every control has an OlapDataManager property. Through this property, the control sends and receives information to and from the base. 

## Below steps explains how to load data in an OLAP control:

1. Give the connection information and OlapReport to the OlapDataManager.
2. Assign this OlapDataManager to the control’s OlapDataManager property.
3. By invoking the control’s DataBind() method virtually when setting the value for the OlapDataManager property, the data processing will begin and the output is displayed in the Control.
