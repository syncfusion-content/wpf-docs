# DataSource

SfDiagram is populated with the Node taken from an external hierarchical data source. SfDiagram exposes its specific, data-related properties and allows you to specify the data source fields where the node information is retrieved from.

DataSource Settings

Two mapping fields are necessary to map a hierarchical datasource with the diagram. Id property is used for unique identification of a record. ParentId property is used to identify the parent object to which a particular object is connected.

<table>
<tr>
<td>
Properties<br/><br/></td><td>
Description<br/><br/></td><td>
Value<br/><br/></td></tr>
<tr>
<td>
DataSource <br/><br/></td><td>
Data source based on the diagram that is to be generated.<br/><br/></td><td>
Object<br/><br/></td></tr>
<tr>
<td>
ParentId<br/><br/></td><td>
Specifies the mapping parent id property of the data source items.<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
Id<br/><br/></td><td>
Specified the mapping unique id property of data source items.<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
Root<br/><br/></td><td>
Specifies the root element of the data source items.<br/><br/></td><td>
String<br/><br/></td></tr>
</table>
DataSource

The following code example illustrates how to bind data to SfDiagram.

<table>
<tr>
<td>
diagram.Nodes = new ObservableCollection<Node>();<br/><br/>diagram.Connectors = new ObservableCollection<Connector>();<br/><br/>DataSourceSettings dataSourceSetttings = new DataSourceSettings();<br/><br/><br/><br/>dataSourceSetttings.ParentId = "ParentId";<br/><br/>dataSourceSetttings.Id = "EmpId";<br/><br/>dataSourceSetttings.Root = "1";<br/><br/>ObservableCollection<Employee> employee = new ObservableCollection<Employee>();<br/><br/>employee.Add(new Employee() { Name = "Steve", EmpId = 1, ParentId = "",<br/><br/>Designation = "CEO" });<br/><br/>employee.Add(new Employee() { Name = "Kevin", EmpId = 2, ParentId = "1", <br/><br/>Designation = "Manager" });<br/><br/>employee.Add(new Employee() { Name = "John", EmpId = 3, ParentId = "1", <br/><br/>Designation = "Manager" });<br/><br/>employee.Add(new Employee() { Name = "Raj", EmpId = 4, ParentId = "2", <br/><br/>Designation = "Team Lead" });<br/><br/>employee.Add(new Employee() { Name = "Will", EmpId = 5, ParentId = "2", <br/><br/>Designation = "S/w Developer" });<br/><br/>employee.Add(new Employee() { Name = "Sarah", EmpId = 6, ParentId = "3", <br/><br/>Designation = "TeamLead" });<br/><br/>employee.Add(new Employee() { Name = "Mike", EmpId = 7, ParentId = "3",<br/><br/>Designation = "Testing Engineer" });<br/><br/><br/><br/>dataSourceSetttings.DataSource = employee;<br/><br/>diagram.DataSourceSettings = dataSourceSetttings;<br/><br/><br/><br/></td></tr>
</table>
![](DataSource_images/DataSource_img1.jpeg)


DataSource Root:

During Automatic Layout, Node without parent is treated as Root of the layout. But, now we have provided the option to specify this Root by using the DataSource settings.

The following code illustrates how to specify the root object for the Diagram**.******

<table>
<tr>
<td>
{{'____'| markdownify }}//Object with id “Steve”, is considered as root of tree layout.****<br/><br/>diagram.DataSourceSettings.Root = “Steve”;<br/><br/><br/><br/></td></tr>
</table>
____![](DataSource_images/DataSource_img2.jpeg)
____

______DataSource__ __with__ __Root____.______

