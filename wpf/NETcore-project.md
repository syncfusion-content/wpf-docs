---
layout: post
title: .NET Core | WPF | Syncfusion
description: .NET Core support for Syncfusion Essential WPF controls
platform: wpf
control: .NET Core
documentation: ug
---

# .NET Core Support

This section explains how to create the project in .NET Core application.

## Create a .NET Core project

**Step 1**: Open Visual Studio, go to **"File > New > Project..."** and you can now see **"Create a new project"** dialog. Here, select **"WPF App (.NET Core)"** template and click **"Next"**.

![NETcore showing create the project](NETcore_WPF_images/NETcore_createproject.jpeg)


**Step 2**: You will now see **"Configure your new project"** dialog. Here, fill in the necessary details and click **"Create"**.

![NETcore showing configure the project](NETcore_WPF_images/NETcore_configureproject.jpeg)


**Step 3**: Finally, WPF (.NET Core) sample project is created.

![NETcore application output](NETcore_WPF_images/NETcore_sample.jpeg)

**Step 4**: Before adding your controls into the application, first you need to remove the default template like in the below screenshot.

![NETcore showing hide the code](NETcore_WPF_images/NETcore_hidecode.jpeg)


N> If you do not remove the default template, you cannot see your control in the output window.

**Step 5**: Now, you can add your controls. To do so, follow the immediate section **"Adding controls in WPF (.NET Core) application"** for more details. 

## Adding controls in WPF (.NET Core) application

The below section explains how to add controls in WPF (.NET Core) application.

### Through assembly deployment

In **"Solution Explorer"**, right-click on **"Dependencies"** and select **"Add Reference"**.

![NETcore showing assembly](NETcore_WPF_images/NETcore_reference.png)

Now, **"Reference Manager"** dialog will be opened. Here click **"Browse"** and can select the needed assemblies from the location mentioned in below note section. On selecting necessary assemblies, click **"Add"** and then click **"Ok"**. Now, required assemblies are added in to the project, like in the below screenshot.

N> You can get Syncfusion WPF (.NET Core) controls assemblies from `netcoreapp3.0` folder in the following location - C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\x.x.x.x\precompiledassemblies

![NETcore showing assembly](NETcore_WPF_images/NETcore_assembly.jpeg)

### Through NuGet Package

[Click here](https://help.syncfusion.com/wpf/nuget-packages) to find more details regarding how to install the NuGet packages in WPF application.


### Example: Adding ButtonAdv control

We are now going to see a demo on how to add **"ButtonAdv"** control in WPF (.NET Core) application.

**Step 1**:	Add the following dependent assembly for the inclusion of **"ButtonAdv"** control.

•	Syncfusion.Shared.WPF

**Step 2**:	We can add button either using code behind or through XAML code. Both methods are explained below.

a.	Following code explains how to declare the **"ButtonAdv"** control through XAML.

{% tabs %}
{% highlight xaml %}

<Window x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        xmlns:sync="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">

<sync:ButtonAdv Label="Hello World" Height = “35” Width = “150”/>

{% endhighlight %}
{% endtabs %}

b.	Following code explains how to declare the **"ButtonAdv"** control through code.

{% tabs %}
{% highlight xaml %}

<Grid X:Name = "ROOT_Grid">

</Grid>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

using Syncfusion.Windows.Tools.Controls;

ButtonAdv button = new ButtonAdv();
button.Height = 35;
button.width = 150;
button.Label = "Hello World!";
ROOT_Grid.Children.Add(button);

{% endhighlight %}
{% endtabs %}

**Step 3**: Run the application.

![NETcore showing control output](NETcore_WPF_images/NETcore_controloutput.jpeg)


## List of supported controls

The following controls are support in .NET Core 3.0

<table>
<tr>
<th>
Controls List<br/><br/></th></tr>
<tr>
<td>
{{'[AutoComplete](https://help.syncfusion.com/wpf/autocomplete/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Barcode](https://help.syncfusion.com/wpf/sfbarcode/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Bullet Graph](https://help.syncfusion.com/wpf/sfbulletgraph/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[BusyIndicator](https://help.syncfusion.com/wpf/sfbusyindicator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ButtonAdv](https://help.syncfusion.com/wpf/buttonadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Calculate](https://help.syncfusion.com/wpf/calculate/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[CalendarEdit](https://help.syncfusion.com/wpf/calendaredit/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[CardView](https://help.syncfusion.com/wpf/cardview/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Carousel](https://help.syncfusion.com/wpf/carousel/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
Clock<br/><br/></td></tr>
<tr>
<td>
{{'[GanttControl](https://help.syncfusion.com/wpf/gantt/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfChart](https://help.syncfusion.com/wpf/sfchart/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[CheckedListBox](https://help.syncfusion.com/wpf/checklistbox/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Chromeless Window](https://help.syncfusion.com/wpf/chromlesswindow/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ColorPicker](https://help.syncfusion.com/wpf/colorpicker/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ColorPickerPalette](https://help.syncfusion.com/wpf/colorpickerpalatte/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ComboBoxAdv](https://help.syncfusion.com/wpf/comboboxadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[CurrencyTextBox](https://help.syncfusion.com/wpf/currencytextbox/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[DateTimeEdit](https://help.syncfusion.com/wpf/datetimeedit/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[DockingManager](https://help.syncfusion.com/wpf/dockingmanager/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[DocumentContainer](https://help.syncfusion.com/wpf/documentcontainer/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[DoubleTextBox](https://help.syncfusion.com/wpf/doubletextbox/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[DropDownButtonAdv](https://help.syncfusion.com/wpf/dropdownbuttonadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[EditControl](https://help.syncfusion.com/wpf/syntaxeditor/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
FontComboBox<br/><br/></td></tr>
<tr>
<td>
{{'[GridControl](https://help.syncfusion.com/wpf/grid/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[GridDataControl](https://help.syncfusion.com/wpf/griddata/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[GridTreeControl](https://help.syncfusion.com/wpf/gridtree/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[GroupBar](https://help.syncfusion.com/wpf/groupbar/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Grouping](https://help.syncfusion.com/wpf/grouping/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[HierarchyNavigator](https://help.syncfusion.com/wpf/hierarchynavigator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[IntegerTextBox](https://help.syncfusion.com/wpf/integertextbox/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
MaskedTextBox<br/><br/></td></tr>
<tr>
<td>
{{'[MenuAdv](https://help.syncfusion.com/wpf/menuadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[NotifyIcon](https://help.syncfusion.com/wpf/notifyicon/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Pager](https://help.syncfusion.com/wpf/sfdatapager/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[PercentTextBox](https://help.syncfusion.com/wpf/percenttextbox/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
PinnableListBox<br/><br/></td></tr>
<tr>
<td>
{{'[PivotGridControl](https://help.syncfusion.com/wpf/pivotgrid/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[PropertyGrid](https://help.syncfusion.com/wpf/propertygrid/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[RangeSliderControl](https://help.syncfusion.com/wpf/sfrangeslider/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Report Writer](https://help.syncfusion.com/wpf/reportwriter/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ReportViewer](https://help.syncfusion.com/wpf/reportviewer/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Ribbon](https://help.syncfusion.com/wpf/ribbon/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[PdfViewerControl](https://help.syncfusion.com/wpf/pdfviewer/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfAccordion](https://help.syncfusion.com/wpf/sfaccordion/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfBusyIndicator](https://help.syncfusion.com/wpf/sfbusyindicator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfCalculator](https://help.syncfusion.com/wpf/sfcalculator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfCircularGauge](https://help.syncfusion.com/wpf/sfcirculargauge/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfColorPalette](https://help.syncfusion.com/wpf/sfcolorpalette/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDataGrid](https://help.syncfusion.com/wpf/sfdatagrid/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDatePicker](https://help.syncfusion.com/wpf/sfdatepicker/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDateTimeRangeNavigator](https://help.syncfusion.com/wpf/sfdatetimerangenavigator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDiagram](https://help.syncfusion.com/wpf/sfdiagram/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDigitalGauge](https://help.syncfusion.com/wpf/sfdigitalgauge/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfDomainUpDown](https://help.syncfusion.com/wpf/sfdomainupdown/getting-started)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfGridSplitter](https://help.syncfusion.com/wpf/sfgridsplitter/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfHeatMap](https://help.syncfusion.com/wpf/sfheatmap/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfHubTile](https://help.syncfusion.com/wpf/sfhubtile/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfKanban](https://help.syncfusion.com/wpf/sfkanban/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfLinearGauge](https://help.syncfusion.com/wpf/sflineargauge/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfMap](https://help.syncfusion.com/wpf/sfmaps/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfMaskedEdit](https://help.syncfusion.com/wpf/sfmaskededit/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfMultiColumnDropDownControl](https://help.syncfusion.com/wpf/sfmulticolumndropdown/getting-started)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfPulsingTile](https://help.syncfusion.com/wpf/sfhubtile/pulsing-tile-control)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfRadialSlider](https://help.syncfusion.com/wpf/sfradialslider/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfRichTextBoxAdv](https://help.syncfusion.com/wpf/sfrichtextboxadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfSpreadsheet](https://help.syncfusion.com/wpf/sfspreadsheet/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfTimePicker](https://help.syncfusion.com/wpf/sftimepicker/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfNavigationDrawer](https://help.syncfusion.com/wpf/sfnavigationdrawer/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfRadialMenu](https://help.syncfusion.com/wpf/sfradialmenu/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfRangeSlider](https://help.syncfusion.com/wpf/sfrangeslider/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfRating](https://help.syncfusion.com/wpf/sfrating/getting-started)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfSchedule](https://help.syncfusion.com/wpf/sfschedule/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfSunburstChart](https://help.syncfusion.com/wpf/sfsunburstchart/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfSurfaceChart](https://help.syncfusion.com/wpf/sfsurfacechart/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfTextBoxExt](https://help.syncfusion.com/wpf/sftextboxext/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfTreeGrid](https://help.syncfusion.com/wpf/sftreegrid/getting-started)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfTreeMap](https://help.syncfusion.com/wpf/sftreemap/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SfTreeNavigator](https://help.syncfusion.com/wpf/sftreenavigator/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Smith Chart](https://help.syncfusion.com/wpf/sfsmithchart/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[Sparkline](https://help.syncfusion.com/wpf/sfsparkline/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SpellChecker](https://help.syncfusion.com/wpf/sfspellchecker/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SplitButtonAdv](https://help.syncfusion.com/wpf/splitbutton/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[SpreadsheetControl(Classic)](https://help.syncfusion.com/wpf/spreadsheet/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TabControlExt](https://help.syncfusion.com/wpf/tabext/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TabNavigationControl](https://help.syncfusion.com/wpf/tabnavigation/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TabSplitter](https://help.syncfusion.com/wpf/tabsplitter/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TaskBar](https://help.syncfusion.com/wpf/taskbar/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TileViewControl](https://help.syncfusion.com/wpf/tileview/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TimeSpanEdit](https://help.syncfusion.com/wpf/timespanedit/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[ToolBarAdv](https://help.syncfusion.com/wpf/toolbaradv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[TreeViewAdv](https://help.syncfusion.com/wpf/treeviewadv/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[UpDown](https://help.syncfusion.com/wpf/updown/overview)' | markdownify }}<br/><br/></td></tr>
<tr>
<td>
{{'[WizardControl](https://help.syncfusion.com/wpf/wizard/overview)' | markdownify }}<br/><br/></td></tr>
</table>
