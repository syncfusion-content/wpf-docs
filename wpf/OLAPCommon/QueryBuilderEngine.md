---
layout: post
title: QueryBuilderEngine| OLAPCommon  | Wpf | Syncfusion
description: querybuilderengine
platform: wpf
control: OLAPCommon 
documentation: ug
---

# QueryBuilderEngine

This class will generate the query from the MDXQuerySpecification. The query generation starts from invoking the GenerateQueryEx() static method of QueryBuilderEngineVersion3, the inner class of QueryBuilderEngine class. 

## MDXQuerySpecification

MDXQuerySpecification is the base for query creation. The MDXQuerySpecification will categorize the element into three clauses namely:

* With
* Select and
* Where

The elements in the given report are iterated and stored according to the specification.

* The calculated member element in the given report will be added under the With clause.
* The categorical and series items in the given report’s categorical elements and series element will come in the Select category.
* The Slicer and Filter items will comes under the Where category.

Based on the current report, the TogglePivot value and the axis position of each item will be assigned before it is stored in the appropriate clauses.

![](MDXQuerySpecification_images/MDXQuerySpecification_img1.png)





 MDXQuerySpecification
 {:.caption}



Once the query specification is created, the GenerateQueryEx() method of QueryBuilderEngine was called by passing the created MDXQuerySpecification to generate the query.

## Steps in Query Generation

To generate a query:

1. Get the query specification and iterate through the items in each category (With, Select and Where) of specification and separately store the column elements, row elements, filter elements and slice elements.
2. The filter, slicer and sort elements are moved to the appropriate axis based on their axis property.
3. Once the initial level categorizing of elements is completed, it starts creating a query string by writing using With or Select.
4. Now it starts writing the query by checking each and every property. 



By invoking the BuildAxisElements() method, the building query for the column axis elements and row axis elements are done.

### The helper methods for the BuildAxisElements() are:

* BuildAxisItems
* BuildDimensionElement
* If no level is specified, the  GetDefaultLevel() method will be called else
* The BuildHierarchyElement() will be called
* BuildLevelElements
* If the level member count is greater than zero the BuildMemberElement() will be called else the GetDefaultLevel() method will be called.

The BuildAxisElements() will build the query for the column element when we pass the column items and it will generate the query for the row elements when the row items is passed as an argument. The BuildAxisElements() method will return a Boolean value which represents whether the KPI element is existing in the given item list or not. Based on that return, the value of the KPI Element axis was fixed.

Up to this the Select section of the query was built and now the From section. The From section will start by invoking the BuildFilterCondition() method.

### The Helper method for the BuildFilterCondition() is given below:

1. BuildFilterElements() - This method iterates through the elements and appends the parent details and child member details in the query based on the axis either in a row or in a column.
2. Then it comes to the Where section, by invoking the BuildSlicerElements() method.
3. Then the BuildSlicerItem is invoked. This method will check whether the given item is Dimension or Measure or KPI or NamedSet or Level and based on this the appropriate query part will appended with the query.



Finally, the Cell properties will append with the created query and the query string will be returned to the OlapDataManager. By using the newly generated query, the OlapDataManager will invoke the ExecuteCellSet of DataProvide, which will return the CellSet. 

This CellSet will be used to create the PivotEngine, which will give the input to the controls. 



