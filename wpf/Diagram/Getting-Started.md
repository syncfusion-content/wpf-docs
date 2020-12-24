---
layout: post
title: Getting started with Syncfusion Essential Diagram for WPF.
description: Getting started walk through how to integrate SfDiagram into an application and how to create your first Flow Diagram and Organizational Chart Diagram
platform: wpf
control: SfDiagram
documentation: ug
---

# Getting Started in WPF Diagram (SfDiagram)

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfdiagram) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link:
[How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages)


The following section helps you to build your application with SfDiagram.

## Creating the project

Create new WPF project using Visual Studio. For more [details](https://msdn.microsoft.com/en-IN/library/bb546958(v=vs.90)).

### Adding control via Designer

SfDiagram control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

![DiagramfromDesigner](Getting-Started_images\DiagramfromDesigner.png)

### Adding control manually in XAML

To add control manually in XAML, do the following steps:

1. Add the following required assembly reference to the project, Syncfusion.SfDiagram.WPF .
2. Import Syncfusion WPF schema  http://schemas.syncfusion.com/wpf or SfDiagram control namespace  Syncfusion.UI.Xaml.Diagram in XAML page.
3. Declare SfDiagram control in XAML page.

N> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your WPF application to use Syncfusion components.
    
{% tabs %}
{% highlight xaml %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:SfDiagram_WPF"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="SfDiagram_WPF.MainWindow"
        mc:Ignorable="d" Title="MainWindow" Height="350" Width="525">
    <Grid>
        <!--Initializes the SfDiagram in XMAL window-->
        <syncfusion:SfDiagram x:Name="diagram"/>
    </Grid> 
</Window>

{% endhighlight %}

{% endtabs %}

### Adding control manually in C#

To add control manually in C#, do the following steps:

1. Add the following required assembly references to the project, Syncfusion.SfDiagram.WPF.
2. Import SfDiagram namespace Syncfusion.UI.Xaml.Diagram.
3. Create SfDiagram control instance and add it to the Grid.

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Diagram;

namespace SfDiagram_WPF
{   
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            // Initializes the SfDiagram
            SfDiagram diagram=new SfDiagram();
            Root_Grid.Children.Add(diagram);
        }
    }
}

{% endhighlight %}

{% endtabs %}

## Basic Diagram elements

* **Node:** Visualizes any graphical object using nodes, which can also be arranged and manipulated on a diagram page.
* **Connector:** Represents the relationship between two nodes. Four types of connectors provided as follows:

       1) Orthogonal
       2) Bezier
       3) Straight
       4) Cubic Bezier

* **Port:** Acts as the connection points of node or connector and allows you to create connections with only specific points. 
* **Annotation:** Shows additional information by adding text or labels on nodes and connectors. 

## Flow chart

Let us create a simple flow chart using SfDiagram.

### Initialize the Diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram in XAML as shown in the following code example.

{% tabs %}

{% highlight xaml %}
  
<!--Initializes the SfDiagram in XMAL window--> 
<syncfusion:SfDiagram x:Name="diagram"/>

{% endhighlight %}

{% highlight c# %}

//Initializes the SfDiagram in C#

SfDiagram diagram =new SfDiagram();

{% endhighlight %} 

{% endtabs %}

### Initialize nodes and connectors

To initialize the nodes and connectors properties of the SfDiagram, the Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. 
The Connectors property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfDiagram.Nodes>
   <!--Observable Collection of NodeViewModel-->
   <syncfusion:NodeCollection/>
</syncfusion:SfDiagram.Nodes>

<syncfusion:SfDiagram.Connectors>
   <!--Observable Collection of ConnectorViewModel-->
   <syncfusion:ConnectorCollection/>
</syncfusion:SfDiagram.Connectors>

{% endhighlight %}

{% highlight c# %}

//Initialize Nodes with Observable Collection of NodeViewModel.
diagram.Nodes = new NodeCollection();

//Initialize Connectors with Observable Collection of ConnectorViewModel
diagram.Connectors = new ConnectorCollection();

{% endhighlight %}       

{% endtabs %}

### Add nodes

Let us create and add a NodeViewModel with height, width, shape, shape style, specific position, size, and annotation.

#### Creating a node

Creating NodeViewModel with specified height and width at a specific position.

{% tabs %}
{% highlight xaml %}
<syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" 
                          OffsetX="300" OffsetY="60"/>  
{% endhighlight %}
{% highlight c# %}
NodeViewModel Begin = new NodeViewModel()
{
    ID = "Begin", 
    UnitWidth = 120, 
    UnitHeight = 40, 
    OffsetX = 300, 
    OffsetY = 60,
};
{% endhighlight %}
{% endtabs %}

#### Adding shape and style to node

We have provided set of basic shapes for Diagram as ResourceDictionary. To use the built-in shapes, Shapes dictionary should be merged in the application.  
Please refer to [Shapes](/wpf/sfdiagram/shapes) to know about built-in Shapes.
 
{% tabs %}
{% highlight xaml %}  
<ResourceDictionary>
    <ResourceDictionary.MergedDictionaries>
        <!--Initialize Shapes-->
        <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
    </ResourceDictionary.MergedDictionaries>
    <!--Style for Shape of the Node-->
    <Style TargetType="Path" x:Key="ShapeStyle">
        <Setter Property="Fill" Value="#FF5B9BD5"/>
        <Setter Property="Stretch" Value="Fill"/>
        Setter Property="Stroke" Value="#FFEDF1F6"/>
    </Style>
            
    <!--To apply Style for NodeViewModel-->
    <Style TargetType="syncfusion:Node">
        <Setter Property="ShapeStyle" Value="{StaticResource ShapeStyle}"></Setter>
    </Style>
</ResourceDictionary>

<syncfusion:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" 
                          Shape="{StaticResource Ellipse}" 
                          UnitHeight="40" UnitWidth="120"/>
{% endhighlight %}

{% highlight c# %} 
NodeViewModel Begin = new NodeViewModel()
{
    ID = "Begin", UnitWidth = 120, UnitHeight = 40, OffsetX = 300, OffsetY = 60,
    //Specify shape to the Node from built-in Shape Dictionary
    Shape = this.Resources["Ellipse"],
    //Apply style to Shape
    ShapeStyle = this.Resources["ShapeStyle"] as Style,
};
{% endhighlight %}
{% endtabs %}

Now, the node will be as follows.
   
![AddNode](Getting-Started_images\addNode.png)
   
N> ID sets for each node to identify nodes easily while setting connectors.
   
#### Adding annotation to node
   
To initialize the Annotation property of the node and connector, it is assigned with the annotation collection, that is, ObservableCollection of the IAnnotation.

Now add the Annotation content to Node.

{% tabs %}
{% highlight xaml %}
<syncfusion:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" 
                          Shape="{StaticResource Ellipse}" 
                          UnitHeight="40" UnitWidth="120">
    <syncfusion:NodeViewModel.Annotations>
        <!--Observable Collection of AnnotationEditorViewModel-->
        <syncfusion:AnnotationCollection>
            <syncfusion:AnnotationEditorViewModel Content="Begin"/>
        </syncfusion:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>       
{% endhighlight %}
{% highlight c# %}
// Creating the NodeViewModel  
NodeViewModel Begin = new NodeViewModel()
{
    ID = "Begin", 
    UnitWidth = 120, 
    UnitHeight = 40, 
    OffsetX = 300, 
    OffsetY = 60,
    //Specify shape to the Node from built-in Shape Dictionary
    Shape = this.Resources["Ellipse"],
    //Apply style to Shape
    ShapeStyle = this.Resources["ShapeStyle"] as Style,
    Annotations = new AnnotationCollection()
    {
        new AnnotationEditorViewModel()
        {
            Content="Begin",
        }
    }
};
      
//Add Node to Nodes property of the Diagram
(diagram.Nodes as NodeCollection).Add(Begin);
      
{% endhighlight %}
{% endtabs %}

Now, the node will be as follows.
 
![NodeAnnotation](Getting-Started_images\nodeAnnotation.PNG)

N> `Annotations` property is a collection, which indicates that more than one Annotation can be added to a Node and Connector. By default, `Annotations` property of Node and Connector is null.
 
### Nodes for flow diagram

You can add multiple nodes with different shapes into diagram as NodeViewModel.

{% tabs %}
{% highlight xaml %}
<syncfusion:NodeCollection>
    <!--Begin-->
    <syncfusion:NodeViewModel ID="Begin" OffsetX="300" OffsetY="60" 
                              Shape="{StaticResource Ellipse}" 
                              UnitHeight="40" UnitWidth="120">
        <syncfusion:NodeViewModel.Annotations>
            <!--Observable Collection of AnnotationEditorViewModel-->
            <syncfusion:AnnotationCollection>
                <syncfusion:AnnotationEditorViewModel Content="Begin"/>
            </syncfusion:AnnotationCollection>
        </syncfusion:NodeViewModel.Annotations>
    </syncfusion:NodeViewModel>
    <!--Process-->
    <syncfusion:NodeViewModel ID="Process" UnitHeight="60" UnitWidth="120" 
                              OffsetX="300" OffsetY="140" 
                              Shape="{StaticResource PredefinedProcess}">
        <syncfusion:NodeViewModel.Annotations>
            <syncfusion:AnnotationCollection>
                <syncfusion:AnnotationEditorViewModel Content="Process"/>
            </syncfusion:AnnotationCollection>
        </syncfusion:NodeViewModel.Annotations>
    </syncfusion:NodeViewModel>
    <!--End-->
    <syncfusion:NodeViewModel ID="End" UnitHeight="40" UnitWidth="40" 
                              OffsetX="300" OffsetY="225" 
                              Shape="{StaticResource Ellipse}">
        <syncfusion:NodeViewModel.Annotations>
            <syncfusion:AnnotationCollection>
                <syncfusion:AnnotationEditorViewModel Content="End"/>
            </syncfusion:AnnotationCollection>
        </syncfusion:NodeViewModel.Annotations>
    </syncfusion:NodeViewModel>
</syncfusion:NodeCollection>
{% endhighlight %}
{% highlight c# %}
//Create Begin node
NodeViewModel Begin = AddNode(300, 60, 120, 40, "Begin", "Ellipse");
//Create Process node
NodeViewModel Process = AddNode(300, 140, 120, 60, "Process", "PredefinedProcess");
//Creae End node
NodeViewModel End = AddNode(300, 225, 40, 40, "End", "Ellipse");

//Add Node to Nodes property of the Diagram
(diagram.Nodes as NodeCollection).Add(Begin);
(diagram.Nodes as NodeCollection).Add(Process);
(diagram.Nodes as NodeCollection).Add(End);
  
//Creating NodeViewModel
public NodeViewModel AddNode(double offsetX, double offsetY, double width, double height, string text, string shape)
{
    NodeViewModel node = new NodeViewModel();
    node.ID = text;
    node.OffsetX = offsetX;
    node.OffsetY = offsetY;
    node.UnitHeight = height;
    node.UnitWidth = width;
    //Specify shape to the Node from built-in Shape Dictionary
    node.Shape = this.Resources[shape];
    //Apply style to Shape
    node.ShapeStyle = this.Resources["ShapeStyle"] as Style;
    node.Annotations = new AnnotationCollection()
    {
        new AnnotationEditorViewModel()
        {
            Content=text,
        },
    };
    return node;
 }
{% endhighlight %}
{% endtabs %}

Finally, all the nodes are added to diagram and they will be as follows.

![CompleteNodes](Getting-Started_images\completeNodes.png)

### Add connectors

Connector is to make connection or link between two nodes, ports, and points.

#### Create connector With source node and target node 

Here, the `SourceNodeID` and `TargetNodeID` properties of the Connector are used. These properties will be assigned with the `ID` property of the node.

{% tabs %}
{% highlight xaml %}
<syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process"/>
{% endhighlight %}
{% highlight c# %}
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNodeID = "Begin",
    TargetNodeID = "Process",
};
{% endhighlight %}
{% endtabs %}

#### Adding connector geometry style

Here, the `ConnectorGeometryStyle` property of the Connector are used to customize the appearance of the line. And, `SourceDecoratorStyle` and `TargetDecoratorStyle` properties are used to customize the appearance of the decorators. 

{% tabs %}
{% highlight xaml %}
<!--Style for TargetDecorator of the Connector-->
<Style TargetType="Path" x:Key="TargetDecoratorStyle">
    <Setter Property="Stroke" Value="Black"/>
    <Setter Property="Stretch" Value="Fill"/>
    <Setter Property="Fill" Value="Black"/>
    <Setter Property="Height" Value="10"/>
    <Setter Property="Width" Value="10"/>
</Style>

<!--Style for Geometry of the Connector-->
<Style TargetType="Path" x:Key="ConnectorGeometryStyle">
    <Setter Property="Stroke" Value="Black" />
    <Setter Property="StrokeThickness" Value="1" />
</Style>
      
<!--To apply Style for ConnectorViewModel-->
<Style TargetType="syncfusion:Connector" >
    <Setter Property="TargetDecoratorStyle" Value="{StaticResource TargetDecoratorStyle}"/>
    <Setter Property="ConnectorGeometryStyle" Value="{StaticResource ConnectorGeometryStyle}"/>
</Style>
{% endhighlight %} 
{% highlight c# %}
ConnectorViewModel connector1 = new ConnectorViewModel()
{
    SourceNodeID = "Begin",
    TargetNodeID = "Process",
    //Apply Style to TargetDecorator
    TargetDecoratorStyle = this.Resources["TargetDecoratorStyle"] as Style,
    //Apply Style to Geometry of the Connector.
    ConnectorGeometryStyle = this.Resources["ConnectorGeometryStyle"] as Style
};
       
//Add Connector to Connectors property of the Diagram
(diagram.Connectors as ConnectorCollection).Add(connector1);
{% endhighlight %}
{% endtabs %}

Now, the output will be as follows.

![NodewithConnector](Getting-Started_images\nodewithConnector.png)
 
### Connectors for flow diagram

Now, you can connect all nodes using ConnectorViewModel.

{% tabs %}
{% highlight xaml %}
<syncfusion:ConnectorCollection>
    <syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process"/>
    <syncfusion:ConnectorViewModel SourceNodeID="Process" TargetNodeID="End"/>
</syncfusion:ConnectorCollection>
{% endhighlight %} 
{% highlight c# %}
//Creating ConnectorViewModel
ConnectorViewModel connector1 = CreateConnector("Begin", "Process");
ConnectorViewModel connector2 = CreateConnector("Process", "End");

//Add Connector to Connectors property of the Diagram
(diagram.Connectors as ConnectorCollection).Add(connector1);
(diagram.Connectors as ConnectorCollection).Add(connector2);
     
//Creating ConnectorViewModel
private ConnectorViewModel CreateConnector(string source, string target)
{
   ConnectorViewModel connector = new ConnectorViewModel()
   {
        SourceNodeID = source,
        TargetNodeID = target,
        //Apply Style to TargetDecorator
        TargetDecoratorStyle = this.Resources["TargetDecoratorStyle"] as Style,
        //Apply Style to Geometry of the Connector.
        ConnectorGeometryStyle = this.Resources["ConnectorGeometryStyle"] as Style
   };
   
   return connector;
 }
{% endhighlight %} 
{% endtabs %}

Now, the output will be as follows.

![CompleteDiagram](Getting-Started_images\completeDiagram.png)
    
[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/GettingStarted/Simple-FlowChart-Creation)

### Flowchart creation using stencil

Let us create a simple flowchart diagram using stencil.

#### Define stencil

`Stencil` is a gallery of reusable symbols and nodes, which can be dragged and dropped onto the diagram surface at any number of times.

{% tabs %}
{% highlight xaml %}
<!--Namespace for stencil-->
xmlns:stencil="clr-namespace:Syncfusion.UI.Xaml.Diagram.Stencil;assembly=Syncfusion.SfDiagram.WPF"

<!--Define the Stencil-->
<stencil:Stencil x:Name="stencil"  ExpandMode="All" 
                 BorderBrush="Black" BorderThickness="0,0,2,0"/>

{% endhighlight %}
{% endtabs %}

#### Define SymbolSource

`SymbolSource` is the property of stencil, which is a collection of objects like symbol, node, connector, and more. Based on the SymbolSource, the Stencil will populate the Symbols. And the `SymbolGroupProvider` groups the symbols into SymbolGroup based on the `MappingName` property.

{% tabs %}
{% highlight xaml %}

<!--Define the Stencil-->
<stencil:Stencil x:Name="stencil"  ExpandMode="All" 
                 BorderBrush="Black" BorderThickness="0,0,2,0">
    <!--Initialize the SymbolSource-->
    <stencil:Stencil.SymbolSource>
        <!--Initialize the SymbolCollection-->
        <local:SymbolCollection>
            <!--Define the DiagramElement-Node-->
            <Syncfusion:NodeViewModel UnitHeight="40" UnitWidth="120" 
                                      Shape="{StaticResource Ellipse}" Key="Nodes">
                <Syncfusion:NodeViewModel.Annotations>
                    <!--Observable Collection of AnnotationEditorViewModel-->
                    <Syncfusion:AnnotationCollection>
                        <Syncfusion:AnnotationEditorViewModel Content="Begin"/>
                    </Syncfusion:AnnotationCollection>
                </Syncfusion:NodeViewModel.Annotations>
            </Syncfusion:NodeViewModel>
            <!--Define the DiagramElement-Connector-->
            <Syncfusion:ConnectorViewModel Key="Connectors"
                                           SourcePoint="100,100" 
                                           TargetPoint="200,200" /> 
        </local:SymbolCollection>
    </stencil:Stencil.SymbolSource>
    <!--Initialize the SymbolGroup-->
    <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
            <!--Map Symbols Using MappingName-->
            <stencil:SymbolGroupProvider MappingName="Key"/>
        </stencil:SymbolGroups>
    </stencil:Stencil.SymbolGroups>
</stencil:Stencil>

<!--Define DiagramControl to drag and drop elements into the diagram-->
<Syncfusion:SfDiagram x:Name="sfdiagram">
    <Syncfusion:SfDiagram.Nodes>
        <Syncfusion:NodeCollection/>
    </Syncfusion:SfDiagram.Nodes>
    <Syncfusion:SfDiagram.Connectors>
        <Syncfusion:ConnectorCollection/>
    </Syncfusion:SfDiagram.Connectors>
</Syncfusion:SfDiagram>
{% endhighlight %}

{% highlight c# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize NodeCollection to SfDiagram
diagram.Nodes = new NodeCollection();
//Initialize ConnectorCollection to SfDiagram
diagram.Connectors = new ConnectorCollection();

//Initialize Stencil and its properties
Stencil stencil = new Stencil();
stencil.ExpandMode = ExpandMode.All;
stencil.BorderBrush = new SolidColorBrush(Colors.Black);
stencil.BorderThickness = new Thickness(0,0,2,0);
          
NodeViewModel node1 = new NodeViewModel()
{
    UnitHeight = 40,
    UnitWidth = 120,
    Shape = this.Resources["Ellipse"],
    Key = "Nodes",
    Annotations = new AnnotationCollection()
    {
        new AnnotationEditorViewModel()
        {
            Content ="Begin"
        }
    }
};

ConnectorViewModel connector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    Key = "Connectors",
    Segments = new ConnectorSegments()
    {
        new StraightSegment()
    }
};

//Initialize collection to hold the symbols
SymbolCollection symbolcollection = new SymbolCollection();
//Add the symbols to the collection
symbolcollection.Add(node1);            
symbolcollection.Add(connector);

//Initialize the SymbolSource
stencil.SymbolSource = symbolcollection;

//Map Symbols Using MappingName
SymbolGroupProvider sgp = new SymbolGroupProvider()
{                
    MappingName = "Key"
};
            
//Initialize SymbolGroup
stencil.SymbolGroups = new SymbolGroups();

//Add the SymbolGroupProvider to SymbolGroup
stencil.SymbolGroups.Add(sgp);


//Add the Diagram and Stencil to Mainwindow grid
RootGrid.Children.Add(stencil);
RootGrid.Children.Add(diagram);

//Position the stencil and Diagram in the Main Grid
stencil.SetValue(Grid.RowProperty, 1);
stencil.SetValue(Grid.ColumnProperty, 0);
diagram.SetValue(Grid.RowProperty, 1);
diagram.SetValue(Grid.ColumnProperty, 1);

public class SymbolCollection:ObservableCollection<object>
{
}
{% endhighlight %}
{% endtabs %}

#### Visualization of stencil elements

Declare the style for node, connector, symbol, and symbol group to visualize the elements in the stencil.

{% tabs %}
{% highlight xaml %}
<ResourceDictionary>
    <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml"/>
    </ResourceDictionary.MergedDictionaries>

    <!--Style for Node-->
    <Style TargetType="Syncfusion:Node">
        <Setter Property="ShapeStyle">
            <Setter.Value>
                <Style TargetType="Path">
                    <Setter Property="Stretch" Value="Fill"></Setter>
                    <Setter Property="Fill" Value="#FF5B9BD5"></Setter>
                </Style>
            </Setter.Value>
        </Setter>
    </Style>

    <!--Style for Connector-->
    <Style TargetType="Syncfusion:Connector">
        <Setter Property="TargetDecoratorStyle">
            <Setter.Value>
                <Style TargetType="Path">
                    <Setter Property="Stretch" Value="Fill"/>
                    <Setter Property="Fill" Value="Black"/>
                    <Setter Property="Stroke" Value="Black"/>
                    <Setter Property="StrokeThickness" Value="1"/>
                </Style>
            </Setter.Value>
        </Setter>
    </Style>
            
    <!--Style for Symbol-->
    <Style TargetType="stencil:Symbol">
        <Setter Property="Width" Value="50"/>
        <Setter Property="Height" Value="50"/>
        <Setter Property="Padding" Value="3" />
        <Setter Property="BorderThickness" Value="1" />
        <Setter Property="Background" Value="Transparent" />
        <Setter Property="BorderBrush" Value="Transparent" />
        <Setter Property="Margin" Value="4"></Setter>
    </Style>

    <!--Style for Symbol Group-->
    <Style TargetType="stencil:SymbolGroup">
        <Setter Property="FontFamily" Value="Regular"/>
        <Setter Property="Background" Value="#ffffff"/>
        <Setter Property="Foreground" Value="#222222"/>
        <Setter Property="FontSize" Value="14"/>
        <Setter Property="HeaderTemplate">
            <Setter.Value>
                <DataTemplate>
                    <stencil:Header>
                        <stencil:Header.Template>
                            <ControlTemplate TargetType="stencil:Header">
                                <Grid>
                                    <Border x:Name="header" Background="#f5f5f5" 
                                            BorderBrush="Black" BorderThickness="1">
                                        <ContentPresenter Margin="10" Content="{Binding}"/>
                                    </Border>
                                </Grid>
                            </ControlTemplate>
                        </stencil:Header.Template>
                    </stencil:Header>
                </DataTemplate>
            </Setter.Value>
        </Setter>
    </Style>
</ResourceDictionary>
    
{% endhighlight %}
{% endtabs %}

The output will be as follows.

![Stencil output](Getting-Started_images\Stencil_output.PNG)

#### Interaction with stencil

We have represented the steps to interact with stencil such as drag and drop elements from stencil to diagram in the following gif.

![StencilDiagram](Getting-Started_images\StencilDiagram.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/GettingStarted/StencilCreation)

For more information about stencil, please [refer](https://help.syncfusion.com/wpf/sfdiagram/stencil#using-diagramelements). 

## Organization layout

SfDiagram provides support to auto-arrange the nodes in the diagram area that is referred as Layout.

#### Business object (employee information)

Define employee information as collection of data. The following code example shows the employee information whose, EmpId is used as an unique identifier and ParentId is used to identify the person to whom an employee report to, in the organization.

{% tabs %}
{% highlight xaml %}
<!--Initializes the DataSource -->
<local:Employees x:Key="employees">
   <local:Employee  EmpId="1" ParentId="" Designation="CEO"/>
   <local:Employee  EmpId="2" ParentId="1" Designation="Project Manager1"/>
   <local:Employee  EmpId="3" ParentId="1" Designation="Project Manager2"/>
   <local:Employee  EmpId="4" ParentId="2" Designation="Engineer1"/>
   <local:Employee  EmpId="5" ParentId="3" Designation="Engineer2"/>  
</local:Employees>
{% endhighlight %}

{% highlight c# %}

private Employees GetData()
{
    Employees data = new Employees();
    data.Add(new Employee() { EmpId = "1", ParentId = "", Designation = "CEO" });
    data.Add(new Employee() { EmpId = "2", ParentId = "1", Designation = "Project Manager1" });
    data.Add(new Employee() { EmpId = "3", ParentId = "1", Designation = "Project Manager2" });
    data.Add(new Employee() { EmpId = "4", ParentId = "2", Designation = "Engineer1" });
    data.Add(new Employee() { EmpId = "5", ParentId = "3", Designation = "Engineer2" });    
    return data;
}

public class Employee
{
    public Employee()
    {

    }
    public string EmpId { get; set; }
    public string ParentId { get; set; }
    public string Designation { get; set; }
}

public class Employees:ObservableCollection<Employee>
{
}

{% endhighlight %}
{% endtabs %}

#### Map DataSource with Diagram

You can configure the above “Employee Information” with diagram, so that the nodes and connectors are automatically generated using the mapping properties. The following code example shows how dataSourceSettings is used to map ID , ParentId and DataSource with property name identifiers for employee information.

{% tabs %}
{% highlight xaml %}

<!--Initializes the DataSourceSettings -->
<Syncfusion:DataSourceSettings x:Key="DataSourcesettings" 
                               DataSource="{StaticResource employees}" 
                               ParentId="ParentId" Id="EmpId" />
    <!--Map the DataSourceSettings class with Diagram-->
    <Syncfusion:SfDiagram x:Name="sfdiagram" 
                          DataSourceSettings="{StaticResource DataSourcesettings}"/>   
</Syncfusion:SfDiagram> 
{% endhighlight %}

{% highlight c# %}

//Initialize SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize NodeCollection to SfDiagram
diagram.Nodes = new NodeCollection();
//Initialize ConnectorCollection to SfDiagram
diagram.Connectors = new ConnectorCollection();
//Initialize DataSourceSettings to SfDiagram
diagram.DataSourceSettings = new DataSourceSettings()
{
    DataSource =GetData(),
    ParentId= "ParentId",
    Id= "EmpId"
};

{% endhighlight %}
{% endtabs %}

#### Rendering layout with DataSource

To create an organizational chart, TreeLayout type should be set to `LayoutType.Organization`. The following code example shows how LayoutManager is used to generate TreeLayout based on the DataSourceSettings of the Diagram.

{% tabs %}
{% highlight xaml %}

<!--Style for Connector-->
<Style TargetType="Syncfusion:Connector">
    <Setter Property="ConnectorGeometryStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="Black"  />
                <Setter Property="StrokeThickness" Value="1" />
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="TargetDecoratorStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="#4f4f4f"  />
                <Setter Property="Stretch" Value="Fill" />
                <Setter Property="Fill" Value="#4f4f4f"  />
                <Setter Property="StrokeThickness" Value="1" />
            </Style>
        </Setter.Value>
    </Setter>
</Style>

<!--Style for Node-->
<Style TargetType="Syncfusion:Node">
    <Setter Property="ContentTemplate">
        <Setter.Value>
            <DataTemplate>
                <Border Background="#FF5B9BD5" BorderBrush="Blue" 
                        Width="120" Height="40" 
                        VerticalAlignment="Center" HorizontalAlignment="Center">
                    <TextBlock Margin="5" TextWrapping="Wrap" FontSize="12" 
                               Foreground="#ffffff" Text="{Binding Path=Designation}" 
                               FontFamily="Segoe UI" VerticalAlignment="Center" 
                               FontWeight="Bold" HorizontalAlignment="Center"/>
                </Border>
            </DataTemplate>
        </Setter.Value>
    </Setter>
</Style>

<!--Initializes the Layout-->
<Syncfusion:DirectedTreeLayout x:Key="treeLayout" Orientation="TopToBottom" 
                               HorizontalSpacing="50" Type="Organization"/>

<!--Initializes the LayoutManager-->
<Syncfusion:LayoutManager x:Key="LayoutManager" Layout="{StaticResource treeLayout}" />

<!--Map the DataSourceSettings and LayoutManager class with Diagram-->
<Syncfusion:SfDiagram x:Name="sfdiagram" 
                      DataSourceSettings="{StaticResource DataSourcesettings}" 
                      LayoutManager="{StaticResource LayoutManager}">
    <Syncfusion:SfDiagram.Nodes>
        <Syncfusion:NodeCollection/>
    </Syncfusion:SfDiagram.Nodes>
    <Syncfusion:SfDiagram.Connectors>
        <Syncfusion:ConnectorCollection/>
    </Syncfusion:SfDiagram.Connectors>
</Syncfusion:SfDiagram>

{% endhighlight %}

{% highlight c# %}

//Initialize LayoutManager to SfDiagram
diagram.LayoutManager = new LayoutManager()
{
    //Initialize Layout for LayoutManager  
    Layout=new DirectedTreeLayout()
    {
        Type=LayoutType.Organization,
        Orientation=TreeOrientation.TopToBottom,
        HorizontalSpacing=50
    }
};
//RootGrid is the instance of the MainWindow Grid
RootGrid.Children.Add(diagram);

{% endhighlight %}
{% endtabs %}

The output will be as follows.

![OrgLayout](Getting-Started_images\orglayout.PNG)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/GettingStarted/Simple-OrganizationLayout-Creation)

For more information about Layout, [refer](https://help.syncfusion.com/wpf/sfdiagram/automatic-layouts)

