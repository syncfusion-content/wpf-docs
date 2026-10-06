---
layout: post
title: Getting Started with Syncfusion® A2UI for WPF | Syncfusion®
description: Step-by-step guide to install the Syncfusion® A2UI for WPF package and render your first A2UI v0.9 surface as a Syncfusion® WPF control.
control: A2UI Getting Started
platform: wpf
documentation: ug
---

# Getting Started with Syncfusion® A2UI for WPF

This section explains the steps to add and configure the [Syncfusion® A2UI for WPF](https://a2ui.org/specification/v0.9-a2ui/) package in a WPF application. Follow the steps below to integrate the A2UI renderer and render A2UI v0.9 content using Syncfusion® WPF controls.

The Syncfusion® A2UI for WPF package converts streamed [A2UI v0.9](https://a2ui.org/specification/v0.9-a2ui/) messages into a `SurfaceModel` that is rendered as Syncfusion® WPF controls - **DataGrid**, **SfChart**, **Scheduler**, **CalendarEdit**, **Syntax Editor**, **PdfViewer**, **SfTreeView**, **SfMap**, **Diagram**, **DockingManager**, **Ribbon**, **SfGantt**, and more.

The runtime is composed of two NuGet packages:

- `Syncfusion.A2UI.Core` - the framework-agnostic A2UI v0.9 engine.
- `Syncfusion.A2UI.WPF` - the WPF renderer that adds Syncfusion® WPF control adapters on top of the engine. When you call `SyncfusionWpfCatalogBuilder.BuildRegistry()` it transitively brings in every Syncfusion® WPF control package the renderers depend on (`Syncfusion.Shared.WPF`, `Syncfusion.Tools.WPF`, `Syncfusion.SfInput.WPF`, `Syncfusion.SfGrid.WPF`, `Syncfusion.SfChart.WPF`, `Syncfusion.SfScheduler.WPF`, `Syncfusion.SfDiagram.WPF`, `Syncfusion.SfMaps.WPF`, `Syncfusion.SfImageEditor.WPF`, `Syncfusion.SfHeatMap.WPF`, `Syncfusion.SfTreeView.WPF`, `Syncfusion.Edit.WPF`, `Syncfusion.PdfViewer.WPF`, `Syncfusion.Gantt.WPF`, and more).

> Syncfusion® A2UI for WPF is currently in **preview (beta)** and will be published on NuGet under the package `Syncfusion.A2UI.WPF` (with `Syncfusion.A2UI.Core` as a transitive dependency).

{% tabcontents %}
{% tabcontent Visual Studio %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) or later.
2. Set up a WPF environment with Visual Studio 2022 v17.8 or later.

## Step 1: Create a new WPF project

1. Go to **File > New > Project** and choose the **WPF App** template (C#).
2. Name the project and choose a location. Then, click **Next**.
3. Select the .NET framework version and click **Create**.

## Step 2: Install the Syncfusion<sup>®</sup> WPF A2UI NuGet package

1. In **Solution Explorer**, right-click the project and choose **Manage NuGet Packages**.
2. Search for `Syncfusion.A2UI.WPF` and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

{% endtabcontent %}
{% tabcontent Visual Studio Code %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) or later.
2. Set up a WPF environment with Visual Studio Code.
3. Ensure that the .NET desktop workloads are installed and configured as described [here](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio).

## Step 1: Create a new WPF project

1. Open the Command Palette by pressing **Ctrl+Shift+P** and type **.NET:New Project** and press Enter.
2. Choose the **WPF App** template.
3. Select the project location, type the project name and press Enter.
4. Then choose **Create project**.

## Step 2: Install the Syncfusion<sup>®</sup> WPF A2UI NuGet package

1. Press <kbd>Ctrl</kbd> + <kbd>`</kbd> to open the integrated terminal in Visual Studio Code.
2. Ensure you are in the project root directory where your .csproj file is located.
3. Run the command `dotnet add package Syncfusion.A2UI.WPF` to install the Syncfusion<sup>®</sup> A2UI for WPF package.
4. To ensure all dependencies are installed, run `dotnet restore`.

{% endtabcontent %}
{% tabcontent JetBrains Rider %}

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) or later.
2. Set up a WPF environment with JetBrains Rider 2024.3 or later.
3. Make sure the .NET desktop workloads are installed and configured as described [here](https://www.jetbrains.com/help/rider/Get_started_with_net_desktop_apps.html).

## Step 1: Create a new WPF project

1. Go to **File > New Solution,** Select .NET (C#) and choose the **WPF Application** template.
2. Enter the Project Name, Solution Name, and Location.
3. Select the .NET framework version and click Create.

## Step 2: Install the Syncfusion<sup>®</sup> WPF A2UI NuGet package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for `Syncfusion.A2UI.WPF` and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored. If not, open the Terminal in Rider and manually run: `dotnet restore`.

{% endtabcontent %}
{% endtabcontents %}

> The Syncfusion® WPF control packages the renderer depends on (`Syncfusion.Shared.WPF`, `Syncfusion.Tools.WPF`, `Syncfusion.SfInput.WPF`, `Syncfusion.SfGrid.WPF`, `Syncfusion.SfChart.WPF`, `Syncfusion.SfScheduler.WPF`, `Syncfusion.SfDiagram.WPF`, `Syncfusion.SfMaps.WPF`, `Syncfusion.SfImageEditor.WPF`, `Syncfusion.SfHeatMap.WPF`, `Syncfusion.SfTreeView.WPF`, `Syncfusion.Edit.WPF`, `Syncfusion.PdfViewer.WPF`, `Syncfusion.Gantt.WPF`, etc.) come in transitively from `Syncfusion.A2UI.WPF`. No separate `dotnet add package` is needed. See [Supported Components](./supported-components) for the full list of control families the agent can render.

## Register the A2UI catalog

Open **App.xaml.cs** and build the registry, catalog, and host before the application starts. The WPF renderer does not use a DI-aware `MauiAppBuilder`; the WPF assembly exposes the same building blocks as standalone types that you wire in the application startup path.

{% tabs %}
{% highlight C# %}

using Syncfusion.A2UI.Core;
using syncfusion.a2ui.wpf.Catalog;
using syncfusion.a2ui.wpf.Hosting;
using syncfusion.a2ui.wpf.SyncfusionComponents;

// Syncfusion WPF control adapters (SfDataGrid, SfChart, ...)
var syncfusionRegistry = SyncfusionWpfCatalogBuilder.BuildRegistry();

// Catalog object for the MessageProcessor (schemas + WireFunctions).
var catalog = SyncfusionCatalogFactory.Create();

// MessageProcessor + SurfaceModel live in Syncfusion.A2UI.Core.
var processor = new MessageProcessor(model: new SurfaceModel(), catalog: catalog);

// SurfaceHost owns the registry and per-surface events.
var host = new SurfaceHost(syncfusionRegistry);

{% endhighlight %}
{% endtabs %}

> The A2UI v0.9 `MessageProcessor` and `SurfaceModel` types are part of `Syncfusion.A2UI.Core` and expose the four-message life cycle (`createSurface`, `updateComponents`, `updateDataModel`, `deleteSurface`). `A2uiSurface` and `SurfaceHost` consume the resulting `SurfaceModel`.

## Register the Syncfusion® license key

The Syncfusion® WPF components require a valid license key to be registered before they render without a trial-license. The A2UI adapters call into the same components under the hood, so a registered key is required even when the UI is generated by an agent.

For instructions on generating and registering a license key, see [Register License Key in a WPF application](https://help.syncfusion.com/wpf/licensing/how-to-register-in-an-application).

## Import the A2UI namespace

Add the following namespace in your XAML or C#.
 
{% tabs %}
{% highlight XAML %}
 
xmlns:a2ui="clr-namespace:syncfusion.a2ui.wpf.V09;assembly=Syncfusion.A2UI.WPF"
 
{% endhighlight %}
{% highlight C# %}
 
using System.Text.Json;
using Syncfusion.A2UI.Core;
using Syncfusion.A2UI.Core.Common;
using Syncfusion.A2UI.Core.Serialization;
using syncfusion.a2ui.wpf.Hosting;
using syncfusion.a2ui.wpf.V09;
 
{% endhighlight %}
{% endtabs %}

## Render your first WPF A2UI surface

Open **MainWindow.xaml** and add an `<a2ui:A2uiSurface>` control to the visual tree.

{% tabs %}
{% highlight XAML hl_lines="6" %}

<Window x:Class="A2uiDemo.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:a2ui="clr-namespace:syncfusion.a2ui.wpf.V09;assembly=Syncfusion.A2UI.WPF"
        Title="Syncfusion A2UI for WPF" Height="600" Width="900">
    <Grid>
        <a2ui:A2uiSurface x:Name="OrdersSurface" />
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

using System.Text.Json;
using Syncfusion.A2UI.Core;
using Syncfusion.A2UI.Core.Common;
using Syncfusion.A2UI.Core.Serialization;

 public partial class MainWindow : Window
 {
    private readonly MessageProcessor _processor;
    public MainWindow(MessageProcessor processor)
    {
        InitializeComponent();
        _processor = processor;
    }
 
    private void Window_Loaded(object sender, RoutedEventArgs e)
    {
        try { _processor.Model.DeleteSurface("orders"); } catch { /* surface did not exist */ }
        var messages = A2uiJson.ParseMessages(JsonDocument.Parse(Json).RootElement);
        _processor.ProcessMessages(messages);
        var surface = _processor.Model.GetSurface("orders");
        OrdersSurface.Surface = surface;
    }

private const string Json = """
{
  "version": "v0.9",
  "messages": [
    { "version": "v0.9", "createSurface": { "surfaceId": "orders", "catalogId": "syncfusion-a2ui-catalog", "sendDataModel": true } },
    { "version": "v0.9", "updateDataModel": {
       "surfaceId": "orders",
        "path": "/orders",
        "value": [
          { "OrderID": 10248, "CustomerID": "VINET",  "Freight":  32.38, "OrderDate": "1996-07-04", "ShipCountry": "France"     },
          { "OrderID": 10249, "CustomerID": "TOMSP",  "Freight":  11.61, "OrderDate": "1996-07-05", "ShipCountry": "Germany"    },
          { "OrderID": 10250, "CustomerID": "HANAR",  "Freight":  65.83, "OrderDate": "1996-07-08", "ShipCountry": "Brazil"     },
          { "OrderID": 10251, "CustomerID": "VICTE",  "Freight":  41.34, "OrderDate": "1996-07-08", "ShipCountry": "France"     },
          { "OrderID": 10252, "CustomerID": "SUPRD",  "Freight":  51.30, "OrderDate": "1996-07-09", "ShipCountry": "Belgium"    },
          { "OrderID": 10253, "CustomerID": "HANAR",  "Freight":  58.17, "OrderDate": "1996-07-10", "ShipCountry": "Brazil"     },
          { "OrderID": 10254, "CustomerID": "CHOPS",  "Freight":  22.98, "OrderDate": "1996-07-11", "ShipCountry": "Switzerland"},
          { "OrderID": 10255, "CustomerID": "RICSU",  "Freight": 148.33, "OrderDate": "1996-07-12", "ShipCountry": "Switzerland"},
          { "OrderID": 10256, "CustomerID": "WELLI",  "Freight":  13.97, "OrderDate": "1996-07-15", "ShipCountry": "Brazil"     },
          { "OrderID": 10257, "CustomerID": "HILAA",  "Freight":  81.91, "OrderDate": "1996-07-16", "ShipCountry": "Venezuela"  },
          { "OrderID": 10258, "CustomerID": "ERNSH",  "Freight": 140.51, "OrderDate": "1996-07-17", "ShipCountry": "Austria"    },
          { "OrderID": 10259, "CustomerID": "CENTC",  "Freight":   3.25, "OrderDate": "1996-07-18", "ShipCountry": "Mexico"     },
          { "OrderID": 10260, "CustomerID": "OTTIK",  "Freight":  55.09, "OrderDate": "1996-07-19", "ShipCountry": "Germany"    },
          { "OrderID": 10261, "CustomerID": "QUEDE",  "Freight":   3.05, "OrderDate": "1996-07-19", "ShipCountry": "Brazil"     },
          { "OrderID": 10262, "CustomerID": "RATTC",  "Freight":  48.29, "OrderDate": "1996-07-22", "ShipCountry": "USA"        }
        ]
    }},

   { "version": "v0.9", "updateDataModel": {
      "surfaceId": "orders",
      "path": "/selectedRowJson",
      "value": ""
   }},

   { "version": "v0.9", "updateComponents": {
      "surfaceId": "orders",
      "components": [
      {
        "id": "root",
        "component": "Column",
        "children": ["grid", "selected-json"]
      },
      {
        "id": "grid",
        "component": "SyncfusionDataGrid",
        "dataSource": { "path": "/orders" },
        "columns": [
          { "mappingName": "OrderID", "headerText": "Order ID", "textAlign": "end", "format": "N0" },
          { "mappingName": "CustomerID", "headerText": "Customer" },
          { "mappingName": "Freight", "headerText": "Freight", "textAlign": "end", "format": "C2" },
          { "mappingName": "OrderDate", "headerText": "Order Date" },
          { "mappingName": "ShipCountry", "headerText": "Ship Country" }
        ],
        "selectionMode": "single",
        "columnWidthMode": "auto"
    },
    {
      "id": "selected-json",
      "component": "Text",
      "text": { "path": "/selectedRowJson" },
      "variant": "caption"
    }
   ]
  }}
 ]
}
""";

{% endhighlight %}

{% highlight c# tabtitle="App.xaml.cs" hl_lines="3 4 5 6 7 8" %}

  public partial class App : Application
  {
      private readonly MessageProcessor _processor;
      private readonly SurfaceHost _host;

      public App()
      {
          var catalog = SyncfusionCatalogFactory.Create();
          _processor = new MessageProcessor(new SurfaceModel(), catalog);
          var registry = SyncfusionWpfCatalogBuilder.BuildRegistry();
          _host = new SurfaceHost(registry);
      }

      protected override void OnStartup(StartupEventArgs e)
      {
          base.OnStartup(e);
          var window = new MainWindow(_processor);
          window.Show();
      }
  }

{% endhighlight %}
{% endtabs %}

The window renders a Syncfusion® WPF `SfDataGrid` populated with sample `Orders` rows (Order ID, Customer, Freight, Order Date, Ship Country). The grid enables single-column sorting, filtering, grouping, single-row selection, alternating rows, and grid lines - all driven from a static A2UI v0.9 JSON message list. No agent is involved.

> In production, replace the embedded JSON with messages streamed from an [A2UI v0.9-compatible agent](https://a2ui.org/specification/v0.9-a2ui/). See [AI Integration](./ai-integration) for the agent round-trip pattern.

## See also

- [Overview](./overview)
- [AI Integration](./ai-integration)
- [Supported Components](./supported-components)
- [A2UI v0.9 protocol](https://a2ui.org/specification/v0.9-a2ui/)
