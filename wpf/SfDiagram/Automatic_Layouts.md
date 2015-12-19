# Automatic Layouts

SfDiagram provides support to specify automatic layouts for nodes. It includes the following layout modes.

* Organization Layout
* Directed-Tree Layout
* Radial-Tree Layout

We have explained the Automatic Layout with Employee class and DataSourceSettings.The followings are initali steps for all the Layout.

1. Create Class for Data

Now, you have to create a class, Employee with properties to store the employee’s information like Team, Role, ID, reporting person ID, etc. You also have to create a collection that stores a collection of the employees.

<table>
<tr>
<td>
//Employee Business Object<br/><br/>public class Employee<br/><br/>{<br/><br/>public string Team { get; set; }<br/><br/>public string Role { get; set; }<br/><br/>public int EmpiD { get; set; }<br/><br/>}<br/><br/>//Employee Collection<br/><br/>public class Employees : ObservableCollection<Employee><br/><br/>{<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
2. Initalize Dats Source Settings
<table>
<tr>
<td>
<br/><!--Initializes the DataSourceSettings --><br/><br/><syncfusion:DataSourceSettings x:Key="DataSourceSettings" ParentId="Team" Id="Empid" <br/><br/>DataSource="{StaticResource Employees}" /><br/><br/><br/><br/><br/></td></tr>
</table>
3. Visulaize the Node and Connector
<table>
<tr>
<td>
<br/><!--Style for the Node>--><br/><br/><Style TargetType="syncfusion:Node"><br/><br/><Setter Property="UnitWidth" Value="100" /><br/><br/><Setter Property="UnitHeight" Value="50" /><br/><br/><Setter Property="FontSize" Value="14"></Setter><br/><br/><Setter Property="Foreground" Value="Black"></Setter><br/><br/><Setter Property="HorizontalContentAlignment" Value="Stretch"></Setter><br/><br/><Setter Property="VerticalContentAlignment" Value="Stretch"></Setter><br/><br/><Setter Property="Shape"><br/><br/><Setter.Value><br/><br/><RectangleGeometry Rect="10,10,10,10"></RectangleGeometry><br/><br/></Setter.Value><br/><br/></Setter><br/><br/><Setter Property="ShapeStyle"><br/><br/><Setter.Value><br/><br/><Style TargetType="Path"><br/><br/><Setter Property="Fill" Value="OliveDrab"></Setter><br/><br/><Setter Property="Stroke" Value="Black"></Setter><br/><br/><Setter Property="StrokeThickness" Value="1"></Setter><br/><br/><Setter Property="Stretch" Value="Fill"></Setter><br/><br/></Style><br/><br/></Setter.Value><br/><br/></Setter><br/><br/><Setter Property="ContentTemplate"><br/><br/><Setter.Value><br/><br/><DataTemplate><br/><br/><Border><br/><br/><TextBlock Text="{Binding Role}" TextAlignment="Center"<br/><br/>TextWrapping="Wrap" Foreground="White"  HorizontalAlignment="Center" VerticalAlignment="Center"/><br/><br/></Border><br/><br/></DataTemplate><br/><br/></Setter.Value><br/><br/></Setter><br/><br/></Style><br/><br/><!--< ! -Style for the Connector>--><br/><br/><Style TargetType="syncfusion:Connector"><br/><br/><Setter Property="ConnectorGeometryStyle"><br/><br/><Setter.Value><br/><br/><Style TargetType="Path"><br/><br/><Setter Property="Stroke" Value="Black" /><br/><br/><Setter Property="StrokeThickness" Value="1" /><br/><br/></Style><br/><br/></Setter.Value><br/><br/></Setter><br/><br/><Setter Property="TargetDecorator" Value="null"></Setter><br/><br/></Style><br/><br/></td></tr>
</table>
**Organization** **Layout**  ****

An organizational chart is a Diagram that displays the structure of an organization and relationships. To create an organizational chart, Type should be set as LayoutType.Organization. The following code example illustrates how to create an organizational chart. 

<table>
<tr>
<td>
{{'__//__'| markdownify }}{{'__Initializes__ '| markdownify }}{{'__data__ '| markdownify }}{{'__source__'| markdownify }}<br/><local:Employees x:Key="Employees"><br/><br/><local:Employee Empid="0" Role="Project Management"></local:Employee><br/><br/><local:Employee Empid= "1"  Role= "R and D Team" Team= "0"/><br/><br/><local:Employee Empid= "3"  Role= "Philosophy" Team= "1"/><br/><br/><local:Employee Empid= "4"  Role= "Organization" Team= "1"/><br/><br/><local:Employee Empid= "5"  Role= "Technology" Team= "1"/><br/><br/><local:Employee Empid= "7"  Role= "Funding" Team= "1"/><br/><br/><local:Employee Empid= "8"  Role= "Resource Allocation" Team= "1"/><br/><br/><local:Employee Empid= "9"  Role= "Targeting" Team= "1"/><br/><br/><local:Employee Empid= "11"  Role= "Evaluation" Team= "1"/><br/><br/><local:Employee Empid= "156"  Role= "HR Team" Team= "0"/><br/><br/><local:Employee Empid= "13"  Role= "Recruitment" Team= "156"/><br/><br/><local:Employee Empid= "113"  Role= "Training" Team= "156"/><br/><br/><local:Employee Empid= "112"  Role= "Employee Relation" Team= "156"/><br/><br/><local:Employee Empid= "14"  Role= "Record Keeping" Team= "156"/><br/><br/><local:Employee Empid= "15"  Role= "Compensations and Benefits" Team= "12"/><br/><br/><local:Employee Empid= "16"  Role= "Compliances" Team= "12"/><br/><br/><local:Employee Empid= "17"  Role= "Production and Sales Team" Team= "0"/><br/><br/><local:Employee Empid= "119"  Role= "Design" Team= "17"/><br/><br/><local:Employee Empid= "19"  Role= "Operation" Team= "17"/><br/><br/><local:Employee Empid= "20"  Role= "Support" Team= "17"/><br/><br/><local:Employee Empid= "21"  Role= "Quality Assurance" Team= "17"/><br/><br/><local:Employee Empid= "23"  Role= "Customer Interaction" Team= "17"/><br/><br/><local:Employee Empid= "24"  Role= "Support and Maintenance" Team= "17"/><br/><br/><local:Employee Empid= "25"  Role= "Task Coordination" Team= "17"/><br/><br/></local:Employees><br/><br/><br/><br/><!--Initializes the Layout--><br/><br/><layout:DirectedTreeLayout x:Key="TreeLayout" HorizontalSpacing="90" VerticalSpacing="50"<br/><br/>SpaceBetweenSubTrees="20"Orientation="TopToBottom"/><br/><br/><layout:LayoutManager x:Key="LayoutManager"<br/><br/>Layout="{StaticResource TreeLayout}"/><br/><br/></td></tr>
</table>
![](AutomaticLayouts_images/AutomaticLayouts_img1.jpeg)


Organizational chart layout starts parsing from root and iterate through all its child elements. ‘GetLayoutInfo’ method provides necessary information of a Node’s children and the way to arrange (Orientation, Type etc.) them. You can customize the arrangements by overriding this function as explained.

GetLayoutInfo

User can change ChartType and Orientation by using GetLayoutInfo event of the SfDiagram. This event will fire for each Node added in Layout when the layout is getting updated. Default ChartType us Alternate and default orientation is Vertical. The following code example illustrates how to register an event and how to change ChartType and orientation.

**Event** **Arguments****:******

<table>
