---
layout: post
title: Getting started with Syncfusion Essential Diagram for WPF.
description: Getting started walk through to create your first Flow Diagram and Organizational Chart Diagram
platform: wpf
control: SfDiagram
documentation: ug
---

#Getting Started

##About Diagram

Let us create flow diagram and automatic layout with SfDiagram.
 
* Flow Diagram Example

![](Getting-Started_images\ug_Getting_Started_flowDiagram.PNG)

* Automatic Layout Example

![](Getting-Started_images\Getting_Started_img3.PNG)

###WPF Application

* Create new WPF project using Visual Studio. For more [details](https://msdn.microsoft.com/en-IN/library/bb546958(v=vs.90).

###Assembly Reference

1. Open the Add reference window from your project.
2. Choose Windows > Extensions > Syncfusion.SfDiagram.WPF.

![](Getting-Started_images\Getting_Started_img.png)

####Add SfDiagram from Toolbox

Drag and drop the SfDiagram control from the Toolbox to the XAML window.

![](Getting-Started_images\Getting_Started_img1.png)

The xmlns name space is added to the MainWindow.xaml

![](Getting-Started_images\Getting_Started_img2.png)

###Initialize the Diagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram in XAML as shown in the following code example.

{% tabs %}
{% highlight xaml %}
   <!--Initializes the SfDiagram in XMAL window-->  
   <syncfusion:SfDiagram x:Name="diagram"/>
{% endhighlight %}
{% highlight c# %}
   /// Initialize SfDiagram
   SfDiagram diagram = new SfDiagram();
{% endhighlight %} 
{% endtabs %}

####Initialize Nodes and Connectors

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connectors property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% tabs %}
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
{% highlight c# %}
//Initialize with Collection of NodeViewModel
diagram.Nodes = new NodeCollection();
//Initialize with Collection of ConnectorViewModel
diagram.Connectors = new ConnectorCollection();  
{% endhighlight %}       
{% endtabs %}

####DataBinding

We have provided the default binding style support, in order to bind the properties of ViewModel to View.
For more information, refer to  [Data-Binding](/wpf/sfdiagram/Data-Binding).

##Simple Application

Let us create simple flow diagram in ViewModel, By applying binding style as mentioned in DataBinding.For more details about DataBinding, refer to  [Data-Binding](/wpf/sfdiagram/Data-Binding).

###Basic Shapes

* We have provided set of basic shapes for Diagram as ResourceDictionary. For more information, refer to  [Shapes](/wpf/sfdiagram/Shapes). 

###Add Nodes

* Let us create and add a NodeViewModel with height, width, shape, shape style,specific position, size and Annotation.

####Creating a Node

Creating NodeViewModel with Specified Height and Width.

{% tabs %}
{% highlight xaml %}
<syncfusion:NodeViewModel ID="Begin"  UnitHeight="40" UnitWidth="120"/> 
{% endhighlight %}
{% highlight c# %}
NodeViewModel Begin = new NodeViewModel()
            {
                ID="Begin"
                //Sets the size
                UnitWidth = 120,UnitHeight = 40,            
            };
{% endhighlight %}
{% endtabs %}

####Adding specific position to Node

{% tabs %}
{% highlight xaml %}
 <syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60"/>  
{% endhighlight %}
{% highlight c# %}
NodeViewModel Begin = new NodeViewModel()
            {
                ID="Begin",
                //Sets the size
                UnitWidth = 120,UnitHeight = 40,
                //Sets the position
                OffsetX = 300,OffsetY = 60,
            };
{% endhighlight %}
{% endtabs %}

####Adding Shape to Node

{% tabs %}
{% highlight xaml %}  
 <syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}"/>
{% endhighlight %}
{% highlight c# %}
 NodeViewModel Begin = new NodeViewModel()
            {
                ID="Begin"            
                //Sets the size
                UnitWidth = 120,UnitHeight = 40,
                //Sets the position
                OffsetX = 300,OffsetY = 60,
                //Add the Node shape
                Shape=App.Current.Resources[Ellipse];
            };
{% endhighlight %}
{% endtabs %}

####Adding Shape Style to the Node

{% tabs %}
{% highlight xaml %} 
            <Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
                <Setter Property="ShapeStyle">
                    <Setter.Value>
                        <Style TargetType="Path">
                            <Setter Property="Fill" Value="CornflowerBlue"/>
                            <Setter Property="Stretch" Value="Fill"/>
                            <Setter Property="Stroke" Value="Black"/>
                        </Style>
                    </Setter.Value>
                </Setter>
            </Style>        
{% endhighlight %}
{% highlight c# %} 
NodeViewModel Begin = new NodeViewModel()
            {
                 ID="Begin" 
                //Sets the size
                UnitWidth = 120,UnitHeight = 40,
                //Sets the position
                OffsetX = 300,OffsetY = 60,
                //Add the Node shape
                Shape=App.Current.Resources[Ellipse];
                //Add node shape style
                ShapeStyle=App.Current.Resources["shapestyle"] as Style,
            };
{% endhighlight %}
{% endtabs %}

* Now Node will be looks like,
   
![](Getting-Started_images\node.PNG)
   
N> ID sets for each node to identify nodes easily while setting connectors.
   
####Adding Annotation to node
   
* To initialize the Annotation property of the Node and Connector, it is assigned with the annotation collection, that is, ObservableCollection of the IAnnotation.

{% highlight C# %}
   /// <summary>
   /// create custom class for Annotation Collection
   /// </summary>
   public class AnnotationCollection : ObservableCollection<IAnnotation>
   {

   }   
{% endhighlight %} 
    
N> Annotation property is a collection, which indicates that more than one Annotation can be added to a Node and Connector.

* Now add the Annotation content to Node.

{% tabs %}
{% highlight xaml %}
    <syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" >
        <syncfusion:NodeViewModel.Annotations>
            <local:AnnotationCollection>
                <syncfusion:AnnotationEditorViewModel Content="Begin"/>
            </local:AnnotationCollection>
        </syncfusion:NodeViewModel.Annotations>
    </syncfusion:NodeViewModel>             
{% endhighlight %}
{% highlight c# %}
NodeViewModel node = new NodeViewModel()
            {
                ID="Begin",
                //Sets the size
                UnitWidth = 120,UnitHeight = 40,
                //Sets the position
                OffsetX = 300,OffsetY = 60,
                //Add the Node shape
                Shape=new EllipseGeometry() { RadiusX=10,RadiusY=10},
                //Add node shape style
                ShapeStyle=App.Current.Resources["shapestyle"] as Style,
                Annotations=new ObservableCollection<AnnotationEditorViewModel>()
                {
                    new AnnotationEditorViewModel()
                    {
                        Content="Begin",
                    }
                }
            };
{% endhighlight %}
{% endtabs %}

* For Annotation binding style,refer to [Data-Binding](/wpf/sfdiagram/Data-Binding).
 
Now Node will be looks like,
 
![](Getting-Started_images\Getting_Started_flowDiagram_img1.PNG)
 
###Nodes for Flow Diagram

* We can add multiple Nodes with different shapes into diagram as NodeViewModel.

{% tabs %}
{% highlight xaml %}
<!--Begin-->
<syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" >
   <syncfusion:NodeViewModel.Annotations>
      <local:AnnotationCollection>
         <syncfusion:AnnotationEditorViewModel Content="Begin"/>
      </local:AnnotationCollection>
   </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
<!--Process-->
<syncfusion:NodeViewModel ID="Process" UnitHeight="60" UnitWidth="120" OffsetX="300" OffsetY="140"  Shape="{StaticResource PredefinedProcess}">
   <syncfusion:NodeViewModel.Annotations>
      <local:AnnotationCollection>
          <syncfusion:AnnotationEditorViewModel Content="Process"/>
      </local:AnnotationCollection>
    </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>       
<!--End-->           
<syncfusion:NodeViewModel ID="End" UnitHeight="40" UnitWidth="40" OffsetX="300" OffsetY="225" Shape="{StaticResource Ellipse}">
   <syncfusion:NodeViewModel.Annotations>
      <local:AnnotationCollection>
          <syncfusion:AnnotationEditorViewModel Content="End"/>
      </local:AnnotationCollection>
  </syncfusion:NodeViewModel.Annotations>
</syncfusion:NodeViewModel>
{% endhighlight %}
{% highlight c# %}
public MainWindow()
        {
            InitializeComponent();
            ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
            //Begin Node
            NodeViewModel Begin = Addnode(300, 60, 120, 40, "Begin", "Ellipse");
            //Process Node
            NodeViewModel Process = Addnode(300, 140, 120, 60, "Process", "Process");
            //End Node
            NodeViewModel End = Addnode(300, 225, 40, 40, "End", "Ellipse");
            //Adding Nodes to diagram
            nodes.Add(Begin);
            nodes.Add(Process);
            nodes.Add(End);
            diagram.Nodes = nodes;
        }
        //Method for creating Node
        public NodeViewModel Addnode(string id, double offsetX, double offsetY, double width, double height, string text, string shape)
        {

            NodeViewModel node = new NodeViewModel();
            node.ID = id;
            node.OffsetX = offsetX;
            node.OffsetY = offsetY;
            node.UnitHeight = height;
            node.UnitWidth = width;
            node.Shape = App.Current.Resources[shape];
            node.ShapeStyle = App.Current.Resources["nodeshapestyle"] as Style;
            node.Annotations = new ObservableCollection<AnnotationEditorViewModel>()
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

* Finally all Nodes added to diagram and it will be looks like

![](Getting-Started_images\nodes.PNG)

###Add Connectors

* Connector is to make connection or link between two Nodes, Ports and Points.

####Create Connector With Source Node and Target Node 

* Here, we have used `SourceNodeID` and `TargetNodeID` property of the Connector.These properties wil be assigned with `ID` property of the Node.

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

####Adding Connector geometry style

{% highlight xaml %}
<!--Customized connector style--> 
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

Now output will be,

 ![](Getting-Started_images\Getting_Started_flowDiagram_img2.PNG)
 
####Connectors for Flow diagram

Now we can connect all nodes using ConnectorViewModel.

{% tabs %}
{% highlight xaml %}
<syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process"/>
<syncfusion:ConnectorViewModel SourceNodeID="Process" TargetNodeID="End"/> 
{% endhighlight %} 
{% highlight c# %}
ConnectorViewModel connector1 = new ConnectorViewModel()
            {
               SourceNodeID = "Begin",
               TargetNodeID = "Process"
            };
            ConnectorViewModel connector2 = new ConnectorViewModel()
            {
                SourceNodeID = "Process",
                TargetNodeID = "End",
            };
{% endhighlight %} 
{% endtabs %}

Now output will be looks like,

![](Getting-Started_images\ug_Getting_Started_flowDiagram.PNG)
    
###Complete Diagram

Now we can integrate all NodeViewModel and corresponding ConnectorViewModel to Diagram. Final XMAL code will be,

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDiagram x:Name="diagram" DefaultConnectorType="Line" >
  <!--Initializes the Nodes-->
  <syncfusion:SfDiagram.Nodes>
    <!--Initializes the NodeCollection-->
    <syncfusion:NodeCollection>
      <!--Begin-->
        <syncfusion:NodeViewModel ID="Begin" UnitHeight="40" UnitWidth="120" OffsetX="300" OffsetY="60" Shape="{StaticResource Ellipse}" >
           <syncfusion:NodeViewModel.Annotations>
              <!--Initialize Annotation Collection-->
              <local:AnnotationCollection>
                 <syncfusion:AnnotationEditorViewModel Content="Begin"/>
              </local:AnnotationCollection>
          </syncfusion:NodeViewModel.Annotations>
        </syncfusion:NodeViewModel>
      <!--Begin-->
      <syncfusion:NodeViewModel ID="Process" UnitHeight="60" UnitWidth="120" OffsetX="300" OffsetY="140"  Shape="{StaticResource PredefinedProcess}">
         <syncfusion:NodeViewModel.Annotations>
           <!--Initialize Annotation Collection-->
           <local:AnnotationCollection>
              <syncfusion:AnnotationEditorViewModel Content="Process"/>
           </local:AnnotationCollection>
         </syncfusion:NodeViewModel.Annotations>
     </syncfusion:NodeViewModel>
     <!--End-->
     <syncfusion:NodeViewModel ID="End" UnitHeight="40" UnitWidth="40" OffsetX="300" OffsetY="225" Shape="{StaticResource Ellipse}">
        <!--Initialize Annotation Collection-->
        <local:AnnotationCollection>
           <syncfusion:AnnotationEditorViewModel Content="End"/>
        </local:AnnotationCollection>
     </syncfusion:NodeViewModel.Annotations>
  </syncfusion:NodeViewModel>
 </syncfusion:NodeCollection>
</syncfusion:SfDiagram.Nodes>
<!--Initialize Connectors-->
<syncfusion:SfDiagram.Connectors>
    <!--Initialize Connector Collection-->
     <syncfusion:ConnectorCollection>
        <!--create a connection from begin to Process-->
        <syncfusion:ConnectorViewModel SourceNodeID="Begin" TargetNodeID="Process"/>
        <!--create a connection from Process to End-->
        <syncfusion:ConnectorViewModel SourceNodeID="Process" TargetNodeID="End"/>
    </syncfusion:ConnectorCollection>
  </syncfusion:SfDiagram.Connectors>
  </syncfusion:SfDiagram>
{% endhighlight %} 
{% highlight c# %}
public MainWindow()
        {
            InitializeComponent();
            ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();
            NodeViewModel Begin = Addnode("Begin", 300, 60, 120, 40, "Begin", "Ellipse") ;
            NodeViewModel Process = Addnode("Process", 300, 140, 120, 60, "Process", "Process");
            NodeViewModel End = Addnode("End", 300, 225, 40, 40, "End", "Ellipse");
            nodes.Add(Begin);
            nodes.Add(Process);
            nodes.Add(End);
            diagram.Nodes = nodes;
            ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();
           ConnectorViewModel connector1 = new ConnectorViewModel()
            {
                SourceNodeID = "Begin",
                TargetNodeID = "Process",
            };
            ConnectorViewModel connector2 = new ConnectorViewModel()
            {
                SourceNodeID = "Process",
                TargetNodeID = "End",
            };
            lines.Add(connector1);
            lines.Add(connector2);
            diagram.Connectors = lines;
        }
        public NodeViewModel Addnode(string id, double offsetX, double offsetY, double width, double height, string text, string shape)
        {
            NodeViewModel node = new NodeViewModel();
            node.ID = id;
            node.OffsetX = offsetX;
            node.OffsetY = offsetY;
            node.UnitHeight = height;
            node.UnitWidth = width;
            node.Shape = App.Current.Resources[shape];
            node.ShapeStyle = App.Current.Resources["nodeshapestyle"] as Style;
            node.Annotations = new ObservableCollection<AnnotationEditorViewModel>()
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

Final output diagram will be,

![](Getting-Started_images\ug_Getting_Started_flowDiagram.PNG)

##Automatic Layout

Now let us see how to create and position to diagram automatically.

###Initialize diagram

Initializing diagram is already discussed above > [Initialize the diagram](/wpf/sfdiagram/Getting-Started#Initialize the diagram) section.

###Business object (Employee information)

* Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

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

You can configure this “Employee Information” with Diagram, so that the Node and Connector are automatically generated using mapping properties. 
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
<syncfusion:DirectedTreeLayout Type="Organization" x:Key="TreeLayout" Orientation="TopToBottom"
    HorizontalSpacing="80" VerticalSpacing="50" SpaceBetweenSubTrees="20"/>
    
<syncfusion:LayoutManager x:Key="LayoutManager"  
                          Layout="{StaticResource TreeLayout}"/>
<Grid Background="White">
    <!--Initialize the SfDiagram-->
	<syncfusion:SfDiagram x:Name="diagram" LayoutManager="{StaticResource LayoutManager}">
    </syncfusion:SfDiagram>
</Grid>
{% endhighlight %}

The final MainWindow.Xaml looks like this.

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
    <Setter Property="FontSize" Value="15"></Setter>
    <Setter Property="Foreground" Value="Black"></Setter>
    <Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter>
    <Setter Property="VerticalContentAlignment" Value="Stretch"></Setter>
    <Setter Property="ContentTemplate">
        <Setter.Value>
            <DataTemplate>
                <Border Background="#008b8b" CornerRadius="5" Width="80" Height="40">
                    <TextBlock Text="{Binding Name}" Foreground="White" HorizontalAlignment="Center"  VerticalAlignment="Center"/>
                </Border>
            </DataTemplate>
        </Setter.Value>
     </Setter>
</Style>
<!--Style for the Connector>-->
<Style TargetType="syncfusion:Connector"  BasedOn="{StaticResource ConnectorBindingStyle}">
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

![](Getting-Started_images\Getting_Started_img3.PNG)









                    


 
 








 

