---
layout: post
title: Creating-the-OlapReport
description: creating the olapreport
platform: wpf
control: OLAP Common 
documentation: ug
---

# Creating the OlapReport

## To create a report:

1. Instantiate a new object for OlapReport.
2. Create the required elements like dimension element, measure elements.
3. Add the created element in the desired axis (Column or Categorical, Row or Series, Filter or Slicer) elements. 
4. Then bind the created report to the OlapDataManager using the SetCurrentReport() method or assign the report to OlapDataManager’s current report property.
