---
layout: post
title: Grid-Localization-Support in WPF Wizard Control control | Syncfusion
description: Learn here all about Grid-Localization-Support support in Syncfusion WPF GridDataControl (Classic) control and more.
platform: wpf
control: GridData (Classic)
documentation: ug
---
# Grid-Localization-Support in WPF GridDataControl (Classic)

Localization is the process of making your application multi-lingual, by formatting content according to cultures. This involves configuring the application for a specific language. Culture is the combination of language and the location (e.g. En-US is the culture for English spoken in  United States; En-GB is the culture for English spoken in  Great Britain). Syncfusion Grid allows you to set custom resource through the Resx file. The user can simply give the string values in the resource file for a specific culture and set the culture in the application. The given string values are set to the Grid that does not affect the Code Block of the Grid

## Adding Localization to an Application 

The following steps explain the implementation of Localization support in applications.

### Creating an Application

Create a WPF application and add GridDataControl to it. 

### Creating a Resource File

To create a Resource file:

1. Create a folder named “Resources” in the application. 
2. Create a resource file (Resx file) and name it “Syncfusion.Grid.Wpf.<your culture info name>.resx” E.g. Syncfusion.Grid.Wpf.en-GB.resx. 
3. Use the prescribed naming convention as it is mandatory. 
4. The following screenshot explains the addition of a Resource File to the application. 

   ![Getting-Started_images159](Getting-Started_images/Getting-Started_img159.png)

5. Select the String option in the Resource file. This is explained in the following screenshot.

   ![StringSelection](Getting-Started_images/Getting-Started_img160.png)

6. Enter the “Name” and “Value” in the Resource file. 

   The String Property names used in the Grid are given in the Property table. This is explained in the following screenshot.

   ![Getting-Started_images161](Getting-Started_images/Getting-Started_img161.png)

   
### Setting the Culture Information in the Application

The culture information should be set in the application before the InitializeComponent() method is called. Now, the application is set to Britain English Culture info. The following code snippet explains the implementation of this.


{% highlight c# %}

public MainWindow()

{

	System.Threading.Thread.CurrentThread.CurrentUICulture = new               System.Globalization.CultureInfo("en-GB");



	InitializeComponent();

}

{% endhighlight %}

### Properties

Localization Property Table

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
AllowDrag</td><td>
Sets the string for AllowDrag property</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AllowDrag</td><td>
Sets the string for AllowDrag</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AllowGroup</td><td>
Sets the string for AllowGroup</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AllowResize</td><td>
Sets the string for AllowResize</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AllowSort</td><td>
Sets the string for  AllowSort</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AND</td><td>
Sets the string for AND</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
ApplyWidthSettings</td><td>
Sets the string for ApplyWidthSettings</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
AutoFit</td><td>
Sets the string for AutoFit</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
CanntPerformSortMessage</td><td>
Sets the string for CanntPerformSortMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
ClipboardCopyPaste</td><td>
Sets the string for ClipboardCopyPaste</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
ColumnFormat</td><td>
Sets the string for ColumnFormat</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
ConfirmDeleteMessage</td><td>
Sets the string for ConfirmDeleteMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Contains</td><td>
Sets the string for Contains</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
CurrentPageText</td><td>
Sets the string for CurrentPageText</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
DeleteMessage</td><td>
Sets the string for DeleteMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
DragDropText</td><td>
Sets the string for DragDropText</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
DynamicOptions</td><td>
Sets the string for DynamicOptions</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
EndsWith</td><td>
Sets the string for EndsWith</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
EnterFilterValue</td><td>
Sets the string for EnterFilterValue</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Equals</td><td>
Sets the string for Equals</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
First</td><td>
Sets the string for First</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
GreaterThan</td><td>
Sets the string for GreaterThan</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
GreaterThanOrEqual</td><td>
Sets the string for GreaterThanOrEqual</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
HCenter</td><td>
Sets the string for HCenter</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
HeaderText</td><td>
Sets the string for HeaderText</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
HLeft</td><td>
Sets the string for HLeft</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Horizontal</td><td>
Sets the string for Horizontal</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
HRight</td><td>
Sets the string for HRight</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
HStretch</td><td>
Sets the string for HStretch</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
InvalidColumn</td><td>
Sets the string for InvalidColumn</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
InvalidDataTime</td><td>
Sets the string for InvalidDataTime</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
InvalidDataToFilter</td><td>
Sets the string for InvalidDataToFilter</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
IsReadOnly</td><td>
Sets the string for IsReadOnly</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Last</td><td>
Sets the string for Last</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
LessThan</td><td>
Sets the string for LessThan</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
LessThanOrEqual</td><td>
Sets the string for LessThanOrEqual</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
MatchCase</td><td>
Sets the string for MatchCase</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Next</td><td>
Sets the string for Next</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
NoMoreItemRemoveMessage</td><td>
Sets the string for NoMoreItemRemoveMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
None</td><td>
Sets the string for None</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
NoRecordsfound</td><td>
Sets the string for NoRecordsfound</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
NotEnoughSpaceMessage</td><td>
Sets the string for NotEnoughSpaceMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
NotEquals</td><td>
Sets the string for NotEquals</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
NotSupportDeletingItemMessage</td><td>
Sets the string for  NotSupportDeletingItemMessage</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
OR</td><td>
Sets the string for OR</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
PageSizes</td><td>
Sets the string for PageSizes</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Previous</td><td>
Sets the string for Previous</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
PrintOutputColor</td><td>
Sets the string for PrintOutputColor</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
PrintText</td><td>
Sets the string for PrintText</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
PrintZoom</td><td>
Sets the string for PrintZoom</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
SelectAllFilter</td><td>
Sets the string for SelectAllFilter</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
StartsWith</td><td>
Sets the string for StartsWith</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
TextAlignment</td><td>
Sets the string for TextAlignment</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
VBottom</td><td>
Sets the string for VBottom</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
VCenter</td><td>
Sets the string for VCenter</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Vertical</td><td>
Sets the string for Vertical</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
VStretch</td><td>
Sets the string for VStretch</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
VTop</td><td>
Sets the string for VTop</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
Width</td><td>
Sets the string for Width</td><td>
static</td><td>
string</td></tr>
<tr>
<td>
WidthOptions</td><td>
Sets the string for WidthOptions</td><td>
static</td><td>
string</td></tr>
</table>


#### Sample Link

Refer to the sample in the shipped Sample Browser: 

Essential Studio - WPF Sample Browser - Grid -  LocalizationSupport - LocalizationDemo.
