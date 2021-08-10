---
layout: post
title: UI Automation in WPF DataGrid control | Syncfusion
description: Learn here all about UI Automation support in Syncfusion WPF DataGrid (SfDataGrid) control and more.
platform: wpf
control: SfDataGrid
documentation: ug
---

# UI Automation in WPF DataGrid (SfDataGrid)

Microsoft UI Automation is the new accessibility Framework for Microsoft Windows, available on all operating systems that support Windows Presentation Foundation (WPF). UI Automation provides accessibility to most UI elements and it provides the information about UI element to the end user. You can interact with the UI by using automated test scripts. To know more about UI Automation, refer the MSDN page [here](https://docs.microsoft.com/en-us/dotnet/framework/ui-automation/ui-automation-overview).

SfDataGrid supports the following types of UI Automation,

1. Coded UI
2. Quick Test Professional

## Coded UI Test


Automated tests that drive your application through its user interface (UI) are known as Coded UI Tests (CUITs). These tests include functional testing of the UI controls. SfDataGrid supports CUITs Coded UI automation that helps you create automated tests for inner elements and records the sequence of actions. While dragging the crosshair that is shown in CodedUITestBuilder, on UI elements, it shows the properties of the respective UI elements and you can also add assertion for each of the properties.

[SfDataPager](https://help.syncfusion.com/wpf/datapager/overview) and [SfMultiColumnDropDownControl](https://help.syncfusion.com/wpf/multi-column-dropdown/getting-started) support `Coded UI` Test automation.

Provided here are three levels of support in Coded UI Test automation.

`Coded UI Test`

<table>
<tr>
<th>
Levels</th><th>
Description</th></tr>
<tr>
<td>
Level – 1</td><td>
Record and Detect the UI Elements when you perform any actions in the Control.</td></tr>
<tr>
<td>
Level – 2</td><td>
Provide custom properties for UI elements when you drag the Crosshair to any UI element.</td></tr>
<tr>
<td>
Level – 3</td><td>
Coded UI Test Builder generates code from recorded session and custom class is implemented to access custom properties, so the generated code is simplified.</td></tr>
</table>

### Requirements and Configuration

Coded UI provides support only in Visual Studio Ultimate and Visual Studio Premium. For more information about the platforms and configurations that are supported by Coded UI tests, refer this [link](https://docs.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2015/test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings?view=vs-2015&redirectedfrom=MSDN).

To test SfDataGrid with CUITs, build the Extension Project and place it in the mentioned location. You can get the Extension Project of SfDataGrid from [this](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Src-229533545.zip) location.

1. Open the Extension Project and build it.
2. You can get the `Syncfusion.VisualStudio.TestTools.UITest.SfGridExtension.dll` from bin folder. 

The above assembly must be placed into the following directory based on your Visual Studio version.

For `Visual Studio 2010` : C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages

For `Visual Studio 2012` : C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\11.0\UITestExtensionPackages

For `Visual Studio 2013` : C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\12.0\UITestExtensionPackages

N> `Syncfusion.VisualStudio.TestTools.UITest.SfGridExtension.dll` need to be installed in GAC location. Please refer the MSDN link for  [GAC](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-2.0/ex0ss12c(v=vs.80))  installation.

### Getting Started

This topic shows you how to create a CodedUITest project and test the SfDataGrid application. 

1. Create a new WPF application or open an existing WPF application with SfDataGrid and enable Coded UI Test in SfDataGrid. To enable CUITs, you need to set [AutomationPeerHelper.EnableCodedUI](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutomationPeerHelper.html#Syncfusion_UI_Xaml_Grid_AutomationPeerHelper_EnableCodedUI) as `True` and access the [AutomationPeerHelper](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.AutomationPeerHelper.html) class from [Syncfusion.UI.Xaml.Grid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.html) namespace as shown in the following code example,


{% tabs %}
{% highlight c# %}

using Syncfusion.UI.Xaml.Grid;

public MainWindow()
{
	 InitializeComponent();
	 AutomationPeerHelper.EnableCodedUI = true;
}

{% endhighlight %}
{% endtabs %}

2. Build the application and launch the .exe file from the bin folder.          
3. Create a Coded UI Test Project as shown in the following screenshot.               



   ![Choose the coded ui test project from visual studio](Features_images/Features_img223.png)



   Add New Project
   {:.caption}
4. After you create a new Coded UI project, a CUIT file is added automatically and the Generate Code dialog box appears. In this, choose Record actions, edit UI map or add assertions.

   ![Choose the type of coded ui test  from visual studio](Features_images/Features_img224.png)



   Generate Code for Coded UI Test
   {:.caption}
5. Now the Coded UI project Visual Studio gets minimized and CodedUITestBuilder appears in the bottom right corner of your window. You can record the actions by clicking Start Recording in CodedUITestBuilder.



   ![Genarate the coded ui test files by using the CodedUITestBuilder](Features_images/Features_img225.png)



   CodedUITestBuilder
   {:.caption}
6. You can also open the CodedUITestBuilder from existing Coded UI project by right clicking on the CodedUITestMethod1 in CUIT file and clicking the Generate Code For Coded UI Test as shown in the following screenshot. You can see the same CodedUITestBuilder in the bottom right corner of the window.

   ![UI Automation in SfDataGrid WPF](Features_images/Features_img226.png)



   CodedUITestMethod
   {:.caption}
7. Now you can drag the Crosshairs on to the UI elements of your WPF SfDataGrid application and it shows the available properties of the inner UI elements in SfDataGrid.
8. You can record the actions made on UI elements by clicking Record button on the CodedUITest builder. For example you can record the action of changing the cell value in SfDataGrid. Click the Pause button to finish the record.



   ![Record the coded ui test actions by using the CodedUITest builder](Features_images/Features_img227.png)



   CodedUITest
   {:.caption}
9. Once the record is completed, click the GenerateCode icon in CodedUITestBuilder for generate a test method. Then close the CodedUITestBuilder and you can see the generated code for cell value changed action as follows.

{% tabs %}
{% highlight c# %}

public void RecordedMethod1()
{
    #region Variable Declarations
    WpfText uIMEREPText = this.UIWpfWindow.UISfDataGridCustom.UIGridCellCustom4.UIMEREPText;
    WpfEdit uIGridCellEdit = this.UIWpfWindow.UISfDataGridCustom.UIGridCellEdit;
	WpfSfGridCell uIGridCellCustom11 = this.UIWpfWindow.UISfDataGridCustom.UIGridCellCustom11;
	WpfSfGridCell uIGridCellCustom12 = this.UIWpfWindow.UISfDataGridCustom.UIGridCellCustom12;
	#endregion

}

{% endhighlight %}
{% endtabs %}

10. You can also create an assertion to check the modified cell value. Drag the crosshair to the modified cell, and the Assertion window appears. The properties for control (Cell) is now listed in the Assertion dialog box. You can add assertion by clicking the Generate Code button in CodedUITestBuilder.

    ![SfDataGrid UI Automation with adding the assertion](Features_images/Features_img228.png)



    Assertion window
    {:.caption}
11. After all tests and assertion are created, right-click on the Test method and click Run Tests to run the test as follows.

    ![Run the SfDataGrid coded ui test](Features_images/Features_img229.png)



    Run Test
	{:.caption}

### Tables for Properties 

The following properties are for each of the UI elements in SfDataGrid.

<table>
<tr>
<th>
UI Elements</th><th>
Properties</th></tr>
<tr>
<td>
DataGrid</td><td>
RowCountColumnCount SelectionMode SelectionUnit SelectedIndex SelectedItemCount</td></tr>
<tr>
<td>
GridCell</td><td>
CellValue FormattedValue RowIndex ColumnIndex ColumnName</td></tr>
<tr>
<td>
GridHeaderCellControl</td><td>
MappingName IsFilterApplied FilterIconVisibility SortDirection SortNumberVisibility</td></tr>
<tr>
<td>
GridRowHeaderCell</td><td>
RowErrorMessage RowIndexState</td></tr>
<tr>
<td>
GroupDropArea</td><td>
IsExpanded GroupDropAreaText</td></tr>
<tr>
<td>
DetailsViewDataGrid</td><td>
RowCountColumnCount SelectionMode SelectionUnit SelectedIndex SelectedItemCount</td></tr>
<tr>
<td>
GroupDropAreaItem</td><td>
GroupName SortDirection</td></tr>
<tr>
<td>
GridStackedHeaderCellControl</td><td>
      Default Properties </td></tr>
<tr>
<td>
GridTableSummaryCell</td><td>
      Default Properties</td></tr>
<tr>
<td>
GridGroupSummaryCell</td><td>
      Default Properties</td></tr>
<tr>
<td>
GridCaptionSummaryCell</td><td>
      Default Properties</td></tr>
<tr>
<td>
GridDetailsViewExpanderCellControl</td><td>
      Default Properties</td></tr>
<tr>
<td>
GridIndentCell</td><td>
      Default Properties</td></tr>
</table>


The following properties are for each of the UI elements in `SfMultiColumnDropDownControl`.

<table>
<tr>
<th>
UI Elements</th><th>
Properties</th></tr>
<tr>
<td>
SfMultiColumnDropDownControl</td><td>
AllowAutoComplete AllowNullInput AllowImmediatePopup AllowIncrementalFiltering AllowCaseSensitiveFiltering AllowSpinOnMouseWheel DisplayMember IsDropDownOpen SelectedIndex ValueMember</td></tr>
</table>


The following properties are for each of the UI elements in `SfDataPager`.

<table>
<tr>
<th>
UI Elements</th><th>
Properties</th></tr>
<tr>
<td>
SfDataPager</td><td>
AccentBackground AccentForeground AutoEllipsisMode AutoEllipsisText DisplayMode EnableGridPaging NumericButtonCount Orientation PageCount PageSize UseOnDemandPaging</td></tr>
</table>

### Limitations

*  SfDataGrid UI Automation will not work when you automate the datagrid with editing in Visual Studio 2015. It is a known issue in Visual Studio 2015.

### How To

### How to Enable Coded UI Test in SfDataGrid

To enable Coded UI Test in SfDataGrid, set `AutomationPeerHelper.EnableCodedUI` as `True`. You can use the `AutomationPeerHelper` class from `Syncfusion.UI.Xaml.Grid` namespace.

{% tabs %}
{% highlight C# %}
using Syncfusion.UI.Xaml.Grid;

public MainWindow()
{
    InitializeComponent();
    AutomationPeerHelper.EnableCodedUI = true;
}
{% endhighlight %}
{% endtabs %}

## Quick Test Professional (QTP)

You can refer the UFT/QTP document from [here](https://help.syncfusion.com/wpf/testing/uft)
