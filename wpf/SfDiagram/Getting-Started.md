---
layout: post
title: Getting started with Syncfusion Essential Diagram for WPF.
description: Getting started walk through to create your first Flow Diagram and Organizational Chart Diagram
platform: wpf
control: SfDiagram
documentation: ug
---

#Getting Started

Getting started with your Essential WPF Diagram is easy. You can start by creating a simple Flow Diagram.

## Creating Simple Diagram

   * Create new WPF project using Visual Studio. For more [details](https://msdn.microsoft.com/en-IN/library/bb546958(v=vs.90)).
   * Add SfDiagram assembly to your application. 
   * Initialize the diagram.

###Adding assembly reference   
 
1. Open the Add reference window from your project.
2. Choose Windows > Extensions > Syncfusion.SfDiagram.WPF.

![](Getting-Started_images\Getting_Started_img.png)

###Add SfDiagram from Toolbox

Drag and drop the SfDiagram control from the Toolbox to the XAML Page.

![](Getting-Started_images\Getting_Started_img1.png)

The xmlns name space is added to the MainPage.xaml

![](Getting-Started_images\Getting_Started_img2.png)

###Initialize the diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram to the XAML Page as shown in the following code example.

{% highlight xaml %}

<Grid>
    <!--Initializes the SfDiagram-->  
    <syncfusion:SfDiagram x:Name="diagram">
    </syncfusion:SfDiagram>
</Grid>

{% endhighlight %}


###Initialize PageSettings

Page settings enable to customize the appearance of the Diagram page.

{% highlight xaml %}
<Grid>
    <!--Initializes the SfDiagram-->  
    <syncfusion:SfDiagram x:Name="diagram">
        <!--customize default page settings-->
        <syncfusion:SfDiagram.PageSettings>
            <syncfusion:PageSettings PageBorderBrush="Transparent" PageBackground="White"></syncfusion:PageSettings>
        </syncfusion:SfDiagram.PageSettings>
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

We have provided the Default Binding Style support, in order to Bind the properties of ViewModel to View.
For more information, refer to [Data Binding](/wpf/sfdiagram/Data-Binding).

##Flow Diagram

###BasicShapes
We have provided support for the BasicShapes for Diagram as ResourceDictionary. So, Merge the BasicShapes ResourceDictionary to the Application.
{% highlight xaml %}
<ResourceDictionary.MergedDictionaries>               
   <!--Shapes as StaticResource-->
   <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
</ResourceDictionary.MergedDictionaries>
{% endhighlight %}

###Create Custom Annotation Collection

To create annotation collection of the node and connector. Annotation properties assigned with the annotation collection, that is, ObservableCollection of the IAnnotation.

{% highlight xaml %}

//create Annotation Collection
public class AnnotationCollection : ObservableCollection<IAnnotation>
{

}
{% endhighlight %}

###Create and add Node
Let us create and add a NodeViewModel with specific position, Size, Annotation and Shape.
{% highlight xaml %}

<!--Create a NodeViewModel with Specific customization option-->
<syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}">
    <syncfusion:NodeViewModel.Annotations>
        <!--Initialize Annotation Collection-->
        <local:AnnotationCollection>
            <syncfusion:AnnotationEditorViewModel Content="Begin"/>
        </local:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>

{% endhighlight %}
           
N> Annotations property is an Collection, which indicates that more than one Annotation can be added to a Node.

Added node will be displayed in diagram as shown below.
                           
![](Getting-Started_images\Getting_Started_Image2.jpg)

###Connect nodes
    * Create another NodeViewModel with another set of data.
    {% highlight xaml %}
<!--Begin-->
<syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}">
    <syncfusion:NodeViewModel.Annotations>
        <!--Initialize Annotation Collection-->
        <local:AnnotationCollection>
            <syncfusion:AnnotationEditorViewModel Content="Begin"/>
        </local:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
<!--Input the number-->
<syncfusion:NodeViewModel ID="Input" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="140" Shape="{StaticResource Data}">
    <syncfusion:NodeViewModel.Annotations>
        <!--Initialize Annotation Collection-->
        <local:AnnotationCollection>
            <syncfusion:AnnotationEditorViewModel Content="Input : n"/>
        </local:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
   {% endhighlight %}
    * Connect these two nodes by adding a ConnectorViewModel into Connectors collection with reference to SourceNodeID and TargetNodeID.
   {% highlight xaml %}
   <!--Create a connection from Begin to Inputn-->
   <syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Input"/>
   {% endhighlight %}
    * Connector connects the two nodes as shown below.

 ![](Getting-Started_images\Getting_Started_Image1.jpg)
 
###Common Style for nodes and Connectors
Default values for all Nodes and Connectors can be set using Common Style for Node and Connector. For example if all Nodes have same appearance, we can move such properties into Common Style.
 {% highlight xaml %}
<!--Binding Node Style-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
    <Setter Property="ShapeStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Fill" Value="White"/>
                <Setter Property="Stretch" Value="Fill"/>
                <Setter Property="Stroke" Value="Black"/>
            </Style>
        </Setter.Value>
    </Setter>
</Style>
            
<!--Binding connector style-->
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle}">
    <Setter Property="TargetDecoratorStyle" >
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="Black"/>
                <Setter Property="Stretch" Value="Fill"/>
                <Setter Property="Fill" Value="Black"/>
                <Setter Property="Height" Value="10"/>
                <Setter Property="Width" Value="10"/>
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="ConnectorGeometryStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Stroke" Value="Black" />
                <Setter Property="StrokeThickness" Value="1" />
            </Style>
        </Setter.Value>
    </Setter>
</Style>
 {% endhighlight %}
                    
###Complete flow diagram

Similarly we can add required Nodes and Connectors to form a complete flow diagram.          

{% highlight xaml %}  
<syncfusion:SfDiagram.Nodes>
    <!--Initializes the NodeCollection-->              
    <syncfusion:NodeCollection>
        <!--Begin-->
        <syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="Begin"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
        <!--Input the number-->
        <syncfusion:NodeViewModel ID="Input" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="140" Shape="{StaticResource Data}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="Input : n"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
        <!--check the condition-->
        <syncfusion:NodeViewModel ID="condition" UnitHeight="80" UnitWidth="120" OffsetX="300" OffsetY="230"
                                         Shape="{StaticResource Decision}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="if(n % 2 == 0)"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
        <!--dispaly odd-->
        <syncfusion:NodeViewModel ID="odd" UnitHeight="50" UnitWidth="120" OffsetX="190" OffsetY="350"
                                         Shape="{StaticResource PredefinedProcess}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="n is odd"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
        <!--display even-->
        <syncfusion:NodeViewModel ID="even" UnitHeight="50" UnitWidth="120" OffsetX="410" OffsetY="350"
                                         Shape="{StaticResource PredefinedProcess}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="n is even"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
        <!--End-->
        <syncfusion:NodeViewModel ID="end" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="450" Shape="{StaticResource Ellipse}">
            <syncfusion:NodeViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="End"/>
                </local:AnnotationCollection>
            </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
    </syncfusion:NodeCollection>
</syncfusion:SfDiagram.Nodes>

<syncfusion:SfDiagram.Connectors>
    <!--Initializes the ConnectorCollection-->
    <syncfusion:ConnectorCollection>
        <!--create a connection from begin to Inputn-->
        <syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Input"/>
        <!--create a connection from Inputn to condition-->
        <syncfusion:ConnectorViewModel SourceNodeID="Input" TargetNodeID="condition"/>
        <!--create a connection from condition to even-->
        <syncfusion:ConnectorViewModel SourceNodeID="condition" TargetNodeID="even">
            <syncfusion:ConnectorViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="Yes"/>
                </local:AnnotationCollection>
            </syncfusion:ConnectorViewModel.Annotations>
        </syncfusion:ConnectorViewModel>
        <!--create a connection from condition to odd-->
        <syncfusion:ConnectorViewModel SourceNodeID="condition" TargetNodeID="odd">
            <syncfusion:ConnectorViewModel.Annotations>
                <!--Initialize Annotation Collection-->
                <local:AnnotationCollection>
                    <syncfusion:AnnotationEditorViewModel Content="No"/>
                </local:AnnotationCollection>
            </syncfusion:ConnectorViewModel.Annotations>
        </syncfusion:ConnectorViewModel>
        <!--create a connection from odd to end-->
        <syncfusion:ConnectorViewModel SourceNodeID="odd" TargetNodeID="end"/>
        <!--create a connection from even to end-->
        <syncfusion:ConnectorViewModel SourceNodeID="even" TargetNodeID="end"/>
    </syncfusion:ConnectorCollection>
</syncfusion:SfDiagram.Connectors>
 {% endhighlight %}

Final flow chart will looks as shown below.
 ![](Getting-Started_images\Getting_Started.jpg)

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
                <Border Background="#008b8b" CornerRadius="5">
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
<syncfusion:DirectedTreeLayout x:Key="TreeLayout" HorizontalSpacing="80" VerticalSpacing="50"
                               SpaceBetweenSubTrees="20" Orientation="TopToBottom"/>

<syncfusion:LayoutManager x:Key="LayoutManager" Layout="{StaticResource TreeLayout}"/>
    </ResourceDictionary>
</Window.Resources>

<Grid Background="White">
<!--Initializes the SfDiagram-->
    <syncfusion:SfDiagram x:Name="diagram" DataSourceSettings="{StaticResource DataSourceSettings}"
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