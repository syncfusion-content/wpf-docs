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
AutoComplete<br/><br/></td></tr>
<tr>
<td>
Barcode<br/><br/></td></tr>
<tr>
<td>
Bullet Graph<br/><br/></td></tr>
<tr>
<td>
BusyIndicator<br/><br/></td></tr>
<tr>
<td>
ButtonAdv<br/><br/></td></tr>
<tr>
<td>
Calculate<br/><br/></td></tr>
<tr>
<td>
CalendarEdit<br/><br/></td></tr>
<tr>
<td>
CardView<br/><br/></td></tr>
<tr>
<td>
Carousel<br/><br/></td></tr>
<tr>
<td>
Clock<br/><br/></td></tr>
<tr>
<td>
GanttControl<br/><br/></td></tr>
<tr>
<td>
SfChart<br/><br/></td></tr>
<tr>
<td>
CheckedListBox<br/><br/></td></tr>
<tr>
<td>
Chromeless Window<br/><br/></td></tr>
<tr>
<td>
ColorPicker<br/><br/></td></tr>
<tr>
<td>
ColorPickerPalette<br/><br/></td></tr>
<tr>
<td>
ComboBoxAdv<br/><br/></td></tr>
<tr>
<td>
CurrencyTextBox<br/><br/></td></tr>
<tr>
<td>
DateTimeEdit<br/><br/></td></tr>
<tr>
<td>
DockingManager<br/><br/></td></tr>
<tr>
<td>
DocumentContainer<br/><br/></td></tr>
<tr>
<td>
DoubleTextBox<br/><br/></td></tr>
<tr>
<td>
DropDownButtonAdv<br/><br/></td></tr>
<tr>
<td>
EditControl<br/><br/></td></tr>
<tr>
<td>
FontComboBox<br/><br/></td></tr>
<tr>
<td>
GridControl<br/><br/></td></tr>
<tr>
<td>
GridDataControl<br/><br/></td></tr>
<tr>
<td>
GridTreeControl<br/><br/></td></tr>
<tr>
<td>
GroupBar<br/><br/></td></tr>
<tr>
<td>
Grouping<br/><br/></td></tr>
<tr>
<td>
HierarchyNavigator<br/><br/></td></tr>
<tr>
<td>
IntegerTextBox<br/><br/></td></tr>
<tr>
<td>
MaskedTextBox<br/><br/></td></tr>
<tr>
<td>
MenuAdv<br/><br/></td></tr>
<tr>
<td>
NotifyIcon<br/><br/></td></tr>
<tr>
<td>
Pager<br/><br/></td></tr>
<tr>
<td>
PercentTextBox<br/><br/></td></tr>
<tr>
<td>
PinnableListBox<br/><br/></td></tr>
<tr>
<td>
PivotGridControl<br/><br/></td></tr>
<tr>
<td>
PropertyGrid<br/><br/></td></tr>
<tr>
<td>
RangeSliderControl<br/><br/></td></tr>
<tr>
<td>
Report Writer<br/><br/></td></tr>
<tr>
<td>
ReportViewer<br/><br/></td></tr>
<tr>
<td>
Ribbon<br/><br/></td></tr>
<tr>
<td>
PdfViewerControl<br/><br/></td></tr>
<tr>
<td>
SfAccordion<br/><br/></td></tr>
<tr>
<td>
SfBusyIndicator<br/><br/></td></tr>
<tr>
<td>
SfCalculator<br/><br/></td></tr>
<tr>
<td>
SfCircularGauge<br/><br/></td></tr>
<tr>
<td>
SfColorPalette<br/><br/></td></tr>
<tr>
<td>
SfDataGrid<br/><br/></td></tr>
<tr>
<td>
SfDatePicker<br/><br/></td></tr>
<tr>
<td>
SfDateTimeRangeNavigator<br/><br/></td></tr>
<tr>
<td>
SfDiagram<br/><br/></td></tr>
<tr>
<td>
SfDigitalGauge<br/><br/></td></tr>
<tr>
<td>
SfDomainUpDown<br/><br/></td></tr>
<tr>
<td>
SfGridSplitter<br/><br/></td></tr>
<tr>
<td>
SfHeatMap<br/><br/></td></tr>
<tr>
<td>
SfHubTile<br/><br/></td></tr>
<tr>
<td>
SfKanban<br/><br/></td></tr>
<tr>
<td>
SfLinearGauge<br/><br/></td></tr>
<tr>
<td>
SfMap<br/><br/></td></tr>
<tr>
<td>
SfMaskedEdit<br/><br/></td></tr>
<tr>
<td>
SfMultiColumnDropDownControl<br/><br/></td></tr>
<tr>
<td>
SfPulsingTile<br/><br/></td></tr>
<tr>
<td>
SfRadialSlider<br/><br/></td></tr>
<tr>
<td>
SfRichTextBoxAdv<br/><br/></td></tr>
<tr>
<td>
SfSpreadsheet<br/><br/></td></tr>
<tr>
<td>
SfTimePicker<br/><br/></td></tr>
<tr>
<td>
SfNavigationDrawer<br/><br/></td></tr>
<tr>
<td>
SfRadialMenu<br/><br/></td></tr>
<tr>
<td>
SfRangeSlider<br/><br/></td></tr>
<tr>
<td>
SfRating<br/><br/></td></tr>
<tr>
<td>
SfSchedule<br/><br/></td></tr>
<tr>
<td>
SfSunburstChart<br/><br/></td></tr>
<tr>
<td>
SfSurfacechart<br/><br/></td></tr>
<tr>
<td>
SfTextBoxExt<br/><br/></td></tr>
<tr>
<td>
SfTreeGrid<br/><br/></td></tr>
<tr>
<td>
SfTreeMap<br/><br/></td></tr>
<tr>
<td>
SfTreeNavigator<br/><br/></td></tr>
<tr>
<td>
Smith Chart<br/><br/></td></tr>
<tr>
<td>
Sparkline<br/><br/></td></tr>
<tr>
<td>
SpellChecker<br/><br/></td></tr>
<tr>
<td>
SplitButtonAdv<br/><br/></td></tr>
<tr>
<td>
SpreadsheetControl(Classic)<br/><br/></td></tr>
<tr>
<td>
TabControlExt<br/><br/></td></tr>
<tr>
<td>
TabNavigationControl<br/><br/></td></tr>
<tr>
<td>
TabSplitter<br/><br/></td></tr>
<tr>
<td>
TaskBar<br/><br/></td></tr>
<tr>
<td>
TileViewControl<br/><br/></td></tr>
<tr>
<td>
TimeSpanEdit<br/><br/></td></tr>
<tr>
<td>
ToolBarAdv<br/><br/></td></tr>
<tr>
<td>
TreeViewAdv<br/><br/></td></tr>
<tr>
<td>
UpDown<br/><br/></td></tr>
<tr>
<td>
WizardControl<br/><br/></td></tr>
</table>
