---
layout: post
title: Localization Support 
description: Localization support
platform: wpf
control: OLAP Client
 documentation: ug
---

# Localization Support

Localization is the key feature for providing software solutions targeted at global users. Essential BI OLAP client for WPF allows users to localize the control to a specific locale. The following document briefly explains the step by step procedure to localize an OLAP client for the WPF control.


![](Localization-Support_images/Localization-Support_img1.png)



### Localizing the OLAP client in an application

The OLAP client for WPF supports “resx” based localization. The following steps should be performed to localize the control.

* Translation.
* Resource file and file name conventions.
* <SupportedCultures> tag inclusion into the project file.
* Specifying the CurrentUICulture.

{% seealso %}

Getting Started

{% endseealso %}

### Translation

The first step in localization is translating the strings that can be localized to the destination locale. Basically, OlapClient.WPF contains control assemblies such as OlapChart.WPF and OlapGrid.WPF and tools assemblies such as OlapShared.WPF and OlapTools.WPF within it. So, it is mandatory to localize those assemblies. The following tables contain the localization keys and strings to be localized for OlapClient.WPF, OlapChart.WPF, OlapGrid.WPF, OlapShared.WPF, and OlapTools.WPF assemblies. Translate the second column in each table, which contains the strings to be localized to the target locale.

N> Localization key field should be same for all locales. Do not translate it.

### Localization strings table for OlapClient.WPF


<table>
<tr>
<th>
Localization Key</th><th>
Strings to be localized</th></tr>
<tr>
<td>
OlapClient_ChartTabHeader</td><td>
Chart</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ChartColorPalette_ToolTip</td><td>
Chart Color Palette</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ChartTypes_ToolTip</td><td>
Chart Types</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_Export_ToolTip</td><td>
Exports Chart as an Image</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ExportPdf_ToolTip</td><td>
Export to PDF</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ExportWord_ToolTip</td><td>
Export to Word</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_Print_ToolTip</td><td>
Print Chart</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_PrintMode_ToolTip</td><td>
Print Mode</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ShowAppearanceDialog_ToolTip</td><td>
Show Chart Appearance Dialog</td></tr>
<tr>
<td>
OlapClient_ChartToolbar_ShowLegend_ToolTip</td><td>
Show Legend</td></tr>
<tr>
<td>
OlapClient_ColumnAxis_HeaderText</td><td>
Columns (Categorical)</td></tr>
<tr>
<td>
OlapClient_ColumnRowSubsetFilter_ToolTip</td><td>
Subset Filter</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Browse</td><td>
Browse</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Connection_String_Header</td><td>
Connection String</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Credential</td><td>
Credential</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Data_Source_Header</td><td>
Data source</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_DatabaseName</td><td>
Database Name:</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_EnterCredential_Header</td><td>
Enter credentials</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Header</td><td>
Server options</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Offline_Cube_Header</td><td>
Offline Cube</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Ok</td><td>
OK</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Password</td><td>
Password:</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_Server_Header</td><td>
Server</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_ServerName</td><td>
Server Name:</td></tr>
<tr>
<td>
OlapClient_Connect_Dlg_User_Name</td><td>
User Name:</td></tr>
<tr>
<td>
OlapClient_ConnectOptions_Dlg_Title</td><td>
Connection Option</td></tr>
<tr>
<td>
OlapClient_CubeDimensionBrowser_HeaderText</td><td>
MetaTree</td></tr>
<tr>
<td>
OlapClient_CubeSelector_HeaderText</td><td>
Cubes</td></tr>
<tr>
<td>
OlapClient_CubeSelector_ToolTip</td><td>
Cube Selector</td></tr>
<tr>
<td>
OlapClient_GridTabHeader</td><td>
Grid</td></tr>
<tr>
<td>
OlapClient_GridToolbar_ExportExcel_ToolTip</td><td>
Export to Excel</td></tr>
<tr>
<td>
OlapClient_GridToolbar_ExportPdf_ToolTip</td><td>
Export to PDF</td></tr>
<tr>
<td>
OlapClient_GridToolbar_ExportWord_ToolTip</td><td>
Export to Word</td></tr>
<tr>
<td>
OlapClient_GridToolbar_FreezeHeaders_ToolTip</td><td>
Freeze Headers</td></tr>
<tr>
<td>
OlapClient_GridToolbar_GridLayout_ToolTip</td><td>
Grid Layouts</td></tr>
<tr>
<td>
OlapClient_GridToolbar_GridStyleDialog_ToolTip</td><td>
Show Grid Style Dialog</td></tr>
<tr>
<td>
OlapClient_GridToolbar_HeaderCellTooltip_ToolTip</td><td>
Show Header Cell Tooltip</td></tr>
<tr>
<td>
OlapClient_GridToolbar_ValueCellTooltip_ToolTip</td><td>
Show Value Cell ToolTip</td></tr>
<tr>
<td>
OlapClient_ReportName_Dlg_ReportName</td><td>
Report Name</td></tr>
<tr>
<td>
OlapClient_RowAxis_HeaderText</td><td>
Rows (Series)</td></tr>
<tr>
<td>
OlapClient_SlicerAxis_HeaderText</td><td>
Slicer</td></tr>
<tr>
<td>
OlapClient_TogglePivot_ToolTip</td><td>
Toggle Pivot</td></tr>
<tr>
<td>
OlapClient_Toolbar_AddReport_ToolTip</td><td>
Add Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_ColumnFilter_ToolTip</td><td>
Column Filter</td></tr>
<tr>
<td>
OlapClient_Toolbar_ConnectionOption_ToolTip</td><td>
Connect to Server</td></tr>
<tr>
<td>
OlapClient_Toolbar_LoadReport_ToolTip</td><td>
Load Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_NewReport_ToolTip</td><td>
New Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_RemoveReport_ToolTip</td><td>
Remove Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_RenameReport_ToolTip</td><td>
Rename Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_ReportList_ToolTip</td><td>
Report List</td></tr>
<tr>
<td>
OlapClient_Toolbar_RowFilter_ToolTip</td><td>
Row Filter</td></tr>
<tr>
<td>
OlapClient_Toolbar_SaveAsReport_ToolTip</td><td>
Save As Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_SaveReport_ToolTip</td><td>
Save Report</td></tr>
<tr>
<td>
OlapClient_Toolbar_ShowExpanders_ToolTip</td><td>
Show Expanders</td></tr>
<tr>
<td>
OlapClient_Toolbar_SortingColumn_ToolTip</td><td>
Sorting Column</td></tr>
<tr>
<td>
OlapClient_Toolbar_SortingRow_ToolTip</td><td>
Sorting Row</td></tr>
</table>

### Localization strings table for OlapChart.WPF

<table>
<tr>
<th>
Localization key</th><th>
Strings to be localized</th></tr>
<tr>
<td>
OlapChart_Dialog_Appearance_Tab</td><td>
Appearance</td></tr>
<tr>
<td>
OlapChart_Dialog_Axis_Tab</td><td>
Axis Labels</td></tr>
<tr>
<td>
OlapChart_Dialog_AxisLabel_FontColor</td><td>
Font Color</td></tr>
<tr>
<td>
OlapChart_Dialog_AxisLabel_FontFace</td><td>
Font Face</td></tr>
<tr>
<td>
OlapChart_Dialog_AxisLabel_FontStyle</td><td>
Font Style</td></tr>
<tr>
<td>
OlapChart_Dialog_BackgroundStyle_Header</td><td>
Background Style</td></tr>
<tr>
<td>
OlapChart_Dialog_BorderColor</td><td>
Color:</td></tr>
<tr>
<td>
OlapChart_Dialog_BorderStyle_Header</td><td>
Border Style</td></tr>
<tr>
<td>
OlapChart_Dialog_BorderWidth</td><td>
Width:</td></tr>
<tr>
<td>
OlapChart_Dialog_CancelButton</td><td>
Cancel</td></tr>
<tr>
<td>
OlapChart_Dialog_Chart_Tab</td><td>
Chart</td></tr>
<tr>
<td>
OlapChart_Dialog_ChartBackground</td><td>
Chart Control:</td></tr>
<tr>
<td>
OlapChart_Dialog_ChartInterior</td><td>
Chart Interior:</td></tr>
<tr>
<td>
OlapChart_Dialog_ChartPalette</td><td>
Chart Palette:</td></tr>
<tr>
<td>
OlapChart_Dialog_ChartStyle_Header</td><td>
Chart Style</td></tr>
<tr>
<td>
OlapChart_Dialog_ChartType</td><td>
Chart Type:</td></tr>
<tr>
<td>
OlapChart_Dialog_CircleAsSymbol</td><td>
Circle</td></tr>
<tr>
<td>
OlapChart_Dialog_LabelVisibility_Header</td><td>
Label Visibility</td></tr>
<tr>
<td>
OlapChart_Dialog_LegendCheckBoxVisibility</td><td>
Show CheckBox</td></tr>
<tr>
<td>
OlapChart_Dialog_LegendPosition</td><td>
Position:</td></tr>
<tr>
<td>
OlapChart_Dialog_Legends_Header</td><td>
Legends</td></tr>
<tr>
<td>
OlapChart_Dialog_LegendVisibility</td><td>
Show Legend</td></tr>
<tr>
<td>
OlapChart_Dialog_OkButton</td><td>
OK</td></tr>
<tr>
<td>
OlapChart_Dialog_Point_Labels_Tab</td><td>
Point Labels</td></tr>
<tr>
<td>
OlapChart_Dialog_RectangleAsSymbol</td><td>
Rectangle</td></tr>
<tr>
<td>
OlapChart_Dialog_SeriesNameAsLabelContent</td><td>
Series Name</td></tr>
<tr>
<td>
OlapChart_Dialog_SymbolVisibility_Header</td><td>
Symbol Visibility</td></tr>
<tr>
<td>
OlapChart_Dialog_Title</td><td>
Chart Appearance Dialog</td></tr>
<tr>
<td>
OlapChart_Dialog_TriangleAsSymbol</td><td>
Triangle</td></tr>
<tr>
<td>
OlapChart_Dialog_XAxis_Header</td><td>
X Axis</td></tr>
<tr>
<td>
OlapChart_Dialog_XValueAsLabelContent</td><td>
X Value</td></tr>
<tr>
<td>
OlapChart_Dialog_YAxis_Header</td><td>
Y Axis</td></tr>
<tr>
<td>
OlapChart_Dialog_YValueAsLabelContent</td><td>
Y Value</td></tr>
</table>

### Localization strings table for OlapGrid.WPF

<table>
<tr>
<th>
Localization key</th><th>
Strings to be localized</th></tr>
<tr>
<td>
OlapGrid_Column_Tooltip</td><td>
Columns :</td></tr>
<tr>
<td>
OlapGrid_Dialog_Background_Color</td><td>
Background Color</td></tr>
<tr>
<td>
OlapGrid_Dialog_Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
OlapGrid_Dialog_CellStyles</td><td>
Cell Styles</td></tr>
<tr>
<td>
OlapGrid_Dialog_ColumnHeader</td><td>
Column Header</td></tr>
<tr>
<td>
OlapGrid_Dialog_ColumnSummary</td><td>
Column Summary</td></tr>
<tr>
<td>
OlapGrid_Dialog_Font_Color</td><td>
Font Color</td></tr>
<tr>
<td>
OlapGrid_Dialog_Font_Name</td><td>
Font Name</td></tr>
<tr>
<td>
OlapGrid_Dialog_Font_Size</td><td>
Font Size</td></tr>
<tr>
<td>
OlapGrid_Dialog_Font_Style</td><td>
Font Style</td></tr>
<tr>
<td>
OlapGrid_Dialog_Foreground_Color</td><td>
Foreground Color</td></tr>
<tr>
<td>
OlapGrid_Dialog_HeaderFont</td><td>
Header Font</td></tr>
<tr>
<td>
OlapGrid_Dialog_HeaderStyle</td><td>
Header Style</td></tr>
<tr>
<td>
OlapGrid_Dialog_Ok</td><td>
OK</td></tr>
<tr>
<td>
OlapGrid_Dialog_RowHeader</td><td>
Row Header</td></tr>
<tr>
<td>
OlapGrid_Dialog_RowSummary</td><td>
Row Summary</td></tr>
<tr>
<td>
OlapGrid_Dialog_SummaryFont</td><td>
Summary Font</td></tr>
<tr>
<td>
OlapGrid_Dialog_SummaryStyle</td><td>
Summary Style</td></tr>
<tr>
<td>
OlapGrid_Dialog_Title</td><td>
Apply Style</td></tr>
<tr>
<td>
OlapGrid_Measure_Tooltip</td><td>
Measure :</td></tr>
<tr>
<td>
OlapGrid_Row_Tooltip</td><td>
Rows:</td></tr>
<tr>
<td>
OlapGrid_Value_Tooltip</td><td>
Values :</td></tr>
</table>

### Localization strings table for OlapShared.WPF

<table>
<tr>
<th>
Localization key</th><th>
Strings to be localized</th></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_EmptyResult_Header</td><td>
Empty Results</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Filter_Tab</td><td>
Filter</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Filter1_Header</td><td>
Filter 1</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Filter2_Header</td><td>
Filter 2</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_FilterEmptyColumns</td><td>
Filter Empty Columns</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_FilterEmptyRows</td><td>
Filter Empty Rows</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_FilterOn</td><td>
Filter On</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_FilterOnValue</td><td>
Value</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Header</td><td>
Filtering and Sorting</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_OnColumn</td><td>
On Column</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_OnRow</td><td>
On Row</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Sort_Header</td><td>
Sort</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Sort_Preserver_Hierarchy</td><td>
Preserve Hierarchy</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_SortAsc</td><td>
Ascending</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_SortDesc</td><td>
Descending</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Sorting_Tab</td><td>
Sorting</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_SortingOn</td><td>
Sorting On</td></tr>
<tr>
<td>
OlapTools_FilterSorting_Dlg_Update</td><td>
Update</td></tr>
<tr>
<td>
OlapTools_FilterSorting_FilterCondition</td><td>
Condition</td></tr>
</table>

### Localization strings table for OlapTools.WPF

<table>
<tr>
<td>
Localization key</td><td>
Strings to be localized</td></tr>
<tr>
<td>
OlapTools_Editor_Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
OlapTools_Editor_Ok</td><td>
OK</td></tr>
<tr>
<td>
OlapTools_Editor_SplitButton_Delete_ToolTip</td><td>
Delete</td></tr>
<tr>
<td>
OlapTools_Editor_SplitButton_MoveDown_ToolTip</td><td>
Move Down</td></tr>
<tr>
<td>
OlapTools_Editor_SplitButton_MoveUp_ToolTip</td><td>
Move Up</td></tr>
<tr>
<td>
OlapTools_MeasureEditor_Remove_ContextMenu</td><td>
Remove</td></tr>
<tr>
<td>
OlapTools_MeasureEditor_Title</td><td>
Measure Editor</td></tr>
<tr>
<td>
OlapTools_MemberEditor_CheckAll_UnCheckAll</td><td>
Check / UnCheck All</td></tr>
<tr>
<td>
OlapTools_MemberEditor_Title</td><td>
Member Editor</td></tr>
<tr>
<td>
OlapTools_SubsetFilter_DropDown_Text</td><td>
Max number of records to be displayed.</td></tr>
</table>


## Resource file and file name conventions

After translating the strings that can be localized, perform the following in the application:

1. Right-click the project file to create a new folder in the project.
2. Select Add > New Folder.
3. Rename the folder as Resources.



N> The folder name should strictly be Resources.



4. Now, right-click the Resources folder to create a new resource file in the Visual Studio project file.
5. Navigate to Add > New Item.



   ![](Localization-Support_images/Localization-Support_img2.png)



The Add New Item dialog displays as follows.

   ![](Localization-Support_images/Localization-Support_img3.png)



6. Select resources file from the list. Name the resource file: Syncfusion.OlapClient.WPF.fr-FR.resx and then click Add.



   N> The resource file name should strictly be in the format  “Syncfusion.OlapClient.WPF.<<Culture Code>>.resx”.

   ## Examples

   * Syncfusion.OlapClient.WPF.es.resx
   * Syncfusion.OlapClient.WPF.ja-JP.resx
   * Syncfusion.OlapClient.WPF.it-IT.resx

   Similarly, for OlapChart.WPF assembly, add one more new resource file. Name the resource file as Syncfusion.OlapChart.WPF.fr-FR.resx.

   For OlapGrid.WPF assembly, add one more new resource file. Name the resource file as Syncfusion.OlapGrid.WPF.fr-FR.resx.

   For OlapShared.WPF assembly, add one more new resource file. Name the resource file as Syncfusion.OlapShared.WPF.fr-FR.resx.

   For OlapTools.WPF assembly, add one more new resource file. Name the resource file as Syncfusion.OlapTools.WPF.fr-FR.resx.

   Now, the new resource file is included successfully.

8. Copy and paste the translated locale to the resource file created in the earlier step.

   ![](Localization-Support_images/Localization-Support_img4.png)

   

## &lt;SupportedCultures&gt; Tag inclusion into the project file

In Silverlight, you should specify the list of supported cultures using the <SupportedCultures> tag in the project file. To specify the supported cultures in a project file, perform the following steps:

1. Go to Solution Explorer, right-click the project file and select Unload.
2. Again, right-click the project file and select Edit. Now, the project files will appear in the XML editor in Visual Studio.
3. Find the tag <SupportedCultures>, and then specify the culture code, which is already appended in the resource file name.

   Example: <SupportedCultures>fr-FR<SupportedCultures>

   You can specify multiple cultures by using the (;) semicolon operator to separate the culture codes.

   Example:<SupportedCultures>en-US;fr;fr-FR;ru;ru-RU;</SupportedCultures>

4. Now, right-click the project name and select Reload.

   
Now, the supported cultures are included in the project file.

## Specifying the CurrentUICulture

Now, you should specify the CurrentUICulture of the application. You can specify the CurrentUICulture either from Application_Startup in App.xaml.cs or from the constructor on the MainPage (If you are specifying the current culture on the main page, then make sure, this is assigned before calling the InitializeComponent method). The following code snippets describe the two variations.

{% tabs %}
{% highlight C# %} 
 




public MainPage() 

{ 

     System.Threading.Thread.CurrentThread.CurrentCulture =

     new System.Globalization.CultureInfo("fr-FR"); 



     System.Threading.Thread.CurrentThread.CurrentUICulture =

     new System.Globalization.CultureInfo("fr-FR"); 



     InitializeComponent(); 

} 

 {% endhighlight %}



{% highlight vbnet %}  



Public Sub New()

System.Threading.Thread.CurrentThread.CurrentCulture = New System.Globalization.CultureInfo("fr-FR")



System.Threading.Thread.CurrentThread.CurrentUICulture = New System.Globalization.CultureInfo("fr-FR")



InitializeComponent()

End Sub

{% endhighlight %}
{% endtabs %}


{% tabs %}

{% highlight C# %} 
 




private void Application_Startup(object sender, StartupEventArgs e) 

{ 

    System.Threading.Thread.CurrentThread.CurrentUICulture = 

    new System.Globalization.CultureInfo("fr-FR"); 



    System.Threading.Thread.CurrentThread.CurrentUICulture = 

    new System.Globalization.CultureInfo("fr-FR"); 



    this.RootVisual = new MainPage(); 

} 

{% endhighlight %}



{% highlight vbnet %}  



Private Sub Application_Startup(ByVal sender As Object, ByVal e As StartupEventArgs)

System.Threading.Thread.CurrentThread.CurrentUICulture = New System.Globalization.CultureInfo("fr-FR")



System.Threading.Thread.CurrentThread.CurrentUICulture = New System.Globalization.CultureInfo("fr-FR")



Me.RootVisual = New MainPage()

End Sub

{% endhighlight %}
{% endtabs %}
