---
layout: post
title: Getting Started | OlapGauge | wpf | Syncfusion
description: getting started
platform: wpf
control: OlapGauge
documentation: ug
---

# Getting Started

This section covers the information required to create a simple OlapGauge bound to OLAP data source.

## Through Visual Studio

Open the Visual Studio IDE and navigate to File > New > Project > WPF Application (inside Visual C# Templates) to create a new WPF application.

Once the WPF application is created, go to View menu and select Toolbox option. Now the Toolbox will appear inside Visual Studio IDE. From the Visual Studio Toolbox, drag and drop the OlapGauge under **Syncfusion BI WPF** tag. It will automatically add the required assemblies into the application.

![](Getting-Started_images/Getting-Started_img1.png)

Add a **Name** to the OlapGauge component for accessing it through code-behind as shown in the following code sample.
   
{% highlight Xaml %}
  
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="SampleApplication.MainWindow"
    Title="MainWindow" Height="350" Width="525">
    <Grid>
         <syncfusion:OlapGauge x:Name="olapGauge" HorizontalAlignment="Left" VerticalAlignment="Top"/>
    </Grid>
</Window>
	
{% endhighlight %}

Include the following namespaces in the code-behind for using OlapReport and OlapDataManger in the application.

   * Syncfusion.Olap.Reports
   * Syncfusion.Olap.Manager

{% tabs %}

{% highlight c# %}

using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;

namespace SampleApplication
{
    public partial class MainWindow : SampleWindow
    {
        private string _connectionString;
        private OlapDataManager _olapDataManager;
        public MainWindow()
        {  
            InitializeComponent();
            _connectionString = " Enter a valid connection string ";
            //Connection string is passed to OlapDataManager as an argument
            _olapDataManager = new OlapDataManager(_connectionString);
            //A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport());
            // Finally OlapGauge gets the information from the OlapDataManager
            this.olapGauge.OlapDataManager = _olapDataManager;
            this.olapGauge.DataBind();
        }
             
        /// <summary>
        /// Defining OlapReport with Dimension and Measure
        /// </summary>
        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            // Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works";
            DimensionElement dimensionElementColumn = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer";
            // Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country");
            MeasureElements measureElementColumn = new MeasureElements();
            //Specifying the Measure name
            measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
            DimensionElement dimensionElementRow = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementRow.Name = "Date";
            // Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
            ///Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn);
            ///Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn);
            ///Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow);
            return olapReport;
        }
    }
}
	
{% endhighlight %}

{% highlight vbnet %}

Imports Syncfusion.Olap.Manager
Imports Syncfusion.Olap.Reports
Namespace SampleApplication
    Partial Public Class MainWindow Inherits SampleWindow
        Private _connectionString As String
        Private _olapDataManager As OlapDataManager
        Public Sub New()
            InitializeComponent()
            _connectionString = "Enter a valid connection string"
            ' Connection string is passed to OlapDataManager as an argument
            _olapDataManager = New OlapDataManager(_connectionString)
            ' A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport())
            ' Finally OlapGauge gets the information from the OlapDataManager 
            Me.olapGauge.OlapDataManager = _olapDataManager
            Me.olapGauge.DataBind()
        End Sub
    
	    ''' <summary>
        ''' Defining OlapReport with Dimension and Measure
        ''' </summary>
        Private Function CreateOlapReport() As OlapReport
            Dim olapReport As OlapReport = New OlapReport()
            ' Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works"
            Dim dimensionElementColumn As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer"
            ' Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country")
            Dim measureElementColumn As MeasureElements = New MeasureElements()
            ' Specifying the Measure name
            measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})
            Dim dimensionElementRow As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementRow.Name = "Date"
            ' Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
            ''' Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn)
            ''' Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn)
            ''' Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow)
            Return olapReport
        End Function
    End Class
End Namespace
	
{% endhighlight %}

{% endtabs %}

Run the application and the following output will be generated.                                                    

![](Getting-Started_images/Getting-Started_img2.png)
   
## Through Expression Blend

Open the Blend for Visual Studio and navigate to File > New project > WPF > WPF Application to create a new WPF application.

Select the **Project** tab available in the left corner of the Blend IDE. Right-click on **References** and select **Add Reference**. Now browse and add the following assemblies to the project.

   * Syncfusion.Gauge.WPF
   * Syncfusion.Core
   * Syncfusion.Olap.Base
   * Syncfusion.OlapGauge.WPF
   * Syncfusion.OlapShared.WPF
   * Syncfusion.Shared.WPF
   
N> You can also get the assemblies by browsing to the Default Assembly Location {System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\ {version number} \precompiledassemblies\ {version number} \ {framework version} \

On adding the above assemblies, the OlapGauge control will be added under the **Assets** tab automatically. Now choose the **Assets** tab, drag and drop the OlapGauge to the designer.

![](Getting-Started_images/Getting-Started_img3.png)

Add a **Name** to the OlapGauge component for accessing it through code-behind as shown in the following code sample.
   
{% highlight xaml %}
 
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="SampleApplication.MainWindow"
    Title="MainWindow" Height="350" Width="525">
    <Grid>
        <syncfusion:OlapGauge x:Name="olapGauge" HorizontalAlignment="Left" VerticalAlignment="Top"/>
    </Grid>
</Window>
				
{% endhighlight %}

Include the following namespaces in the code-behind for using OlapReport and OlapDataManger in the application.

   * Syncfusion.Olap.Reports
   * Syncfusion.Olap.Manager

{% tabs %}

{% highlight c# %}

using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;

namespace SampleApplication
{
    public partial class MainWindow : SampleWindow
    {
        private string _connectionString;
        private OlapDataManager _olapDataManager;
        public MainWindow()
        {  
            InitializeComponent();
            _connectionString = " Enter a valid connection string ";
            //Connection string is passed to OlapDataManager as an argument
            _olapDataManager = new OlapDataManager(_connectionString);
            //A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport());
            // Finally OlapGauge gets the information from the OlapDataManager
            this.olapGauge.OlapDataManager = _olapDataManager;
            this.olapGauge.DataBind();
        }
             
        /// <summary>
        /// Defining OlapReport with Dimension and Measure
        /// </summary>
        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            // Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works";
            DimensionElement dimensionElementColumn = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer";
            // Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country");
            MeasureElements measureElementColumn = new MeasureElements();
            //Specifying the Measure name
            measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
            DimensionElement dimensionElementRow = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementRow.Name = "Date";
            // Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
            ///Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn);
            ///Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn);
            ///Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow);
            return olapReport;
        }
    }
}
	
{% endhighlight %}

{% highlight vbnet %}

Imports Syncfusion.Olap.Manager
Imports Syncfusion.Olap.Reports
Namespace SampleApplication
    Partial Public Class MainWindow Inherits SampleWindow
        Private _connectionString As String
        Private _olapDataManager As OlapDataManager
        Public Sub New()
            InitializeComponent()
            _connectionString = "Enter a valid connection string"
            ' Connection string is passed to OlapDataManager as an argument
            _olapDataManager = New OlapDataManager(_connectionString)
            ' A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport())
            ' Finally OlapGauge gets the information from the OlapDataManager 
            Me.olapGauge.OlapDataManager = _olapDataManager
            Me.olapGauge.DataBind()
        End Sub
    
    	''' <summary>
        ''' Defining OlapReport with Dimension and Measure
        ''' </summary>
        Private Function CreateOlapReport() As OlapReport
            Dim olapReport As OlapReport = New OlapReport()
            ' Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works"
            Dim dimensionElementColumn As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer"
            ' Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country")
            Dim measureElementColumn As MeasureElements = New MeasureElements()
            ' Specifying the Measure name
            measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})
            Dim dimensionElementRow As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementRow.Name = "Date"
            ' Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
            ''' Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn)
            ''' Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn)
            ''' Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow)
            Return olapReport
        End Function
    End Class
End Namespace
	
{% endhighlight %}

{% endtabs %}

Run the application and the following output will be generated.

![](Getting-Started_images/Getting-Started_img4.png)

## Through Code-Behind

Open the Visual Studio IDE and navigate to File > New > Project > WPF Application (inside Visual C# Templates) to create a new WPF application.

To add the dependency assemblies within the application, right-Click on **References** and select **Add Reference**. Then add the following Syncfusion assemblies manually to the project from the installed location.

   * Syncfusion.Gauge.WPF
   * Syncfusion.Core
   * Syncfusion.Olap.Base
   * Syncfusion.OlapGauge.WPF
   * Syncfusion.OlapShared.WPF
   * Syncfusion.Shared.WPF
   
N> You can also get the assemblies by browsing to the Default Assembly Location {System Drive}:\Program Files (x86)\Syncfusion\Essential Studio\ {version number} \precompiledassemblies\ {version number} \ {framework version}\

Include the following namespaces in code-behind for using OlapGauge, OlapReport and OlapDataManger in the application.

   * Syncfusion.Olap.Reports
   * Syncfusion.Olap.Manager
   * Syncfusion.Windows.Gauge.Olap

{% tabs %}
 
{% highlight c# %}

using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using Syncfusion.Windows.Gauge.Olap;

namespace SampleApplication
{
    public partial class MainWindow : SampleWindow
    {
        private string _connectionString;
        private OlapDataManager _olapDataManager;
        public MainWindow()
        {  
            InitializeComponent();
            OlapGauge olapGauge = new OlapGauge();
            _connectionString = " Enter a valid connection string ";
            //Connection string is passed to OlapDataManager as an argument
            _olapDataManager = new OlapDataManager(_connectionString);
            //A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport());
            // Finally OlapGauge gets the information from the OlapDataManager
            this.olapGauge.OlapDataManager = _olapDataManager;
            this.olapGauge.DataBind();
            //OlapGauge added to the Main Window Grid region.
            grid.Children.Add(olapGauge);
        }
             
        /// <summary>
        /// Defining OlapReport with Dimension and Measure
        /// </summary>
        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            // Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works";
            DimensionElement dimensionElementColumn = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer";
            // Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country");
            MeasureElements measureElementColumn = new MeasureElements();
            //Specifying the Measure name
            measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });
            DimensionElement dimensionElementRow = new DimensionElement();
            // Specifying the name of the Dimension
            dimensionElementRow.Name = "Date";
            // Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
            ///Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn);
            ///Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn);
            ///Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow);
            return olapReport;
        }
	}
} 
	
{% endhighlight %}

{% highlight vbnet %}
				
Imports Syncfusion.Olap.Manager
Imports Syncfusion.Olap.Reports
Imports Syncfusion.Windows.Gauge.Olap
Namespace SampleApplication
    Partial Public Class MainWindowInherits SampleWindow
        Private _connectionString As String
        Private _olapDataManager As OlapDataManager
        Public Sub New()
            InitializeComponent()
            Dim olapGauge As New OlapGauge()
            _connectionString = "Enter a valid connection string"
            ' Connection string is passed to OlapDataManager as an argument
            _olapDataManager = New OlapDataManager(_connectionString)
            ' A default OlapReport is set to OlapDataManager
            _olapDataManager.SetCurrentReport(CreateOlapReport())
            ' Finally OlapGauge gets the information from the OlapDataManager
            Me.olapGauge.OlapDataManager = _olapDataManager
            Me.olapGauge.DataBind()
            ' OlapGauge added to the Main Window Grid region.
            grid.Children.Add(olapGauge)
        End Sub

        ''' <summary>
        ''' Defining OlapReport with Dimension and Measure
        ''' </summary>
        Private Function CreateOlapReport() As OlapReport
            Dim olapReport As OlapReport = New OlapReport()
            ' Setting the Cube name
            olapReport.CurrentCubeName = "Adventure Works"
            Dim dimensionElementColumn As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementColumn.Name = "Customer"
            ' Specifying the Hierarchy and Level name
            dimensionElementColumn.AddLevel("Customer Geography", "Country")
            Dim measureElementColumn As MeasureElements = New MeasureElements()
            ' Specifying the Measure name
            measureElementColumn.Elements.Add(New MeasureElement With {.Name = "Internet Sales Amount"})
            Dim dimensionElementRow As DimensionElement = New DimensionElement()
            ' Specifying the name of the Dimension
            dimensionElementRow.Name = "Date"
            ' Specifying the Hierarchy and Level name
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year")
            ''' Adding Dimension in column axis
            olapReport.CategoricalElements.Add(dimensionElementColumn)
            ''' Adding Measure in column axis
            olapReport.CategoricalElements.Add(measureElementColumn)
            ''' Adding Dimension in row axis
            olapReport.SeriesElements.Add(dimensionElementRow)
            Return olapReport
        End Function
    End Class
End Namespace
				
{% endhighlight %}

{% endtabs %}
 
Run the application and the following output will be generated.                                     

![](Getting-Started_images/Getting-Started_img5.png)

   
