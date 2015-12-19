# Getting Started

**Creating** **Simple** **Diagram****:******

This section demonstrates how to visualize the Employee details in the Organizational Chart arrangement by using the SfDiagram.****

1. **Add** **the** **SfDigram** **from** **the** **Toolbox******

Drag and drop the SfDiagram control from the Toolbox to the XAML Page

![](GettingStarted_images/GettingStarted_img1.jpeg)


The xmlns name space is added to the MainWindow.xaml

![C:/Users/ramya.t/Desktop/1.png](GettingStarted_images/GettingStarted_img2.jpeg)


**2****.** **Initialize** **the** **SfDiagram******

The SfDiagram exists in the [http://schemas.syncfusion.com/wpf](http://schemas.syncfusion.com/wpf# "")  namespace. Initialize SfDiagram to the XAML Page as shown in the following code sample.

<table>
<tr>
<td>
<Window<br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"<br/><br/><Grid><br/><br/>******<****syncfusion****:****SfDiagram** **x****:****Name****="****diagram****">******<br/><br/>********<br/><br/>******</****syncfusion****:****SfDiagram****>******<br/><br/></Grid><br/><br/><br/><br/></Window><br/><br/></td></tr>
</table>
**3****.** **Initialize** **Nodes** **and** **Connectors******

To initialize the Nodes and Connectors properties of the SfDiagram, Nodes property is assigned with the NodeCollection, that is, ObservableCollection of the Node. Connector’s property is assigned with the ConnectorCollection, that is, ObservableCollection of the Connector.

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"<br/><br/><Grid><br/><br/>**<****syncfusion****:****SfDiagram** **x****:****Name****="****diagram****">******<br/><br/>******<****syncfusion****:****SfDiagram****.****Nodes****>******<br/><br/>**************<****syncfusion****:****NodeCollection** **/>******<br/><br/>******</****syncfusion****:****SfDiagram****.****Nodes****>**       ****<br/><br/>******<****syncfusion****:****SfDiagram****.****Connectors****>******<br/><br/>**********<****syncfusion****:****ConnectorCollection****/>******<br/><br/>******</****syncfusion****:****SfDiagram****.****Connectors****>******<br/><br/>******</****syncfusion****:****SfDiagram****>******<br/><br/></Grid><br/><br/></Window><br/><br/><br/><br/></td></tr>
</table>
****<table>
<tr>
<td>
namespace EmployeeDetails<br/><br/>{<br/><br/>public partial class MainWindow : Window<br/><br/>{<br/><br/>public MainWindow()<br/><br/>{<br/><br/>this.InitializeComponent();<br/><br/>}<br/><br/>}<br/><br/>**//** **Employee** **Collection****.******<br/><br/>******public** **class** **Employees** **:** **ObservableCollection****<****Employee****>******<br/><br/>******{******<br/><br/>**********}******<br/><br/>}<br/><br/>****<br/><br/></td></tr>
</table>
******4****.** **Create** **class** **to** **store** **employee** **information******

Now, you have to create a class, Employee with properties to store the employee’s information like name, designation, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

<table>
<tr>
<td>
namespace EmployeeDetails<br/><br/>{<br/><br/>public partial class MainWindow : Window<br/><br/>{<br/><br/>public MainWindow()<br/><br/>{<br/><br/>InitializeComponent();<br/><br/>}<br/><br/>}<br/><br/>**//****Employee** **Business** **Object******<br/><br/>******public** **class** **Employee******<br/><br/>******{******<br/><br/>**********public** **string** **ParentId** **{** **get****;** **set****;** **}******<br/><br/>**********public** **string** **Name** **{** **get****;** **set****;** **}******<br/><br/>**********public** **string** **Designation** **{** **get****;** **set****;** **}******<br/><br/>**********public** **int** **EmpID** **{** **get****;** **set****;** **}******<br/><br/>******}******<br/><br/>****//Employee Collection<br/><br/>public class Employees : ObservableCollection<Employee><br/><br/>{<br/><br/>}<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
******5****.** **Initialize** **Data******

Create a collection of employees with each employee having an ID in the Epmid and the reporting person’s ID in the Parent ID. This collection is placed in the Window resource and later incorporated in the Diagram. This is explained in the next point.

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"<br/><br/><Window.Resources><br/><br/>******<!--** **Initializes** **the** **employee** **colletion****-->******<br/><br/>**********<****local****:****Employees** **x****:****Key****="****Employees****">******<br/><br/>**********<****local****:****Employee** **Name****="****Elizabeth****"** **Empid****="****1****"** **ParentId****=""****Designation****="****CEO****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Christina****"** **Empid****="****2****"** **ParentId****="****1****"** **Designation****="****Manager****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Yang****"** **Empid****="****3****"** **ParentId****="****1****"** **Designation****="****Manager****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Yoshi****"** **Empid****="****4****"** **ParentId****="****2****"** **Designation****="****TeamLead****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Philip****"** **Empid****="****5****"** **ParentId****="****2****"** **Designation****="****TeamLead****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Roland****"** **Empid****="****6****"** **ParentId****="****3****"** **Designation****="****TeamLead****"/>******<br/><br/>******<****local****:****Employee** **Name****="****Yuonne****"** **Empid****="****7****"** **ParentId****="****3****"** **Designation****="****TeamLead****"/>******<br/><br/>**********</****local****:****Employees****>******<br/><br/></Window.Resources><br/><br/><Grid><br/><br/><syncfusion:SfDiagram x:Name="diagram"><br/><br/><syncfusion:SfDiagram.Nodes><br/><br/><syncfusion:NodeCollection /><br/><br/></syncfusion:SfDiagram.Nodes>       <br/><br/><syncfusion:SfDiagram.Connectors><br/><br/><syncfusion:ConnectorCollection/><br/><br/></syncfusion:SfDiagram.Connectors><br/><br/></syncfusion:SfDiagram><br/><br/></Grid><br/><br/></Window> <br/><br/>****<br/><br/></td></tr>
</table>
******6****.** **Initialize** **DataSourceSettings******

To populate employee information as Nodes and connectors, configure the DataSourceSettings with the DataSource, ID, and ParentId. The ID property is used as a unique identifier for each Node, and the parent ID represents the parent Node where a Node has to be connected. The following code example illustrates how to define the DataSourceSetting and set it to the Diagram

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"<br/><br/><Window.Resources><br/><br/>**********……….******<br/><br/>**********<!--****Initializes** **the** **DataSourceSettings** **-->******<br/><br/>**********<****syncfusion****:****DataSourceSettings** **x****:****Key****="****DataSourceSettings****"** ****<br/><br/>**************ParentId****="****ParentId****"**    **Id****="****Empid****"******<br/><br/>******DataSource****="{****StaticResource** **Employees****}">******<br/><br/>******</****syncfusion****:****DataSourceSettings****>******<br/><br/></Window.Resources><br/><br/><Grid><br/><br/><syncfusion:SfDiagram x:Name="diagram" <br/><br/>DataSourceSettings="{StaticResource DataSourceSettings}"><br/><br/><syncfusion:SfDiagram.Nodes><br/><br/><syncfusion:NodeCollection /><br/><br/></syncfusion:SfDiagram.Nodes>       <br/><br/><syncfusion:SfDiagram.Connectors><br/><br/><syncfusion:ConnectorCollection/><br/><br/></syncfusion:SfDiagram.Connectors><br/><br/></syncfusion:SfDiagram><br/><br/></Grid><br/><br/></Window><br/><br/>****<br/><br/></td></tr>
</table>
******7****.** **Visualize** **Employees******

Now, Diagram is configured to load the employees’ information as a tree of organization chart. Next, give visual appearance for the Node. To visualize the employees’ details in the Node, a Node has to be created for each employee, and then the employee’s details are stored in the Node’s content property. To visualize the employee information, define the appearance as a data template and apply it to the Node’s content template as shown in the following code example.

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"<br/><br/><Window.Resources><br/><br/>**********……….******<br/><br/>**********<!--****Style** **for** **the** **Node****>-->******<br/><br/>**********<****Style** **TargetType****="****syncfusion****:****Node****">******<br/><br/>**********<****Setter** **Property****="****UnitWidth****"** **Value****="****100****"** **/>******<br/><br/>******<****Setter** **Property****="****UnitHeight****"** **Value****="****40****"** **/>******<br/><br/>******<****Setter** **Property****="****FontSize****"** **Value****="****15****">** **</****Setter****>******<br/><br/>******<****Setter** **Property****="****Foreground****"** **Value****="****Black****">** **</****Setter****>******<br/><br/>******<****Setter** **Property****="****HorizontalContentAlignment****"** **Value****="****Stretch****">** **</****Setter****>******<br/><br/>******<****Setter** **Property****="****VerticalContentAlignment****"** **Value****="****Stretch****">** **</****Setter****>******<br/><br/>**********<****Setter** **Property****="****ContentTemplate****">******<br/><br/>******<****Setter****.****Value****>******<br/><br/>******<****DataTemplate****>******<br/><br/>******<****Border** **Background****="#****008b8b****"** ****<br/><br/>******CornerRadius****="****5****">******<br/><br/>******<****TextBlock** **Text****="{****Binding** **Name****}"** **Foreground****="****White****"******<br/><br/>******************HorizontalAlignment****="****Center****"** **VerticalAlignment****="****Center****"/>**                                   ****<br/><br/>******</****Border****>******<br/><br/>******</****DataTemplate****>******<br/><br/>******</****Setter****.****Value****>******<br/><br/>******</****Setter****>******<br/><br/>**********</****Style****>******<br/><br/>**********<!--****Style** **for** **the** **Connector****>-->******<br/><br/>**********<****Style** **TargetType****="****syncfusion****:****Connector****">******<br/><br/>******<****Setter** **Property****="****ConnectorGeometryStyle****">******<br/><br/>******<****Setter****.****Value****>******<br/><br/>******<****Style** **TargetType****="****Path****">******<br/><br/>******<****Setter** **Property****="****Stroke****"** **Value****="****Black****"** **/>******<br/><br/>******<****Setter** **Property****="****StrokeThickness****"** **Value****="****1****"** **/>******<br/><br/>******</****Style****>******<br/><br/>******</****Setter****.****Value****>******<br/><br/>******</****Setter****>******<br/><br/>******</****Style****>******<br/><br/></Window.Resources><br/><br/><Grid><br/><br/><syncfusion:SfDiagram x:Name="diagram" <br/><br/>DataSourceSettings="{StaticResource DataSourceSettings}"><br/><br/><syncfusion:SfDiagram.Nodes><br/><br/><syncfusion:NodeCollection /><br/><br/></syncfusion:SfDiagram.Nodes>       <br/><br/><syncfusion:SfDiagram.Connectors><br/><br/><syncfusion:ConnectorCollection/><br/><br/></syncfusion:SfDiagram.Connectors><br/><br/></syncfusion:SfDiagram><br/><br/></Grid><br/><br/></Window><br/><br/><br/><br/></td></tr>
</table>
******8****.** **Initialize** **Layout******

Employees are initialized, populated in the Diagram, and appearance for employees are defined. Now, place the nodes and connector by using the layout manager. The following code example shows how to initialize the LayoutManager, specify the layout as the DirectedTreeLayout and set it to the Diagram.

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"><br/><br/><Window.Resources><br/><br/>******……….******<br/><br/>******<!--****Initializes** **the** **Layout****-->******<br/><br/>**********<****syncfusion****:****DirectedTreeLayout** **x****:****Key****="****TreeLayout****"** ****<br/><br/>**************HorizontalSpacing****="****80****"** ****<br/><br/>**************VerticalSpacing****="****50****"** ****<br/><br/>**************SpaceBetweenSubTrees****="****20****"** ****<br/><br/>**************Orientation****="****TopToBottom****"/>******<br/><br/>**********<****syncfusion****:****LayoutManager** **x****:****Key****="****LayoutManager****"**  ****<br/><br/>**************Layout****="{****StaticResource** **TreeLayout****}"/>******<br/><br/></Window.Resources><br/><br/><Grid><br/><br/><syncfusion:SfDiagram x:Name="diagram" <br/><br/>DataSourceSettings="{StaticResource DataSourceSettings}"<br/><br/>LayoutManager="{StaticResource LayoutManager}"><br/><br/><syncfusion:SfDiagram.Nodes><br/><br/><syncfusion:NodeCollection /><br/><br/></syncfusion:SfDiagram.Nodes>       <br/><br/><syncfusion:SfDiagram.Connectors><br/><br/><syncfusion:ConnectorCollection/><br/><br/></syncfusion:SfDiagram.Connectors><br/><br/></syncfusion:SfDiagram><br/><br/></Grid><br/><br/></Window><br/><br/><br/><br/></td></tr>
</table>
The final MainWindow.Xaml looks like this.

<table>
<tr>
<td>
<Window <br/><br/>x:Class="EmployeeDetails.MainWindow"<br/><br/>xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"<br/><br/>xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br/><br/>xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br/><br/>xmlns:local="clr-namespace:EmployeeDetails"><br/><br/><Window.Resources><br/><br/><!-- Initializes the employee colletion--><br/><br/><local:Employees x:Key="Employees"><br/><br/><local:Employee Name="Elizabeth" Empid="1" ParentId=""Designation="CEO"/><br/><br/><local:Employee Name="Christina" Empid="2" ParentId="1" Designation="Manager"/><br/><br/><local:Employee Name="Yang" Empid="3" ParentId="1" Designation="Manager"/><br/><br/><local:Employee Name="Yoshi" Empid="4" ParentId="2" Designation="TeamLead"/><br/><br/><local:Employee Name="Philip" Empid="5" ParentId="2" Designation="TeamLead"/><br/><br/><local:Employee Name="Roland" Empid="6" ParentId="3" Designation="TeamLead"/><br/><br/><local:Employee Name="Yuonne" Empid="7" ParentId="3" Designation="TeamLead"/><br/><br/></local:Employees><br/><br/><!--Initializes the DataSourceSettings --><br/><br/><syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="ParentId"Id="Empid" DataSource="{StaticResource Employees}"><br/><br/></syncfusion:DataSourceSettings><br/><br/><!--Style for the Node>--><br/><br/><Style TargetType="syncfusion:Node"><br/><br/><Setter Property="UnitWidth" Value="80" /><br/><br/><Setter Property="UnitHeight" Value="40" /><br/><br/><Setter Property="FontSize" Value="15"> </Setter><br/><br/><Setter Property="Foreground" Value="Black"> </Setter><br/><br/><Setter Property="HorizontalContentAlignment" Value="Stretch"> </Setter><br/><br/><Setter Property="VerticalContentAlignment" Value="Stretch"> </Setter><br/><br/><Setter Property="ContentTemplate"><br/><br/><Setter.Value><br/><br/><DataTemplate><br/><br/><Border Background="#008b8b" <br/><br/>CornerRadius="5"><br/><br/><TextBlock Text="{Binding Name}" Foreground="White"<br/><br/>HorizontalAlignment="Center"  VerticalAlignment="Center"/>                                <br/><br/></Border><br/><br/></DataTemplate><br/><br/></Setter.Value><br/><br/></Setter><br/><br/></Style><br/><br/><!--Style for the Connector>--><br/><br/><Style TargetType="syncfusion:Connector"><br/><br/><Setter Property="ConnectorGeometryStyle"><br/><br/><Setter.Value><br/><br/><Style TargetType="Path"><br/><br/><Setter Property="Stroke" Value="Black" /><br/><br/><Setter Property="StrokeThickness" Value="1" /><br/><br/></Style><br/><br/></Setter.Value><br/><br/></Setter><br/><br/></Style><br/><br/><!--Initializes the Layout--><br/><br/><syncfusion:DirectedTreeLayout x:Key="TreeLayout" <br/><br/>HorizontalSpacing="80" <br/><br/>VerticalSpacing="50" <br/><br/>SpaceBetweenSubTrees="20" <br/><br/>Orientation="TopToBottom"/><br/><br/><syncfusion:LayoutManager x:Key="LayoutManager"  <br/><br/>Layout="{StaticResource TreeLayout}"/><br/><br/><Style TargetType="Path" x:Key="Deco1"><br/><br/><Setter Property="Stroke" Value="Black" /><br/><br/><Setter Property="StrokeThickness" Value="3" /><br/><br/></Style><br/><br/></Window.Resources><br/><br/><Grid>        <br/><br/><syncfusion:SfDiagram x:Name="diagram" <br/><br/>DataSourceSettings="{StaticResource DataSourceSettings}"<br/><br/>LayoutManager="{StaticResource LayoutManager}"><br/><br/><syncfusion:SfDiagram.Nodes><br/><br/><syncfusion:NodeCollection /><br/><br/></syncfusion:SfDiagram.Nodes>       <br/><br/><syncfusion:SfDiagram.Connectors><br/><br/><syncfusion:ConnectorCollection/><br/><br/></syncfusion:SfDiagram.Connectors><br/><br/></syncfusion:SfDiagram><br/><br/></Grid><br/><br/></Window> <br/><br/><br/><br/></td></tr>
</table>
The Employee data is displayed in the SfDiagram as follows

![](GettingStarted_images/GettingStarted_img3.jpeg)


