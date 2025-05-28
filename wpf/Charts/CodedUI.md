---
layout: post
title: Coded UI in WPF Charts control | Syncfusion
description: Learn here all about Coded UI support in Syncfusion® WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Coded UI in WPF Charts (SfChart)

Automated tests that drive your application through its user interface (UI) are known as **coded UI tests** (CUITs). These tests include functional testing of the UI controls. SfChart supports Coded UI automation that helps you create automated tests for inner elements and records the sequence of actions. While dragging the crosshair on UI elements, it shows the properties of the respective UI elements and you can also add assertions for each of the properties.

## Levels

<table>
<tr>
<th>Levels</th>
<th>Description</th>
</tr>
<tr>
<td>Level 1</td>
<td>Record and identify UI elements when you perform mouse and keyboard actions.</td>
</tr>
<tr>
<td>Level 2</td>
<td>Provide custom properties for UI elements when you drag the crosshair on the UI element.</td>
</tr>
<tr>
<td>Level 3</td>
<td>CUIT generates code from recorded session. Create specialized class to access custom properties so the generated code is simplified.</td>
</tr>
</table>

## Requirements

Coded UI provides support only in:

* Visual Studio Premium
* Visual Studio Enterprise
* Visual Studio Ultimate

For more information about the supported platforms and configurations, refer to [this Microsoft documentation](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2015/test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings?view=vs-2015).

## Configuration

To test SfChart with CUITs, build the Extension Project and place it in the specified location. You can download the Extension Project for SfChart from [here](https://www.syncfusion.com/downloads/support/directtrac/general/ze/CodedUI-1453395823.zip).

1. Open the extension project and build it.

2. Get the Syncfusion.SfChart.CUITExtension.WPF.dll from the bin folder.

Place this assembly in the location mentioned below, and install it in the Global Assembly Cache (GAC).

The assembly must be placed into the following directory based on your Visual Studio version:

For Visual Studio 2015: 
C:\Program Files (x86)\Common Files\Microsoft Shared\VSTT\14.0\UITestExtensionPackages

N> Syncfusion.SfChart.CUITExtension.WPF.dll needs to be installed in the GAC location. Please refer to the [Microsoft documentation on GAC installation](https://learn.microsoft.com/en-us/previous-versions/dotnet/netframework-2.0/ex0ss12c(v=vs.80)).

## Getting Started

### Coded UI Project Creation

Run Visual Studio in administrator mode.

Create a new Coded UI Test Project as shown in the following screenshot:

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img1.jpeg)

After you create a new Coded UI project, a CUIT file is added automatically and the Generate Code dialog box appears. Choose "Record actions, edit UI map or add assertions."

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img2.jpeg)

Now Visual Studio gets minimized and the CodedUITestBuilder appears in the bottom right corner of your window. You can record actions by clicking "Start Recording" in CodedUITestBuilder.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img3.jpeg)

You can also open the CodedUITestBuilder from an existing Coded UI project by right-clicking on the CodedUITestMethod1 in the CUIT file and clicking "Generate Code for Coded UI Test."

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img4.jpeg)

### Record and Generate Code

If you create a Coded UI Test project, UIMap – CodedUITestBuilder is shown at the bottom right corner.

Now you can record and perform actions in your application.

CodedUITestBuilder identifies each action and displays a tooltip message like this:

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img5.jpeg)

If you recorded by mistake, you can select recorded steps to delete.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img6.jpeg)

Once the recording is completed, click the `Generate Code` icon in CodedUITestBuilder to generate a test method. Then close the CodedUITestBuilder, and you can see the generated code action as follows:

{% highlight c# %}
public void RecordedMethod1()
{
    #region Variable Declarations
    WpfSfChart uISfChartCustom = this.UICUITestSampleDemoWindow.UISfChartCustom;
    WpfChartSeries uIColumnSeriesCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIColumnSeriesCustom;
    WpfLegend uIChartLegendCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIChartLegendCustom;
    WpfChartAxis uINumericalAxisCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UINumericalAxisCustom;
    WpfChartAxis uICategoryAxisCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UICategoryAxisCustom;
    WpfZoomingBehavior uIZoomInCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIZoomInCustom;
    WpfZoomingBehavior uIZoomOutCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIZoomOutCustom;
    WpfZoomingBehavior uIZoomResetCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIZoomResetCustom;
    WpfZoomingBehavior uIZoomPanCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIZoomPanCustom;
    WpfZoomingBehavior uISelectionZoomCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UISelectionZoomCustom;
    #endregion
}
{% endhighlight %}

### Add Assertion

You can also create an assertion to check the modified chart/series property values. Drag the crosshair to the chart series, and the Assertion window will appear.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img7.jpeg)

The series properties for the control are now listed in the Assertion dialog box. You can add an assertion by clicking the Generate Code button in CodedUITestBuilder.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img8.jpeg)

Validate assertion properties by using comparators. You can also add an assertion failure message.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img9.jpeg)

Another way to add an assertion is by clicking the crosshair icon in CodedUITestBuilder. This lists all identified controls, allowing you to select the control you want to validate.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img10.jpeg)

Click the Generate Code icon to generate assertion code, then close the builder when validation is finished.

{% highlight c# %}
public void AssertMethod1()
{
    #region Variable Declarations
    WpfChartSeries uIColumnSeriesCustom = this.UICUITestSampleDemoWindow.UISfChartCustom.UIColumnSeriesCustom;
    #endregion
    // Verify that the 'SegmentsCount' property of 'ColumnSeries' custom control equals '10'
    Assert.AreEqual(this.AssertMethod1ExpectedValues.UIColumnSeriesCustomSegmentsCount, uIColumnSeriesCustom.SegmentsCount, "Segments Count Mismatched...");
}
{% endhighlight %}

## Run Tests

After all tests and assertions are created, right-click on the Test method and click Run Tests to run the test as follows.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img11.jpeg)

Open the test explorer and check if the test passed or failed.

![Coded UI support in WPF SfChart](CodedUI_images/CodedUI_img12.jpeg)

## Tables of Properties

The following properties are available for each of the UI elements in SfChart:

<table>
<tr>
<td>
UI Elements<br/><br/></td><td>
Properties<br/><br/></td></tr>
<tr>
<td>
SfChart<br/><br/></td><td>
Header, PrimaryAxis, SecondaryAxis, Palette, AreaBackground, AreaBorderBrush, AreaBorderThickness, SideBySideSeriesPlacement, SeriesCount, BehaviorsCount, AnnotationsCount, TechnicalIndicatorsCount.<br/><br/></td></tr>
<tr>
<td>
Axis<br/><br/></td><td>
VisibleRange, Header, HeaderPosition, OpposedPosition, Orientation, ShowGridLines, IsInversed, ShowTrackBallInfo, LabelFormat, LabelsSource, LabelExtent, LabelsPosition, MaximumLabels, LabelsIntersectAction, LabelRotationAngle, EdgeLabelsDrawingMode, EdgeLabelsVisibilityMode, TickLinesPosition.<br/><br/></td></tr>
<tr>
<td>
Series<br/><br/></td><td>
Area, IsSeriesVisible, Interior, Stroke, StrokeThickness, SeriesSelectionBrush, LegendIcon, VisibilityOnLegend, Label, Palette, SegmentsCount, AdornmentsCount.<br/><br/></td></tr>
<tr>
<td>
ZoomPan ToolBar<br/><br/></td><td>
IconBackground, ToolBarIconHeight, ToolBarIconWidth, ToolBarIconMargin<br/><br/></td></tr>
<tr>
<td>
Legend<br/><br/></td><td>
Header, Orientation, DockPosition, LegendPosition, IconVisibility, CheckBoxVisibility, IconWidth, IconHeight, ItemMargin, Background, OffsetX, OffsetY.<br/><br/></td></tr>
<tr>
<td>
Legend Item<br/><br/></td><td>
IconVisibility, CheckBoxVisibility, VisibilityOnLegend, IsSeriesVisible, Label, IconWidth, IconHeight, ItemMargin.<br/><br/></td></tr>
</table>

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to learn about various chart types and how to easily configure them with built-in support for creating stunning visual effects.