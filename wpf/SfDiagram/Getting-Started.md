---
layout: post
title: Getting started with Syncfusion Essential Diagram for WPF.
description: Getting started walk through to create your Organizational Chart Diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

#Getting Started

Getting started with your Essential WPF Diagram is easy. You can start by creating a simple Flow Diagram.

## Initialize the SfDiagram

   * Create new WPF project using Visual Studio. For more [details](https://msdn.microsoft.com/en-IN/library/bb546958(v=vs.90)).
   * Add SfDiagram assembly to your application. 
   * Initialize the diagram.
  
   
**Creating Simple Diagram**

This section demonstrates how to visualize the Employee details in the Organizational Chart arrangement by using the SfDiagram.

###Adding assembly reference   
 
1. Open the Add reference window from your project.
2. Choose Windows > Extensions > Syncfusion.SfDiagram.WPF.

![](Getting-Started_images\Getting_Started_img.png)

###Add SfDiagram from Toolbox

Drag and drop the SfDiagram control from the Toolbox to the XAML Page.

![](Getting-Started_images\Getting_Started_img1.png)

The xmlns name space is added to the MainPage.xaml

![](Getting-Started_images\Getting_Started_img2.png)

##Initialize the diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram to the XAML Page as shown in the following code example.

{% highlight xaml %}

<Grid Background="White">
    <!--Initializes the SfDiagram-->  
    <syncfusion:SfDiagram x:Name="diagram">
    </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

###Initialize nodes and connectors

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connector’s property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% highlight xaml %}

<!--Initializes the NodeCollection-->
<syncfusion:SfDiagram.Nodes>
	<syncfusion:NodeCollection/>
</syncfusion:SfDiagram.Nodes>
<!--Initializes the ConnectorCollection-->
<syncfusion:SfDiagram.Connectors>
	<syncfusion:ConnectorCollection/>
</syncfusion:SfDiagram.Connectors>

{% endhighlight %}

###Default Binding Style

We have exposed the ViewModel of Node and Connector. We have provided the Default Binding Style support, in order to Bind the properties of ViewModel to View.
For more information, refer to [Data Binding](/wpf/sfdiagram/Data-Binding).

##Flow Diagram

###Merge BasicShapes ResourceDictionary
We have provided support for the BasicShapes as ResourceDictionary. So, Merge the BasicShapes ResourceDictionary to the Application.
<ResourceDictionary.MergedDictionaries>               
   <!--Shapes as StaticResource-->
   <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
</ResourceDictionary.MergedDictionaries>

###Create and add Node
Let us create and add a NodeViewModel with specific position, Size, Annotation and Shape.
{% highlight xaml %}
   <!--Create a NodeViewModel with Specific customization option-->
   <syncfusion:NodeViewModel ID="Start" UnitWidth="70" UnitHeight="35" OffsetX="300" OffsetY="50" Shape="{StaticResource Ellipse}">
   <!--Initialize Annotation-->
   <syncfusion:NodeViewModel.Annotations>
   <!--Collection of Annotation-->
   <local:Annotations>
  <!--Create a AnnotationEditorViewModel with Content-->
   <syncfusion:AnnotationEditorViewModel Content="Start"/>
   </local:Annotations>
   </syncfusion:NodeViewModel.Annotations>
  <syncfusion:NodeViewModel>
{% endhighlight %}
           
>N Annotations property is an Collection, which indicates that more than one Annotation can be added to a Node.

Added node will be displayed in diagram as shown below.

![](Getting-Started_images\Getting_Started_flowDiagram_img1.jpeg)

###Connect nodes
    * Create another NodeViewModel with another set of data.
    {% highlight xaml %}
   <!--Start-->
   <syncfusion:NodeViewModel ID="Start" UnitWidth="70" UnitHeight="35" OffsetX="300" OffsetY="50" Shape="{StaticResource Ellipse}">
   <syncfusion:NodeViewModel.Annotations>
   <local:Annotations>
   <syncfusion:AnnotationEditorViewModel Content="Start"/>
   </local:Annotations>
   </syncfusion:NodeViewModel.Annotations>
   </syncfusion:NodeViewModel>

   <!--Read the Number-->
   <syncfusion:NodeViewModel ID="Read" OffsetX="300" UnitWidth="70" UnitHeight="35" OffsetY="120" Shape="{StaticResource Rectangle}">
   <syncfusion:NodeViewModel.Annotations>
   <local:Annotations>
   <syncfusion:AnnotationEditorViewModel Content="Get Number"/>
   </local:Annotations>
   </syncfusion:NodeViewModel.Annotations>
   </syncfusion:NodeViewModel>  
   {% endhighlight %}
    * Connect these two nodes by adding a ConnectorViewModel into Connectors collection with reference to SourceNodeID and TargetNodeID.
   {% highlight xaml %}
   <!--Create a ConnectorViewModel-->
   <syncfusion:ConnectorViewModel SourceNodeID="node1" TargetNodeID="node2"/>
   {% endhighlight %}
    * Connector connects the two nodes as shown below.
    
 ![](Getting-Started_images\Getting_Started_flowDiagram_img2.jpeg)
 
###Common Style for nodes and Connectors
Default values for all Nodes and Connectors can be set using Common Style for Node and Connector. For example if all Nodes have same apperance, we can move such properties into Commom Style.
 {% highlight xaml %}
<!--Common Style for ConnectorViewModel-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
<Setter Property="ShapeStyle">
<Setter.Value>
<Style TargetType="Path">
<Setter Property="Fill" Value="White"></Setter>
<Setter Property="Stroke" Value="Black"></Setter>
<Setter Property="Stretch" Value="Fill"></Setter>
</Style>
</Setter.Value>
</Setter>
</Style>

<!--Common Style for ConnectorViewModel-->
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle}">
<Setter Property="ConnectorGeometryStyle">
<Setter.Value>
<Style TargetType="Path">
<Setter Property="Stroke" Value="Black"></Setter>
</Style>
</Setter.Value>
</Setter>
</Style>
 {% endhighlight %}
                    
###Complete flow diagram

Similarly we can add required Nodes and Connectors to form a complete flow diagram.          

{% highlight xaml %}                
<syncfusion:NodeCollection>
<syncfusion:NodeViewModel ID="Start" UnitWidth="70" UnitHeight="35" OffsetX="300" OffsetY="50" Shape="{StaticResource Ellipse}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="Start"/>
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

<syncfusion:NodeViewModel ID="Read" OffsetX="300" UnitWidth="70" UnitHeight="35" OffsetY="120" Shape="{StaticResource Rectangle}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="Get Number"/>
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

<syncfusion:NodeViewModel ID="Condition" UnitWidth="75" UnitHeight="45" OffsetX="300" OffsetY="210" Shape="{StaticResource Diamond}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="X%2==0 ?" />
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

<syncfusion:NodeViewModel ID="Even" UnitWidth="70" UnitHeight="35" OffsetX="200" OffsetY="310" Shape="{StaticResource PredefinedProcess}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="Even" />
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
<syncfusion:NodeViewModel ID="Odd" UnitWidth="70" UnitHeight="35" OffsetX="400" OffsetY="310" Shape="{StaticResource PredefinedProcess}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="Odd" />
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

<syncfusion:NodeViewModel ID="End" UnitWidth="70" UnitHeight="35" OffsetX="300" OffsetY="410" Shape="{StaticResource Ellipse}">
<syncfusion:NodeViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="End"/>
</local:Annotations>
</syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
</syncfusion:NodeCollection>

<syncfusion:ConnectorCollection>
<syncfusion:ConnectorViewModel SourceNodeID="Start" TargetNodeID="Read"/>
<syncfusion:ConnectorViewModel SourceNodeID="Read" TargetNodeID="Condition"/>
<syncfusion:ConnectorViewModel SourceNodeID="Condition" TargetNodeID="Even">
<syncfusion:ConnectorViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="Yes"></syncfusion:AnnotationEditorViewModel>
</local:Annotations>
</syncfusion:ConnectorViewModel.Annotations>
</syncfusion:ConnectorViewModel>
<syncfusion:ConnectorViewModel SourceNodeID="Condition" TargetNodeID="Odd">
<syncfusion:ConnectorViewModel.Annotations>
<local:Annotations>
<syncfusion:AnnotationEditorViewModel Content="No"></syncfusion:AnnotationEditorViewModel>
</local:Annotations>
</syncfusion:ConnectorViewModel.Annotations>
</syncfusion:ConnectorViewModel>
<syncfusion:ConnectorViewModel SourceNodeID="Even" TargetNodeID="End"/>
<syncfusion:ConnectorViewModel SourceNodeID="Odd" TargetNodeID="End"/>
</syncfusion:ConnectorCollection>
 {% endhighlight %}

Final flow chart will looks as shown below.
 ![](Getting-Started_images\Getting_Started_flowDiagram_img3.jpeg)

##Automatic organization chart
In ‘Flow Diagram’ section we saw how to create a diagram manually, now let us see how to create and position diagram automatically.

Initialize diagram

Initializing diagram is already discussed above > [Initialize the diagram](/wpf/sfdiagram/Getting-Started#Initialize the diagram) section.

###Business object (Employee information)

Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

{% highlight C# %}

//Employee Business Object
public class Employee
{
    public string ParentId { get; set; }
    public string Name { get; set; }
    public string Designation { get; set; }
    public int EmpId { get; set; }
}

//Employee Collection
public class Employees : ObservableCollection<Employee>
{

}

{% endhighlight %}

###Initialize Data

Define Employee Information as a Collection. The following code example shows an employee array whose,
    * Name is used as a unique identifier and
    * ParentId is used to identify the person to whom an employee report to, in the organization.

{% highlight xaml %}

<!-- Initializes the employee colletion-->
<local:Employees x:Key="Employees">
   <local:Employee Name="Elizabeth" EmpId="1" ParentId="" Designation="CEO"/>
   <local:Employee Name="Christina" EmpId="2" ParentId="1" Designation="Manager"/>
   <local:Employee Name="Yang" EmpId="3" ParentId="1" Designation="Manager"/>
   <local:Employee Name="Yoshi" EmpId="4" ParentId="2" Designation="TeamLead"/>
   <local:Employee Name="Philip" EmpId="5" ParentId="2" Designation="TeamLead"/>
   <local:Employee Name="Roland" EmpId="6" ParentId="3" Designation="TeamLead"/>
   <local:Employee Name="Yuonne" EmpId="7" ParentId="3" Designation="TeamLead"/>
</local:Employees>

{% endhighlight %}

###Map data source

You can configure this “Employee Information” with Diagram, so that the node and connector are automatically generated using mapping properties. 
The following code examples show how DataSourceSetting is used to map id and parent with property name identifiers for employee information.

{% highlight xaml %}

<!--Initializes the DataSourceSettings-->
<syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"							    
                               Id="EmpId">
</syncfusion:DataSourceSettings>

{% endhighlight %}

###Visualize Employees

The following code examples indicate how to define the default appearance of NodeViewModel and ConnectorViewModel using default BindingStyle. The ContentTemplate of the Node is used to update each node based on employee data.

{% highlight xaml %}

<Window.Resources>
<ResourceDictionary>
<!--Style for the Node>-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
<Setter Property="UnitWidth" Value="80" />
<Setter Property="UnitHeight" Value="40" />
<Setter Property="FontSize" Value="15"></Setter>
<Setter Property="Foreground" Value="Black"></Setter>
<Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter>
<Setter Property="VerticalContentAlignment" Value="Stretch"></Setter>
<Setter Property="ContentTemplate">
<Setter.Value>
<DataTemplate>
<Border Background="#008b8b" CornerRadius="5">
<TextBlock Text="{Binding Name}" Foreground="White" HorizontalAlignment="Center" VerticalAlignment="Center"/>
</Border>
</DataTemplate>
</Setter.Value>
</Setter>
</Style>
<!--Style for the Connector>-->
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle }">
<Setter Property="ConnectorGeometryStyle">
<Setter.Value>
<Style TargetType="Path">
<Setter Property="Stroke" Value="Black" />
<Setter Property="StrokeThickness" Value="1" />
</Style>
</Setter.Value>
</Setter>
</Style>
</ResourceDictionary>
</<Window.Resources>

{% endhighlight %}

###Apply org chart layout

Next you need to arrange Nodes in an organizational chart structure, and to do this you can apply layout as shown in following code example. You can see that spacing and orientation are defined, that can also be customized based on the needs.

{% highlight xaml %}

<!--Initializes the Layout-->
<syncfusion:DirectedTreeLayout x:Key="TreeLayout" Orientation="TopToBottom"
    HorizontalSpacing="80" VerticalSpacing="50" SpaceBetweenSubTrees="20"/>
    
<syncfusion:LayoutManager x:Key="LayoutManager"  
                          Layout="{StaticResource TreeLayout}"/>

<Grid Background="White">
    <!--Initialize the SfDiagram-->
	<syncfusion:SfDiagram x:Name="diagram" LayoutManager="{StaticResource LayoutManager}">
    </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}

The final MainPage.Xaml looks like this.

{% highlight xaml %}

<Window
x:Class="EmployeeDetails.MainWindow"
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
xmlns:local="clr-namespace:EmployeeDetails">

<Window.Resources>
<ResourceDictionary>
<ResourceDictionary.MergedDictionaries>
<ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BindingStyle.xaml" />
</ResourceDictionary.MergedDictionaries>

<!-- Initializes the employee colletion-->
<local:Employees x:Key="Employees">
<local:Employee Name="Elizabeth" EmpId="1" ParentId="" Designation="CEO"/>
<local:Employee Name="Christina" EmpId="2" ParentId="1" Designation="Manager"/>
<local:Employee Name="Yang" EmpId="3" ParentId="1" Designation="Manager"/>
<local:Employee Name="Yoshi" EmpId="4" ParentId="2" Designation="TeamLead"/>
<local:Employee Name="Philip" EmpId="5" ParentId="2" Designation="TeamLead"/>
<local:Employee Name="Roland" EmpId="6" ParentId="3" Designation="TeamLead"/>
<local:Employee Name="Yuonne" EmpId="7" ParentId="3" Designation="TeamLead"/>
</local:Employees>

<!--Initializes the DataSourceSettings -->

<syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"
Id="EmpId" DataSource="{StaticResource Employees}">
</syncfusion:DataSourceSettings>

<!--Style for the Node>-->

<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
<Setter Property="UnitWidth" Value="80" />
<Setter Property="UnitHeight" Value="40" />
<Setter Property="FontSize" Value="15"></Setter>
<Setter Property="Foreground" Value="Black"></Setter>
<Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter>
<Setter Property="VerticalContentAlignment" Value="Stretch"></Setter>
<Setter Property="ContentTemplate">
<Setter.Value>
<DataTemplate>
<Border Background="#008b8b"
CornerRadius="5">
<TextBlock Text="{Binding Name}" Foreground="White" HorizontalAlignment="Center"  VerticalAlignment="Center"/>
</Border>
</DataTemplate>
</Setter.Value>
</Setter>

</Style>
<!--Style for the Connector>-->

<Style TargetType="syncfusion:Connector">
<Setter Property="ConnectorGeometryStyle">
<Setter.Value>
<Style TargetType="Path">
<Setter Property="Stroke" Value="Black" />
<Setter Property="StrokeThickness" Value="1" />
</Style>
</Setter.Value>
</Setter>
</Style>

<!--Initializes the Layout-->
<syncfusion:DirectedTreeLayout x:Key="TreeLayout"
HorizontalSpacing="80"
VerticalSpacing="50"
SpaceBetweenSubTrees="20"
Orientation="TopToBottom"/>

<syncfusion:LayoutManager x:Key="LayoutManager" Layout="{StaticResource TreeLayout}"/>
</ResourceDictionary>
</Window.Resources>

<Grid Background="White">
<!--Initializes the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram"
DataSourceSettings="{StaticResource DataSourceSettings}"
LayoutManager="{StaticResource LayoutManager}">
<!--Initializes the NodeCollection-->
<syncfusion:SfDiagram.Nodes>
<syncfusion:NodeCollection/>
</syncfusion:SfDiagram.Nodes>
<!--Initializes the ConnectorCollection-->
<syncfusion:SfDiagram.Connectors>
<syncfusion:ConnectorCollection/>
</syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>
</Grid>

</Window>
{% endhighlight %}

The Employee data is displayed in the SfDiagram as follows

![](Getting-Started_images\Getting_Started_img3.jpeg)