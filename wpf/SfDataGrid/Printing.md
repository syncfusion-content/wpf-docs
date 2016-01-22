---
layout: post
title: Printing | SfDataGrid | WPF | Syncfusion
description: printing
platform: wpf
control: SfDataGrid
documentation: ug
---

# Printing

SfDataGrid control allows you to print the data displayed in the DataGrid. The Print Manager__of SfDataGrid is designed to support different orientations, sizes, margins, etc.  You can change print settings using the PrintSettings property of SfDataGrid. The following section covers all different API sets, print preview options and methods in printing feature.

## Overview

EssentialDataGrid for WPF provides in-built support for print and print preview.You can enable the printing features inSfDataGrid control. You can print SfDataGrid control in two ways – 

* Invoke the public method SfDataGrid.Print() to print the instance of the Grid with print preview (or)
* Using SfDataGrid.ShowPrintPreview()_,_ you can view the print preview window and print the Grid.

The following table lists the methods available in SfDataGrid for printing support feature.

Methods table

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
SfDataGrid.ShowPrintPreview()</td><td>
ShowPrintPreview()</td><td>
Invoked to show the print preview window. You can use this to set the options before printing the data that is displayed in SfDataGrid.</td></tr>
<tr>
<td>
SfDataGrid.Print()</td><td>
Print()</td><td>
Invoked to print the data displayed in SfDataGrid with default settings (print preview window is not displayed).</td></tr>
</table>
The following table lists the SfDataGrid properties in SfDataGrid’s PrintSettings.

Property Table

<table>
<tr>
<th>
Property Name</th><th>
Type</th><th>
Description</th><th>
Default Value</th></tr>
<tr>
<td>
SfDataGrid.PrintSettings.AllowColumnWidthFitToPrintPage</td><td>
Boolean</td><td>
Gets or sets whether to allow the columns to fit in a printable page.\ or not.</td><td>
True</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.AllowRepeatHeaders</td><td>
Boolean</td><td>
Gets or sets whether the column header is displayed in the printable pages or not.</td><td>
True</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPageFooterHeight</td><td>
Double</td><td>
Gets or sets the height for the footer template in the printable page.</td><td>
0</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPagerFooterTemplate</td><td>
DataTemplate</td><td>
Gets or sets the footer template for printable page.</td><td>
Null</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPageHeaderHeight</td><td>
Double</td><td>
Gets or sets the height for the header template in the printable page.</td><td>
0</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPageHeaderTemplate</td><td>
DataTemplate</td><td>
Gets or sets the header template for printable page.</td><td>
Null</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPageMargin</td><td>
Thickness</td><td>
Gets or sets the page margin for the printable page.</td><td>
new Thickness(96)</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintPageWidth</td><td>
Double</td><td>
Gets or sets the width for printable page.</td><td>
793.90d</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintManagerBase.PrintPageHeight</td><td>
Double</td><td>
Gets or sets the height for the printable page.</td><td>
1122.52d</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintManagerBase.PrintPageHeaderTemplate</td><td>
DataTemplate</td><td>
Gets or sets the header template for the printable page.</td><td>
Null</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintManagerBase.PrintPageOrientation</td><td>
PrintOrientation</td><td>
Gets or sets the orientation for printing.</td><td>
PrintOrientation.Portrait</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintManagerBase.PrintScaleOption</td><td>
PrintScaleOptions</td><td>
Gets or sets the print scale options for printing.</td><td>
PrintScaleOptions.NoScaling</td></tr>
<tr>
<td>
SfDataGrid.PrintSettings.PrintManagerBase.PrintRowHeight</td><td>
Double</td><td>
Gets or sets the print row height</td><td>
24</td></tr>
</table>


The following code example shows you how to use Printing feature in SfDataGrid with Print Preview.


{% highlight xaml %}




<Window.DataContext>

<local:ViewModel/>

</Window.DataContext>



<syncfusion:SfDataGrid x:Name="syncgrid"

                       AutoGenerateColumns="True"

                       ItemsSource="{Binding EmployeeDetails}"

                       NavigationMode="Row">
{% endhighlight %}


{% highlight C# %}





private void OnPrintGrid(object sender, RoutedEventArgs args)

{

     if (dataGrid == null) 

         return;

     dataGrid.ShowPrintPreview();

}



private void OnDirectPrintGrid(object sender, RoutedEventArgs args)

{

     if (dataGrid == null) 

         return;

     dataGrid.Print();

}



{% endhighlight %}


The following screenshot displays the SfDataGrid in print preview mode. 



![](Features_images/Features_img199.png)



SfDataGrid in print preview mode
{:.caption}
## Custom Printing

The default SfDataGrid.ShowPrintPreview() provides you the multiple options in printing. It also provides the flexibility to write CustomPrintManager.  The descendant of Custom Print Manager is derived from GridPrintManager based on the required level of customization method that is overridden.  

The following table lists all the overridable methods of GridPrintManager.

Method Table

<table>
<tr>
<th>
Method</th><th>
Prototype</th><th>
Description</th></tr>
<tr>
<td>
GridPrintManager.InitializeProperties()</td><td>
InitializeProperties()</td><td>
Invoked to initialize all the print options for printing in SfDataGrid</td></tr>
<tr>
<td>
GridPrintManager.GetColumnNames()</td><td>
List&lt;string&gt; GetColumnNames()</td><td>
Invoked to get the list of columns that is printed.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnWidth()</td><td>
double GetColumnWidth(string mappingName)</td><td>
Invoked to get the column width for corresponding Mapping Name</td></tr>
<tr>
<td>
GridPrintManager.GetColumnHeaderText()</td><td>
string GetColumnHeaderText(string mappingName)</td><td>
Invoked to get the columns’s Header Text.</td></tr>
<tr>
<td>
GridPrintManager.GetFormattedCellValue()</td><td>
string GetFormatedCellValue(object cellValue, string mappingName)</td><td>
Invoked to get the formatted cell value from the column.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnPadding()</td><td>
Thickness GetColumnPadding(string mappingName)</td><td>
Invoked to get the column’s padding corresponding to the column’s Mapping Name.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnTextAlignment()</td><td>
TextAlignment GetColumnTextAlignment(string mappingName)</td><td>
Invoked to get column’s text alignment corresponding to the column’s Mapping Name.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnTextWrapping()</td><td>
TextWrapping GetColumnTextWrapping(string mappingName)</td><td>
Invoked to get the column’s text alignment corresponding to the column’s Mapping Name.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnElement()</td><td>
object GetColumnElement(object record, string mappingName)</td><td>
Invoked to get the column’s element to set content for the Print Grid Cell.</td></tr>
<tr>
<td>
GridPrintManager.GetColumnHeaderElement()</td><td>
UIElement GetColumnHeaderElement(string mappingName)</td><td>
Invoked to get the Header column element to set content for the Print Header Cell</td></tr>
<tr>
<td>
GridPrintManager.GetGroupCaptionStringFormat()</td><td>
string GetGroupCaptionStringFormat()</td><td>
Invoked to get the Group Caption String Format</td></tr>
<tr>
<td>
GridPrintManager.GetPrintGridCell()</td><td>
PrintGridCell GetPrintGridCell(object record, string mappingName)</td><td>
Invoked to return new instance of PrintGridCell</td></tr>
</table>


The following code example shows you how a CustomPrintManager is developed using the overridable methods in Print Manager.


{% highlight C# %}



    internal class CustomPrintManager : GridPrintManager

    {

        private SfDataGrid dataGrid;



        public CustomPrintManager(SfDataGrid grid)

            : base(grid)

        {

            dataGrid = grid;

            dataGrid.PrintSettings.PrintPageHeaderHeight = 25;

            dataGrid.PrintSettings.PrintPageFooterHeight = 25;

            dataGrid.PrintSettings.PrintPageFooterTemplate = App.Current.Resources["footerTemplate"] as DataTemplate;

            dataGrid.PrintSettings.PrintPageHeaderTemplate = App.Current.Resources["headerTemplate"] as DataTemplate;

        }

        /// <summary>

        /// Invokes to Get the column width for the corresponding Mapping name.

        /// </summary>

        /// <param name="mappingName"></param>

        /// <returns>double</returns>

        protected override double GetColumnWidth(string mappingName)

        {

            return (dataGrid.PrintSettings.PrintPageWidth -

                    (dataGrid.PrintSettings.PrintPageMargin.Left + dataGrid.PrintSettings.PrintPageMargin.Right + 20))/4;

        }



        /// <summary>

        /// Invokes to Get the Column's List that need to be printed.

        /// </summary>

        /// <returns></returns>

        /// <remarks>List<string></remarks>

        protected override System.Collections.Generic.List<string> GetColumnNames()

        {

            return this.dataGrid.Columns.Select(x => x.MappingName).ToList();

        }



        public override PrintGridCell GetPrintGridCell(object record, string mappingName)

        {

            var index = dataGrid.View.Records.IndexOfRecord(record);

            if (index%2 == 0)

                return new PrintGridCell() {Background = new SolidColorBrush(Colors.Bisque)};

            return base.GetPrintGridCell(record, mappingName);

        }



        /// <summary>

        /// Invokes to get the Column's Padding corresponding to the column's Mapping name.

        /// </summary>

        /// <param name="mappingName"></param>

        /// <returns>Thickness</returns>

        protected override Thickness GetColumnPadding(string mappingName)

        {

            var padding = dataGrid.Columns[mappingName].ReadLocalValue(GridColumn.PaddingProperty);

            return padding != DependencyProperty.UnsetValue

                          ? new Thickness(4)

                          : new Thickness(2, 2, 6, 6);

        }



        /// <summary>

        /// Invokes to get the column's Header Text

        /// </summary>

        /// <param name="mappingName"></param>

        /// <returns>string</returns>

        protected override string GetColumnHeaderText(string mappingName)

        {

            if (mappingName == "ContactNumber")

                return "Contact Number";

            return base.GetColumnHeaderText(mappingName);

        }



        /// <summary>

        /// Invokes to get the Column Text alignment corresponding with the Mapping name.

        /// </summary>

        /// <param name="mappingName"></param>

        /// <returns>TextAlignment</returns>

        protected override TextAlignment GetColumnTextAlignment(string mappingName)

        {

            if (mappingName == "Freight")

                return TextAlignment.Right;

            return base.GetColumnTextAlignment(mappingName);

        }



    }

}


{% endhighlight %}

When Custom Print Manager is created, you can assign it to PrintManagerBase to load the Custom Print Manager.


{% highlight C# %}



var window = new PreviewWindow();

window.PrintPreviewArea.PrintManagerBase = new CustomPrintManager(dataGrid);

window.ShowDialog();

{% endhighlight %}

The following screenshot displays you how SfDataGrid is printed.  



![](Features_images/Features_img200.png)



SfDataGrid in print mode
{:.caption}
## How to

### How to set Header and Footer in Printable Page

DataGrid allows you to set the Header and Footer in Printable page. You can set the Header and Footer by using PrintPageHeaderTemplate and PrintPageFooterTemplate properties. 

The following code example illustrates how to set Header and Footer in PrintablePage.


{% highlight xaml %}



<Window.Resources>

      <DataTemplate x:Key="headertemplate">

         <TextBlock Text="OrderDetails" Foreground="Blue" FontSize="25"/>

      </DataTemplate>

      <DataTemplate x:Key="footertemplate">

         <Image Width="200" Height="50" Source="../Images/syncfusion.jpg"/>

      </DataTemplate>

</Window.Resources>
{% endhighlight %}

{% highlight C# %}



private void ShowPrintPreview(object sender, RoutedEventArgs e)

  {

     syncgrid.PrintSettings.PrintPageHeaderTemplate = App.Current.MainWindow.FindResource("headertemplate") as DataTemplate;



     syncgrid.PrintSettings.PrintPageFooterTemplate = App.Current.MainWindow.FindResource("footertemplate") as DataTemplate;



     syncgrid.PrintSettings.PrintPageHeaderHeight = 100;

     syncgrid.PrintSettings.PrintPageFooterHeight = 100;            

            syncgrid.ShowPrintPreview();

        }

{% endhighlight %}

The following screenshot displays the output for Header and Footer applied in Printable page,



![](Features_images/Features_img201.png)



Header and Footer applied in Printable page
{:.caption}