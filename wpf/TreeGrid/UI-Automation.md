---
layout: post
title: UI Automation in WPF TreeGrid control | Syncfusion
description: Learn here all about UI Automation support in Syncfusion WPF TreeGrid (SfTreeGrid) control and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# UI Automation in WPF TreeGrid (SfTreeGrid)

### Requirements and configuration

To test SfTreeGrid control with CUITs, build the extension project and place it in the mentioned location. You can get the extension project from the following location.

<table>
<tr>
<td>
{{'**SfTreeGrid**'| markdownify }}
</td>
<td>
https://github.com/SyncfusionExamples/coded-ui-extension-project-for-wpf-treegrid
</td>
</tr>
</table>

1. Open the extension project and build it.
2. Get the following tabulated assembly from the bin folder.

<table>
<tr>
<td>
{{'**SfGrid.WPF**'| markdownify }}
</td>
<td>
Syncfusion.VisualStudio.TestTools.UITest.SfGridExtension.dll
</td>
</tr>
</table>

The SfGridExtension assembly must be placed into the following directory based on your Visual Studio version.
For Visual Studio 2010: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages

For Visual Studio 2012: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\11.0\UITestExtensionPackages

For Visual Studio 2013: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\13.0\UITestExtensionPackages

For Visual Studio 2015: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\14.0\UITestExtensionPackages

For Visual Studio 2017: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\15.0\UITestExtensionPackages

N> Syncfusion.VisualStudio.TestTools.UITest.SfGridExtension.dll needs to be installed in GAC location. Please refer to the MSDN link for [GAC](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-2.0/ex0ss12c(v=vs.80)) installation.

### Steps to work with Coded UI

This section explains how to create a CodedUITest project and test the tree grid application.

1. Create a new WPF application or open an existing WPF application with tree grid and enable the Coded UI test in tree grid. To enable CUITs, set AutomationPeerHelper.EnableCodedUI to true and access the AutomationPeerHelper class from Syncfusion.UI.Xaml.Grid namespace as demonstrated in the following code sample.

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
3. Create a Coded UI test project as shown in the following screenshot.

   ![Coded UI Test Project](UIAutomation_images/UIAutomation_img1.png)



   Add New Project
   {:.caption}

4. After created a new Coded UI project, a CUIT file is added automatically, and the Generate Code dialog box appears. In this, choose Record actions, edit UI map, or add assertions.

   ![Generate Code dialog box](UIAutomation_images/UIAutomation_img2.png)



   Generate Code for Coded UI Test
   {:.caption}

5. Now, minimize the Coded UI project Visual Studio, and CodedUITestBuilder appears in the bottom-right corner of your window. You can record the actions by clicking the Start Recording in CodedUITestBuilder.



   ![CodedUITestBuilder](UIAutomation_images/UIAutomation_img3.png)



   CodedUITestBuilder
   {:.caption}

6. Open the CodedUITestBuilder from the existing Coded UI project by right-clicking the CodedUITestMethod in the CUIT file and clicking the Generate Code for Coded UI test as shown in the following screenshot. You can see the same CodedUITestBuilder in the bottom-right corner of the window.

   ![CodedUITestBuilder with Coded UI project by right clicking](UIAutomation_images/UIAutomation_img4.png)



   CodedUITestMethod
   {:.caption}
7. Now, drag the Crosshairs to the UI elements of your WPF SfTreeGrid application, and it shows the available properties of the inner UI elements in SfTreeGrid.
8. Record the actions made on UI elements by clicking the Record button on the CodedUITest builder. For example you can record the action of changing the cell value in SfTreeGrid. Click the Pause button to finish the record.



   ![Record button on the CodedUITest builder](UIAutomation_images/UIAutomation_img5.png)



   CodedUITest
   {:.caption}

9. After the record has been completed, click the GenerateCode icon in CodedUITestBuilder for generate a test method, and then close the CodedUITestBuilder. You can see the generated code for cell value changed action as follows.

{% tabs %}
{% highlight c# %}

public void RecordedMethod1()
{
     public void RecordedMethod2()
   {
    #region Variable Declarations
    WpfText uIHardingText = this.UIWpfWindow.UITreeGridRowControlCustom.UITreeGridCellCustom.UIHardingText;
    WpfEdit uIItemEdit = this.UIWpfWindow.UITreeGridRowControlCustom.UITreeGridCellCustom.UIItemEdit;
    WpfText uIJeffersonText = this.UIWpfWindow.UITreeGridRowControlCustom1.UITreeGridCellCustom.UIJeffersonText;
   #endregion
    // Double-Click 'Harding' label
    Mouse.DoubleClick(uIHardingText, new Point(75, 5));
    // Type 'sync' in text box
    uIItemEdit.Text = this.RecordedMethod2Params.UIItemEditText;
    // Click 'Jefferson' label
    Mouse.Click(uIJeffersonText, new Point(140, 6));
}
}

{% endhighlight %}
{% endtabs %}

10. Create an assertion to check the modified cell value. Drag the crosshair to the modified cell, and the Assertion window appears. The properties for control (Cell) is now listed in the Assertion dialog box. You can add assertion by clicking the Generate Code button in CodedUITestBuilder.

    ![modified cell value](UIAutomation_images/UIAutomation_img6.png)



    Assertion window
    {:.caption}

11. After all the tests and assertion have been created, right-click the Test method, and click Run Tests to run the test as follows.

    ![Test method and click Run Tests ](UIAutomation_images/UIAutomation_img7.png)



    Run Test
	{:.caption}

###  Properties 

<table>
<tr>
<td>
{{'**UI Elements**'| markdownify }}
</td>
<td>
{{'**Properties**'| markdownify }}
</td>
</tr>
<tr>
<td>
TreeGrid
</td>
<td>
RowCount
ColumnCount
SelectionMode
SelectionUnit
SelectionIndex
SelectedItemCount

</td>
</tr>
<tr>
<td>
TreeGridCell
</td>
<td>
CellValue
FormattedValue
RowIndex
ColumnIndex
ColumnName

</td>
</tr>
<tr>
<td>
TreeGridHeaderCell
</td>
<td>
MappingName
SortDirection
SortNumberVisibility

</td>
</tr>
<tr>
<td>
TreeGridRowHeaderCell
</td>
<td>
RowErrorMessage
RowIndex
State

</td>
</tr>
<tr>
<td>
TreeGridStackedHeaderCell
</td>
<td>
Default Properties  
</td>
</tr>
<tr>
<td>
TreeGridExpanderCell
</td>
<td>
Default properties
</td>
</tr>
</table>



<table>
<tr>
<td>
{{'**Automation peer class name**'| markdownify }}
</td>
<td>
{{'**Control name in code generation**'| markdownify }}
</td>
<td>
{{'**Property provider class name**'| markdownify }}
</td>
</tr>
<tr>
<td>
SfTreeGridAutomationPeer
</td>
<td>
WpfSfTreeGrid
</td>
<td>
SfTreeGridPropertyProvider
</td>
</tr>
<tr>
<td>
TreeGridCellAutomationPeer
</td>
<td>
WpfSfTreeGridCell
</td>
<td>
SfTreeGridCellPropertyProvider
</td>
</tr>
<tr>
<td>
TreeGridHeaderCellAutomationPeer
</td>
<td>
WpfSfTreeGridHeaderCell
</td>
<td>
SfTreeGridHeaderCellPropertyProvider
</td>
</tr>
<tr>
<td>
TreeGridRowHeaderCellAutomationPeer
</td>
<td>
WpfSfTreeGridRowHeaderCell
</td>
<td>
SfTreeGridRowHeaderCellPropertyProvider
</td>
</tr>
<tr>
<td>
TreeGridStackedHeaderCellAutomationPeer
</td>
<td>
WpfSfTreeGridStackedHeaderCell
</td>
<td>
SfTreeGridStackedHeaderCellPropertyProvider
</td>
</tr>
<tr>
<td>
TreeGridExpanderCellAutomationPeer
</td>
<td>
WpfTreeGridExpanderCell
</td>
<td>
SfTreeGridExpanderCellPropertyProvider
</td>
</tr>
</table>


N> You can refer to our [WPF TreeGrid](https://www.syncfusion.com/wpf-controls/treegrid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeGrid example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the treegrid.