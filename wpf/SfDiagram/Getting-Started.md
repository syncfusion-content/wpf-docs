---
layout: post
title: Getting Started | SfDiagram | wpf | Syncfusion
description: getting started  
platform: wpf
control: SfDiagram
documentation: ug
---

# Getting Started  

## Creating a simple Diagram:

This section demonstrates how to visualize the Employee details in the Organizational Chart arrangement by using the SfDiagram.

1. Add the SfDiagram from the Toolbox.

   Drag and drop the SfDiagram control from the Toolbox to the XAML Page.

   ![](Getting-Started_images/Getting-Started_img1.png)

   The xmlns namespace is added to the MainPage.xaml.

   ![](Getting-Started_images/Getting-Started_img2.png)

2. Initialize the SfDiagram

   The SfDiagram exists in the http://schemas.syncfusion.com/wpf namespace. Initialize the SfDiagram in the XAML page as shown in the following code example.

   ~~~ xaml

		<Window

			x:Class="EmployeeDetails.MainWindow"

			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

			xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

			xmlns:local="clr-namespace:EmployeeDetails" 

		xmlns:syncfusion="http://schemas.syncfusion.com/wpf">  

		<Grid>
				<syncfusion:SfDiagram>            

				</syncfusion:SfDiagram>  

			 </Grid>

		</Window>

   ~~~

3. Initialize Nodes and Connectors

   To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connectors property is assigned with the ConnectorCollection, that is, ObservableCollection of the Coneector.

   ~~~ xaml

		<Window

			x:Class="EmployeeDetails.MainWindow "

			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

			xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

			xmlns:local="clr-namespace:EmployeeDetails" >

			 <Grid>

			   <syncfusion:SfDiagram  x:Name="diagram>

				 <!-- Custom Collection for Node and Connector>-->

				   <syncfusion:SfDiagram.Nodes>

					  <local:NodeList></local:NodeList>

					</syncfusion:SfDiagram.Nodes>

					<syncfusion:SfDiagram.Connectors>

					  <local:ConnectorList></local:ConnectorList>

					</syncfusion:SfDiagram.Connectors>

			  </syncfusion:SfDiagram>

			</Grid>
		</Window>

   ~~~

   ~~~ csharp

		namespace EmployeeDetails

		{

		public sealed partial class MainWindow: Window

		{

				public MainWindow ()

				{

					this.InitializeComponent();
				}
		}

			//Custom collection for Node.

			public class NodeList : ObservableCollection<Node>

			{

			}

			//Custom collection for Connector.

			public class ConnectorList : ObservableCollection<Connector>

			{

			}
		}

   ~~~

4. Create a class to store employee information

   Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

   ~~~ csharp

		namespace EmployeeDetails

		{

		public sealed partial class MainWindow: Window

		{

				public MainWindow ()

				{

					this.InitializeComponent();
				}
		}

		//Employee -Business Object.

			public class Employee 
		{

		public string ParentId { get; set; }

		public int Empid { get; set; }

		public string Name { get; set; }

				public string Designation { get; set; }  

		}

		//Employee Collection.

		public class Employees : ObservableCollection<Employee>

		{



		}

		}

   ~~~
5. Initialize Data

   Create a collection of employees with each employee having an ID in the Epmid and the reporting person’s ID in the ParentId. This collection is placed in the Window resource and later incorporated in the Diagram. This is explained in the next point.

   ~~~ xaml

		<Window

			x:Class="EmployeeDetails.MainWindow "

			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

			xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

		xmlns:local="clr-namespace:EmployeeDetails">

		<Window.Resources>

			  <!--Initializes the employee collection-->

		<local:Employees x:Key="Employees">

		<local:Employee Name="Elizabeth" Empid="1" 	 					Designation="CEO"/>

		<local:Employee Name="Christina" Empid="2" ParentId="1"    				Designation="Manager"/>

		<local:Employee Name="Yang" Empid="3" ParentId="1" 					Designation="Manager"/>

		<local:Employee Name="Yoshi" Empid="4" ParentId="2" 					Designation="TeamLead"/>

		<local:Employee Name="Philip" Empid="5" ParentId="2" 					Designation="TeamLead"/>

		<local:Employee Name="Roland" Empid="6" ParentId="3" 					Designation="TeamLead"/>

		<local:Employee Name="Yuonne" Empid="7" ParentId="3" 					Designation="TeamLead"/>

		</local:Employees>

		</Window.Resources>



		  <Grid>

		<syncfusion:SfDiagram  x:Name="diagram>

		<!-- Custom Collection for Node and Connector>-->

		<syncfusion:SfDiagram.Nodes>

					  <local:NodeList></local:NodeList>

					</syncfusion:SfDiagram.Nodes>

					<syncfusion:SfDiagram.Connectors>

					  <local:ConnectorList></local:ConnectorList>

					</syncfusion:SfDiagram.Connectors>

		</syncfusion:SfDiagram>

		   </Grid>

		</Window>

   ~~~
   
6. Initialize DataSourceSettings

   To populate employee information as nodes and connectors, configure the DataSourceSettings with the DataSource, ID, and ParentId. The ID property is used as a unique identifier for each node, and the parent ID represents the parent node where a node has to be connected. The following code example illustrates how to define the DataSourceSetting and set it to the Diagram.

   ~~~ xaml

		<Window

			x:Class="EmployeeDetails.MainWindow "

			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation

			xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

			xmlns:local="clr-namespace:EmployeeDetails" >



		   <Window.Resources>



			 ……    



			 <!--Initializes the DataSourceSettings -->



			<syncfusion:DataSourceSettings 

				x:Key="DataSourceSettings" 

				DataSource="{StaticResource Employees}" 

				ParentId="ParentId" 

		Id="Empid"

					>

			 </syncfusion:DataSourceSettings>

		   </Window.Resources>



			 <Grid>

			<syncfusion:SfDiagram  

		x:Name="diagram”

		DataSourceSettings="{StaticResource DataSourceSettings}">

				 <!-- Custom Collection for Node and Connector>-->

		<syncfusion:SfDiagram.Nodes>

					  <local:NodeList></local:NodeList>

					</syncfusion:SfDiagram.Nodes>

					<syncfusion:SfDiagram.Connectors>

					  <local:ConnectorList></local:ConnectorList>

					</syncfusion:SfDiagram.Connectors>

		</syncfusion:SfDiagram>

		   </Grid>



		</Window>

   ~~~
   
7. Visualize Employees

   Now, Diagram is configured to load the employees’ information as a tree of organization chart. Next, give visual appearance for the node. To visualize the employees’ details in the Node, a node has to be created for each employee, and then the employee’s details are stored in the node’s content property. To visualize the employee information, define the appearance as a data template and apply it to the node’s content template as shown in the following code example.

   ~~~ xaml

		<Window

			x:Class="EmployeeDetails.MainWindow "

			xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

			xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

			xmlns:local="clr-namespace:EmployeeDetails" >

		   <Window.Resources>



			 ……    



			  <!—Style for Node--> 

		<Style TargetType="syncfusion:Node">

					<Setter Property="UnitWidth" Value="180" />

					<Setter Property="UnitHeight" Value="70" />

					<Setter Property="FontSize" Value="15"></Setter>

					<Setter Property="Foreground" Value="White"></Setter>

					<Setter Property="HorizontalContentAlignment               

					 Value="Stretch"></Setter>

					<Setter Property="VerticalContentAlignment" 

					 Value="Stretch"></Setter>

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



				<!--< ! -Style for the Connector>-->

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



			 <Grid>

			<syncfusion:SfDiagram  x:Name="diagram

			DataSourceSettings="{StaticResource DataSourceSettings}">

					 <!-- Custom Collection for Node and Connector>-->

			<syncfusion:SfDiagram.Nodes>

						  <local:NodeList></local:NodeList>

						</syncfusion:SfDiagram.Nodes>

						<syncfusion:SfDiagram.Connectors>

						  <local:ConnectorList></local:ConnectorList>

						</syncfusion:SfDiagram.Connectors>

			</syncfusion:SfDiagram>

		</Grid>

   ~~~

8. Initialize Layout

   Employees are initialized, populated in the Diagram, and appearance for employees are defined. Now, place the nodes and connector by using the layout manager. The following code example shows how to initialize the LayoutManager, specify the layout as the DirectedTreeLayout and set it to the Diagram.

   ~~~ xaml

		<Window x:Class="EmployeeDetails.MainWindow"

				xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

				xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

				xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

				xmlns:local="clr-namespace:EmployeeDetails"



				xmlns:layout="clr-namespace:Syncfusion.UI.Xaml.Diagram.Layout;assembly=Syncfusion.SfDiagram.Wpf"> 

			<Window.Resources>

			 …….



			  <!--Initializes the Layout-->

			<layout:DirectedTreeLayout 

				x:Key="TreeLayout" 

				HorizontalSpacing="80" 

				VerticalSpacing="50" 

				SpaceBetweenSubTrees="20" 

		Orientation="TopToBottom"/>



			<layout:LayoutManager 

				x:Name="LayoutManager"  

		Layout="{StaticResource TreeLayout}"/>

			</Window.Resources>



			<Grid>

			<syncfusion:SfDiagram  

		x:Name="diagram

		DataSourceSettings="{StaticResource DataSourceSettings}"

		LayoutManager="{StaticResource LayoutManager}">

				   <!-- Custom Collection for Node and Connector>-->

		<syncfusion:SfDiagram.Nodes>

					  <local:NodeList></local:NodeList>

					</syncfusion:SfDiagram.Nodes>

					<syncfusion:SfDiagram.Connectors>

					  <local:ConnectorList></local:ConnectorList>

					</syncfusion:SfDiagram.Connectors>

		</syncfusion:SfDiagram>

			</Grid>
		</Window>

   ~~~

The final MainWindow.Xaml looks like this.

{% highlight xaml %}

<Window x:Class="EmployeeDetails.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:syncfusion ="http://schemas.syncfusion.com/wpf" 

        xmlns:local="clr-namespace:EmployeeDetails"

xmlns:layout="using:Syncfusion.UI.Xaml.Diagram.Layout;assembly=Syncfusion.SfDiagram.Wpf">                       

<Window.Resources>

      <!-- Initializes Data-->

<local:Employees x:Key="Employees">

		<local:Employee Name="Elizabeth" Empid="1" 

Designation="CEO"/>

		<local:Employee Name="Christina" Empid="2" ParentId="1"            

                  Designation="Manager"/>

		<local:Employee Name="Yang" Empid="3" ParentId="1" 

Designation="Manager"/>

<local:Employee Name="Yoshi" Empid="4" ParentId="2" 					Designation="TeamLead"/>

<local:Employee Name="Philip" Empid="5" ParentId="2" 					Designation="TeamLead"/>

<local:Employee Name="Roland" Empid="6" ParentId="3" 					Designation="TeamLead"/>

<local:Employee Name="Yuonne" Empid="7" ParentId="3" 					Designation="TeamLead"/>

</local:Employees>



<!--Initializes the DataSourceSettings -->



<syncfusion:DataSourceSettings 

		x:Key="DataSourceSettings" 

		DataSource="{StaticResource Employees}" 

		ParentId="ParentId" 

Id="Empid">

     </syncfusion:DataSourceSettings>



       <!--< ! -Style for the Node>-->

        <Style TargetType="syncfusion:Node">

            <Setter Property="UnitWidth" Value="180" />

            <Setter Property="UnitHeight" Value="70" />

            <Setter Property="FontSize" Value="15"></Setter>

            <Setter Property="Foreground" Value="White"></Setter>

            <Setter Property="HorizontalContentAlignment" 

               Value="Stretch"></Setter>

            <Setter Property="VerticalContentAlignment" 

               Value="Stretch"></Setter>

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



        <!--< ! -Style for the Connector>-->

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



	<layout:LayoutManager x:Name="LayoutManager"  

Layout="{StaticResource TreeLayout}"/>

    </Window.Resources>



    <Grid>

	<syncfusion:SfDiagram  

x:Name="diagram

DataSourceSettings="{StaticResource DataSourceSettings}"

LayoutManager="{StaticResource LayoutManager}">

            <!-- Custom Collection for Node and Connector>-->

<syncfusion:SfDiagram.Nodes>

              <local:NodeList></local:NodeList>

            </syncfusion:SfDiagram.Nodes>

            <syncfusion:SfDiagram.Connectors>

              <local:ConnectorList></local:ConnectorList>

            </syncfusion:SfDiagram.Connectors>

</syncfusion:SfDiagram>

    </Grid>
</ Window >

{% endhighlight %}

The Employee data is displayed in the SfDiagram as follows:

![](Getting-Started_images/Getting-Started_img3.png)