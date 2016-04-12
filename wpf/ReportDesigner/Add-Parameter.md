---
layout: post
title: Add Parameter | ReportDesigner | wpf | Syncfusion
description: add parameter
platform: wpf
control: Report Designer
documentation: ug
---

# Add Parameter

You can add parameter to the Report Designer using the following steps.

1. In the Report Data, Click New, and then click the DataSet.

   ![](Add-Parameter_images/Add-Parameter_img1.png)

2. Right click on the Parameters and click Add Parameter.

   ![](Add-Parameter_images/Add-Parameter_img2.png)

3. Then Report Parameter Properties dialog opens.

4. In Report Parameter Properties, select any of the following in General tab.

   ![](Add-Parameter_images/Add-Parameter_img3.png)

   * Name - Type the name of the parameter or accept the default name. 
   
   * Prompt -  Type the text that appears next to the parameter text box when the user runs the report.
   
   * Data type - Select the data type for the parameter value.
   
   * Allow blank value - To allow a user to select blank value for the parameter.
   
   * Allow null value - To allow a user to select null value for the parameter.
   
   * Allow multiple values - To allow a user to select more than one value for the parameter. 
   
   * Visible - To show the parameter on the toolbar at the top of the report.
   
   * Hidden - To hide the parameter so that it does not display on the toolbar. 
   
   * Internal - To hide the parameter and protect it from being modified on the report server after the report is published. 

5. In Report Parameter Properties, select any of the following in Available Values tab. 

   ![](Add-Parameter_images/Add-Parameter_img4.png)

   * Default values - Select an option to display default values from a query or from a static value.

   * Specify Values - Select this option to enter a static list of parameter values from which the user can choose. If you select this option, a list in which you can type values and labels appears.

   * Label - Appears only when Specify Values is selected. Type a label that is displayed to the user. When the user clicks the label in the list, the value specified in Value is retained for the parameter.

   * Value - Appears only when Specify Values is selected. Type a value that will be retained for the parameter.
   
   * Get Values from a query - Select Get Values from a query to provide a dynamic list of parameter values from which the user can choose. This list is obtained from a data source. If you select From query, three fields appear in which you can define query information.

   * Dataset - Appears only when Get Values from a query is selected. Select a dataset from which to retrieve the list of parameters. You define datasets using the Data view. For more information, see Defining Report Datasets.

   * Value field - Appears only when Get Values from a query is selected. Select a field from which to obtain a list of available values, for example, EmployeeID. The available fields are retrieved from a list of column or field names in the dataset.

   * Label field - Appears only when Get Values from a query is selected. Select a field from which to obtain a list of labels to display to the user for the values, for example, EmployeeName. The available fields are retrieved from a list of column or field names in the dataset.

   ![](Add-Parameter_images/Add-Parameter_img5.png)
   
6. In Report Parameter Properties, select any of the following in Default Values tab. 

   ![](Add-Parameter_images/Add-Parameter_img6.png)

   * No Default values - Select No default values, if you do not want to provide a default value for the parameter.

   * Specify Values - Select Specify Values to enter a static default value or a set of default values for the parameter. If you select Specify Values, a text box appears in which you type a value or set of values. Click the expression button to edit the expression

   * Get Values from a query - Select Get Values from a query to retrieve the default value or set of default values from a data source. If you select Get Values from a query, two fields appear in which you define query information.

   * Dataset - Appears only when Get Values from a query is selected. Select a dataset from which to retrieve a default value or a set of default values for the parameter. You define datasets using the Data view. For more information, see Defining Report Datasets.

   * Value field - Appears only when Get Values from a query is selected. Select a field from which to obtain the default value or set of default values. The available fields are retrieved from a list of column or field names in the dataset. The value from the first row in the dataset is used for the default value.

   ![](Add-Parameter_images/Add-Parameter_img7.png)
   
7. Click OK.

8. To delete a report parameter, Right-click the report parameter and click Delete. 

   ![](Add-Parameter_images/Add-Parameter_img8.png)