---
layout: post
title: Getting started with Syncfusion Essential Diagram for WPF.
description: Getting started walk through to create your Organizational Chart Diagram.
platform: wpf
control: SfDiagram
documentation: ug
---

#Getting Started

**Creating Simple Diagram**

This section demonstrates how to visualize the Employee details in the Organizational Chart arrangement by using the SfDiagram.

##Add the SfDigram from the Toolbox

Drag and drop the SfDiagram control from the Toolbox to the XAML Page.

![](Getting-Started_images\Getting_Started_img1.png)

The xmlns name space is added to the MainPage.xaml

![](Getting-Started_images\Getting-Started_img2.png)

###Initialize the SfDiagram

The SfDiagram exists in the Syncfusion.UI.Xaml.Diagram namespace. Initialize SfDiagram to the XAML Page as shown in the following code sample.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

    <Grid Background="White">

          <syncfusion:SfDiagram x:Name="diagram">
         
          </syncfusion:SfDiagram>

    </Grid>
</Window>

{% endhighlight %}

###Initialize Nodes and Connectors

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connector’s property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

    <Grid Background="White">
	<syncfusion:SfDiagram x:Name="diagram">
             <syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
             </syncfusion:SfDiagram.Nodes>       
              <syncfusion:SfDiagram.Connectors>
                	<syncfusion:ConnectorCollection/>
              </syncfusion:SfDiagram.Connectors>
       </syncfusion:SfDiagram>

   </Grid>
   </Window>

{% endhighlight %}

{% highlight C# %}

namespace EmployeeDetails
{ 
    public partial class MainPage : Page
    {
        public MainWindow()
        {
            this.InitializeComponent();
        }
    }
    
    // Employee Collection.

    public class Employees : ObservableCollection<Employee>
    {

    }
}

{% endhighlight %}

###Create class to store employee information

Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

{% highlight C# %}

namespace EmployeeDetails
{
	public partial class MainPage : Page
	{
		public MainWindow()
		{
			InitializeComponent();
		}
	}

    	//Employee Business Object
	public class Employee
	{
		public string ParentId { get; set; }
		public string Name { get; set; }
		public string Designation { get; set; }
		public int EmpID { get; set; }
	}

    	//Employee Collection
	public class Employees : ObservableCollection<Employee>
	{

	}
}

{% endhighlight %}

###Initialize Data

Create a collection of employees with each employee having an ID in the Empid and the reporting person’s ID in the Parent ID. This collection is placed in the Window resource and later incorporated in the Diagram. This is explained in the next point.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

    
<Window.Resources>

        <!-- Initializes the employee colletion-->

        <local:Employees x:Key="Employees">

            <local:Employee Name="Elizabeth" Empid="1" ParentId=""Designation="CEO"/>
            <local:Employee Name="Christina" Empid="2" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yang" Empid="3" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yoshi" Empid="4" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Philip" Empid="5" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Roland" Empid="6" ParentId="3" Designation="TeamLead"/>
            <local:Employee Name="Yuonne" Empid="7" ParentId="3" Designation="TeamLead"/>

        </local:Employees>

</Window.Resources>

     <Grid Background="White">
	<syncfusion:SfDiagram x:Name="diagram">
             <syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
             </syncfusion:SfDiagram.Nodes>       
              <syncfusion:SfDiagram.Connectors>
                	<syncfusion:ConnectorCollection/>
              </syncfusion:SfDiagram.Connectors>
       </syncfusion:SfDiagram>
    </Grid>

</Window> 

{% endhighlight %}

###Initialize DataSourceSettings

To populate employee information as Nodes and connectors, configure the DataSourceSettings with the DataSource, ID, and ParentId. The ID property is used as a unique identifier for each Node, and the parent ID represents the parent Node where a Node has to be connected. The following code example illustrates how to define the DataSourceSetting and set it to the Diagram.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

<Window.Resources>
         ……….

        <!--Initializes the DataSourceSettings -->

        <syncfusion:DataSourceSettings x:Key="DataSourceSettings" 
		  ParentId="ParentId"    Id="Empid"
                DataSource="{StaticResource Employees}">
        </syncfusion:DataSourceSettings>

</Window.Resources>

    <Grid Background="White">
	<syncfusion:SfDiagram x:Name="diagram"
	DataSourceSettings="{StaticResource DataSourceSettings}">
		<syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
		</syncfusion:SfDiagram.Nodes>
		<syncfusion:SfDiagram.Connectors>
			<syncfusion:ConnectorCollection/>
		</syncfusion:SfDiagram.Connectors>
	</syncfusion:SfDiagram>
   </Grid>

</Window>

{% endhighlight %}

###Visualize Employees

Now, Diagram is configured to load the employees’ information as a tree of organization chart. Next, give visual appearance for the Node. To visualize the employees’ details in the Node, a Node has to be created for each employee, and then the employee’s details are stored in the Node’s content property. To visualize the employee information, define the appearance as a data template and apply it to the Node’s content template as shown in the following code example.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

<Window.Resources>
         ……….

        <!--Style for the Node>-->

        <Style TargetType="syncfusion:Node">

            <Setter Property="UnitWidth" Value="180" />
            <Setter Property="UnitHeight" Value="70" />
            <Setter Property="FontSize" Value="15"> </Setter>
            <Setter Property="Foreground" Value="Black"> </Setter>
            <Setter Property="HorizontalContentAlignment" Value="Stretch"> </Setter>
            <Setter Property="VerticalContentAlignment" Value="Stretch"> </Setter>

            <Setter Property="ContentTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Border Width="100" Height="40" Background="#008b8b" 
                                CornerRadius="5">
                            <TextBlock Text="{Binding Name}"  
                                       HorizontalAlignment="Center" 
                                       VerticalAlignment="Center"/>
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

</Window.Resources>

    <Grid Background="White">

        <syncfusion:SfDiagram x:Name="diagram"
	DataSourceSettings="{StaticResource DataSourceSettings}">
		<syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
		</syncfusion:SfDiagram.Nodes>
		<syncfusion:SfDiagram.Connectors>
			<syncfusion:ConnectorCollection/>
		</syncfusion:SfDiagram.Connectors>
	</syncfusion:SfDiagram>

    </Grid>

</Window>

{% endhighlight %}

###Initialize Layout

Employees are initialized, populated in the Diagram, and appearance for employees are defined. Now, place the Nodes and Connector by using the layout manager. The following code example shows how to initialize the LayoutManager, specify the layout as the DirectedTreeLayout and set it to the Diagram.

{% highlight xaml %}

<Window
        x:Class="EmployeeDetails.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:local="clr-namespace:EmployeeDetails">

<Window.Resources>
         ……….
        <!--Initializes the Layout-->

        <layout:DirectedTreeLayout x:Key="TreeLayout" 
		                     HorizontalSpacing="80" 
		                     VerticalSpacing="50" 
		                     SpaceBetweenSubTrees="20" 
		                     Orientation="TopToBottom"/>

              <layout:LayoutManager x:Key="LayoutManager"  
		                      Layout="{StaticResource TreeLayout}"/>

</Window.Resources>

    <Grid Background="White">
	<syncfusion:SfDiagram x:Name="diagram"
	DataSourceSettings="{StaticResource DataSourceSettings}"
	LayoutManager="{StaticResource LayoutManager}">
		<syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
		</syncfusion:SfDiagram.Nodes>
		<syncfusion:SfDiagram.Connectors>
			<syncfusion:ConnectorCollection/>
		</syncfusion:SfDiagram.Connectors>
	</syncfusion:SfDiagram>
    </Grid>

</Window>

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

<!-- Initializes the employee colletion-->

        <local:Employees x:Key="Employees">

            <local:Employee Name="Elizabeth" Empid="1" ParentId=""Designation="CEO"/>
            <local:Employee Name="Christina" Empid="2" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yang" Empid="3" ParentId="1" Designation="Manager"/>
            <local:Employee Name="Yoshi" Empid="4" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Philip" Empid="5" ParentId="2" Designation="TeamLead"/>
            <local:Employee Name="Roland" Empid="6" ParentId="3" Designation="TeamLead"/>
            <local:Employee Name="Yuonne" Empid="7" ParentId="3" Designation="TeamLead"/>

        </local:Employees>


        <!--Initializes the DataSourceSettings -->

        <syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"							    
         Id="Empid" DataSource="{StaticResource Employees}">
        </syncfusion:DataSourceSettings>

        <!--Style for the Node>-->

        <Style TargetType="syncfusion:Node">

            <Setter Property="UnitWidth" Value="80" />
            <Setter Property="UnitHeight" Value="40" />
            <Setter Property="FontSize" Value="15"> </Setter>
            <Setter Property="Foreground" Value="Black"> </Setter>
            <Setter Property="HorizontalContentAlignment" Value="Stretch"> </Setter>
            <Setter Property="VerticalContentAlignment" Value="Stretch"> </Setter>
            <Setter Property="ContentTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <Border Background="#008b8b" 
                                CornerRadius="5">
                            <TextBlock Text="{Binding Name}" Foreground="White"
                            HorizontalAlignment="Center"  VerticalAlignment="Center"/>                                
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

        <layout:DirectedTreeLayout x:Key="TreeLayout" 
		                     HorizontalSpacing="80" 
		                     VerticalSpacing="50" 
		                     SpaceBetweenSubTrees="20" 
		                     Orientation="TopToBottom"/>

        <layout:LayoutManager x:Key="LayoutManager"  
		                Layout="{StaticResource TreeLayout}"/>

        <Style TargetType="Path" x:Key="Deco1">
            <Setter Property="Stroke" Value="Black" />
            <Setter Property="StrokeThickness" Value="3" />
        </Style>
  
    </Window.Resources>

    <Grid Background="White">        
	<syncfusion:SfDiagram x:Name="diagram"
	DataSourceSettings="{StaticResource DataSourceSettings}"
	LayoutManager="{StaticResource LayoutManager}">
		<syncfusion:SfDiagram.Nodes>
			<syncfusion:NodeCollection />
		</syncfusion:SfDiagram.Nodes>
		<syncfusion:SfDiagram.Connectors>
			<syncfusion:ConnectorCollection/>
		</syncfusion:SfDiagram.Connectors>
	</syncfusion:SfDiagram>
    </Grid>

</Window> 

{% endhighlight %}

The Employee data is displayed in the SfDiagram as follows

![](Getting-Started_images\Getting_Started_img3.jpeg)