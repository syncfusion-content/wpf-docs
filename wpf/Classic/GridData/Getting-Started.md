---
layout: post
title: Getting Started with WPF GridData Control | Syncfusion
description: Learn here all about getting started with Syncfusion WPF GridDataControl (Classic) control and more.
platform: wpf
control: GridData (Classic)
 documentation: ug
---

# Getting Started with WPF GridDataControl (Classic)

This section is designed to help you understand and quickly get started using Essential Grid in your WPF application. Control appearance and structure are defined and the Essential Grid’s relevant classes are depicted.

The following sections comprise the Getting Started section:

## Appearance and Structure of the Grid

EssentialGrid for WPF is a package of powerful grid controls that provides cell-oriented features and acts as an efficient display engine for tabular data that can be customized down to the cell level. It also offers excellent performance characteristics, such as a virtual mode and high-frequency updates, which makes the grid suitable for real-time applications.

The EssentialGrid package is comprised of following three types of grid controls:

* Grid Control
* GridData Control
* GridTree Control

Now, take closer look at the characteristics of each of these controls. 

### Grid Control

This is a general-purpose grid that can be used in any form, either holding its own data or virtually bound to an external data source. It acts as a base grid for the other two types of grids (the GridData and GridTree controls). Most features are shared among the three grid types. 

In the Grid control, each cell acts as a single entity, which is suitable for applications such as Excel simulator, where the data in the grid cells are not interrelated and need to be maintained in the specific cells themselves. You can also operate this control in virtual mode, where data is not stored in the grid’s internal data structure but comes from an external source like a data table, for example. In virtual mode, data is dynamically loaded into the grid on demand or when users need to view the data.

![WPF GridControl overview](Getting-Started_images/Getting-Started_img1.png)

### GridData Control

The GridData control is designed to be bound with a data source. In the GridData control, each column behaves as a single entity. This grid is more column-centric and can be used to display interrelated tabular data. Unlike the base grid, this grid does not store data values in its data structures; instead, it is connected to an external data source.

For more detailed information about data source connections, refer to the Data Binding section. 

![WPF GridDataControl overview](Getting-Started_images/Getting-Started_img2.png)

### GridTree Control

The GridTree control serves as a multicolumn tree control that is optimized to display thousands of items. This control uses a load-on-demand architecture to quickly generate a tree view. You can toggle the view of the underlying nodes by clicking the plus-minus glyphs of a root node. This control provides complete customization options such as custom level styles, glyphs, node images, and more.

![WPF GridTreeControl overview](Getting-Started_images/Getting-Started_img3.png)

## Class Diagram 

The following illustration depicts the Class Diagram for Essential Grid for WPF.

### Control Hierarchy

![Control hierarchy in WPF GridData control](Getting-Started_images/Getting-Started_img4.png)

### Model Hierarchy

![Model hierarchy in WPF GridData control](Getting-Started_images/Getting-Started_img5.png)

## Add Essential Grid to an Application

This section serves as a guide on how to deploy EssentialGrid in an application.

### Add the Grid Control to a WPF Application

In this section, you can see how to add the Grid control to a WPF application and load random data. The Grid control can be added to an application through one of the following methods: through a designer or programmatically.

Adding the Grid Control through a Designer

Please follow the steps below to add the Grid control through a designer.

1. Create new WPF application.
2. Open the Designer window.
3. Drag ScrollViewer from the Toolbox and drop it in the Designer window (Since the Grid control doesn’t have a built-in ScrollViewer, to make the grid flow based on data, the grid should be placed inside the ScrollViewer control.

   ![Drag the ScrollViewer from toolbox](Getting-Started_images/Getting-Started_img6.png)

4. Drag GridControl from the Toolbox and drop it inside the ScrollViewer.

   ![Drag the GridControl from toolbox](Getting-Started_images/Getting-Started_img7.png)

5. Once you drag GridControl and drop it in ScrollViewer, the grid control is added to the designer and its dependent assemblies are added to the project.

   ![WPF GridControl added to the designer](Getting-Started_images/Getting-Started_img8.png)

### Programmatically Adding the Grid Control

Instead of adding it through a designer such a Visual Studio, you can add the Grid control programmatically.

1. Create a new WPF application.

2. Add the following Syncfusion assemblies to the project.
   1. Syncfusion.Core.dll
   2. Syncfusion.Grid.Wpf.dll
   3. Syncfusion.GridCommon.Wpf.dll
   4. Syncfusion.Shared.Wpf.dll

   ![Added assemblies to the WPF GridData control project](Getting-Started_images/Getting-Started_img9.png)

3. Name the root Grid as layoutRoot in the application’s XAML page.

   ~~~ xaml

		<Grid Name="layoutRoot"/>    

   ~~~  
   
4. Create ScrollViewer and GridControl in code. 

5. To add the grid to the view, add GridControl as content of ScrollViewer and then add the ScrollViewer as a child of layoutRoot (Grid).

   ~~~ csharp

		//ScrollViewer defined here

		ScrollViewer ScrollViewer = new ScrollViewer();

		//GridControl defined here

		GridControl gridControl = new GridControl();

		//GridControl set as the content of the ScrollViewer

		ScrollViewer.Content = gridControl;     

		//To bring the Grid control to the view, ScrollViewer should be set as a child of LayoutRoot      

		this.layoutRoot.Children.Add(ScrollViewer);   

   ~~~

### Populating the Grid control

The Grid control is a cell-based control, so to populate it, RowCount and ColumnCount are mandatory. Once ColumnCount and RowCount are specified, data can be populated by using one of the following methods. 

1. You can populate data by looping through the cells in the Grid control. The following code explains this scenario.

   ~~~ csharp

		//Specifying row and column count

		gridControl.Model.RowCount = 100;

		gridControl.Model.ColumnCount = 20;

		//Looping through the cells and assigning the values based on row and column index

		for (int i = 0; i < 100; i++)

		{
		    for (int j = 0; j < 20; j++)

		    {
		        gridControl.Model[i, j].CellValue = string.Format("{0}/{1}", i, j);

		    }
		}

   ~~~

2. You can populate data by handling the QueryCellInfo event of gridControl. This loads the data in and on-demand basis, ensuring optimized performance.

   ~~~ csharp

		//Specifying row and column count

		gridControl.Model.RowCount = 100;

		gridControl.Model.ColumnCount = 20;

		this.gridControl.QueryCellInfo += new Syncfusion.Windows.Controls.Grid.GridQueryCellInfoEventHandler(gridControl_QueryCellInfo);

		//Assigning values by handling the QueryCellInfo event

		 void gridControl_QueryCellInfo(object sender, Syncfusion.Windows.Controls.Grid.GridQueryCellInfoEventArgs e)

		 {
		   e.Style.CellValue=string.Format("{0}/{1}", e.Cell.RowIndex, e.Cell.ColumnIndex);

		 }   

   ~~~

3. Now, run the application. The grid appears as follows. 

   ![Show the data of WPF GridControl](Getting-Started_images/Getting-Started_img10.png)

### Add the GridData Control to a WPF Application

This section shows you how to add a GridData control to a WPF application and how to bind data from a database and an IEnumerable Collection to the GridData control. The GridData control can be added to an application through programmatically.

### Programmatically Adding the GridData Control:

1. Create a new WPF application.

2. Add the following Syncfusion assemblies to the project.
   1. Syncfusion.Core.dll
   2. Syncfusion.Grid.Wpf.dll
   3. Syncfusion.Linq.Base.dll
   4. Syncfusion.GridCommon.Wpf.dll
   5. Syncfusion.Shared.Wpf.dll

   ![Added assemblies to the project](Getting-Started_images/Getting-Started_img13.png)

3. Name the root grid as layoutRoot in the application’s XAML page.

   ~~~ csharp

		<Grid Name="layoutRoot"/> 

   ~~~
   
4. Create a new GridDataControl in code and add it as a child of layoutRoot (Grid). This adds GridDataControl to the view.

   ~~~ csharp

		//GridDataControl defined here

		GridDataControl dataGrid = new GridDataControl();

		//To bring GridDataControl to the view, it should be added to the children of 

		layoutRoot.

		layoutRoot.Children.Add(dataGrid);

   ~~~   

### Binding a Data Source to the GridData Control

The previous section explained how to add a GridData control to an application. This section explains how to bind a data source with the GridData control after it is added.

The GridData control supports all popular data sources including observable collections, data tables, collection view sources, business objects generated by the ADO.NET Entity Framework, LINQ to SQL or any other ORM.ADO.NET, data views, ICollection views, object data providers, IEnumerable, IList, IBindingList, IQueryable, and ITypedList. 

This section explains how to bind data tables and IEnumerable collections to the GridData control.

### Binding Data Tables to the GridData Control

This section explains how to bind a data table from a database to the GridData control.

1. Connect a database to the current application. The database can be connected several ways, such as ADO.NET, LNQ to SQL, classes, etc. In this example, we have directly established a connection to a simple Northwind.sdf database.

2. Once the connection is established, fetch the required data table from the database. Below, a data table has been fetched from the connected Northwind.sdf by using SQL DataAdapter.

   N> Check that System.data.SqlServerCe.dll has been added to your project before using this procedure.

   ~~~ csharp

		public class Data

		{

		   public static DataTable GetDataTable()

		   {

		      //Connection string 

		    using (SqlCeConnection con = new SqlCeConnection(string.Format(@"Data Source = {0}", "C:\\Northwind.sdf")))//Path where .sdf file is placed.

		     {

		       //Establish the connection

		        con.Open();                    

		        SqlCeDataAdapter sda = new SqlCeDataAdapter("SELECT * FROM Customers", con);

		        DataTable dt = new DataTable();

		        sda.Fill(dt);

		        return dt;
		       }

		     }
		}

   ~~~

3. Now bind the data table as an ItemsSource of GridDataControl, either in XAML or in code.

   ~~~ xaml

		<syncfusion:GridDataControl Name="dataGrid"

		                            HorizontalAlignment="Left"

		                            VerticalAlignment="Top"

		                            ItemsSource="{Binding GDCSource}"/>

   ~~~

   ~~~ csharp

		public MainWindow()

		{

		    InitializeComponent();

		    this.DataContext = this;

		}

		public DataTable GDCSource

		{

		    get

		    {

		       return Data.GetDataTable();

		    }

		}



		Assigning the Items’ Source in Code



		public MainWindow()

		{

		    InitializeComponent();

		//ItemsSource set to GridDataControl

		    this.dataGrid.ItemsSource = Data.GetDataTable();

		}

   ~~~

Once the application runs, the following output is generated.

![Binding data tables to the WPF GridData control](Getting-Started_images/Getting-Started_img14.png)

#### Samples

To view samples, follow these steps: 

1. Select Start > Programs > Syncfusion > Essential Studio xx.x.x.xx > Dashboard.
2. Click Run Samples for WPF under the User Interface Edition panel.
3. Select GridDataControl.
4. Expand the Data Binding Features item in the Sample Browser.
5. Choose the Data Table Demo sample to launch.

### Binding an IEnumerable Collection of GridDataControl

1. Create a collection of objects to bind with the GridData control. In this sample, we have created a collection of objects containing personnel information.

   ~~~ csharp

		//The following is used to create a simple list collection

		public class PersonDetails : List<Person>

		{

		  public PersonDetails()

		  {

		            this.Add(new Person() { CustomerID = "ALKI", CompanyName = "Alfreds Futterkiste", ContactName = "Maria Anders", ContactTitle = "Sales Representative" });

		            this.Add(new Person() { CustomerID = "ANATR", CompanyName = "Ana Trujillo Emparedado", ContactName = "Ana Trujillo", ContactTitle = "Owner" });

		            this.Add(new Person() { CustomerID = "ANTON", CompanyName = "Antonio Moreno Taqurea", ContactName = "Antonio Moreno", ContactTitle = "Owner" });

		            this.Add(new Person() { CustomerID = "ALKI", CompanyName = "Alfreds Futterkiste", ContactName = "Maria Anders", ContactTitle = "Sales Representative" });

		            this.Add(new Person() { CustomerID = "AROUT", CompanyName = "Around the Horn", ContactName = "Thomas Hardy", ContactTitle = "Sales Representative" });

		            this.Add(new Person() { CustomerID = "BERGS", CompanyName = "Berglunds snabbkop", ContactName = "christinaBerglund", ContactTitle = "Sales Representative" });

		            this.Add(new Person() { CustomerID = "BLONP", CompanyName = "Blondel pere et fils", ContactName = "Frederique Citeaux", ContactTitle = "Marketing Manager" });

		            this.Add(new Person() { CustomerID = "BOLID", CompanyName = "BOlido Comidas preparad", ContactName = "Martin Sommer", ContactTitle = "Owner" });

		            this.Add(new Person() { CustomerID = "BONAP", CompanyName = "Bon app", ContactName = "Laurence Lebihan", ContactTitle = "Owner" });

		        }

		    }

		    public class Person

		    {

		        public string CustomerID

		        { get; set; }

		        public string CompanyName

		        { get; set; }

		        public string ContactName

		        { get; set; }

		        public string ContactTitle

		        { get; set; }

		        public string Address

		        { get; set; }

		        public string City

		        { get; set; }

		        public string Region

		        { get; set; }

		    }

   ~~~

2. Bind the collection as item sources of GridDataControl, either in XAML or in code.

   ~~~ xaml

		<syncfusion:GridDataControl Name="dataGrid" AutoPopulateColumns="True" ItemsSource="{Binding GDCSource}"/>

   ~~~

   ~~~ csharp

		public MainWindow()

		{

		    InitializeComponent();

		    this.DataContext = this;

		}



		private PersonDetails _gdcSource = new PersonDetails();



		//This property sets as ItemsSource of GridDataControl

		public PersonDetails GDCSource

		{

		   get

		   {

		      return _gdcSource;

		   }

		   set

		   {

		       _gdcSource = value;

		   }

		}
		
		Assigning the Items Source in Code 

		public MainWindow()

		{

		    InitializeComponent();



			//ItemsSource set to GridDataControl

		    this.dataGrid.ItemsSource = this.GDCSource;

		}

   ~~~

When the application runs, the following output is generated.

![Binding with IEnumerable collection of WPF GridData control](Getting-Started_images/Getting-Started_img15.png)

### Add the GridTree Control to a WPF Application

This section demonstrates how to add a GridTree control to a WPF application and how to load the grid with a data source. The GridTree control can be added to an application through programmatically.

### Programmatically Adding GridTree Control

1. Create a new WPF application.

2. Add the following Syncfusion assemblies to the project.
   1. Syncfusion.Core.dll
   2. Syncfusion.Grid.Wpf.dll
   3. Syncfusion.GridCommon.Wpf.dll
   4. Syncfusion.Shared.Wpf.dll
   
   ![Added assemblies for WPF GridTreeControl](Getting-Started_images/Getting-Started_img18.png)

3. Name the root grid as layoutRoot in the application’s XAML page.	

   ~~~ xaml

		<Grid Name="layoutRoot"/> 

   ~~~  
   
4. Create a new GridTreeControl in code and add it as a child of layoutRoot (Grid). Now GridTreeControl is added to the view.

   ~~~ xaml

		//GridTreeControl defined here

		GridTreeControl treeGrid = new GridTreeControl();

		//To bring the GridTreeControl to the view, GridTreeControl should be added to the children of layoutRoot.

		layoutRoot.Children.Add(treeGrid);

   ~~~

### Data Population in the GridTree Control

The previous section explained how to add the GridTree control to an application. This section explains how to populate data in the GridTree control. There are three approaches to populating data:

* With the RequestTreeItems event.
* By self-relational collection binding.
* Using data-view binding.

### The RequestTreeItems Event

The GridTree control can populate data on demand by handling the RequestTreeItems event. GridTreeControl receives the source of root and child nodes through this event handler. This event is triggered when initially loading and expanding nodes.

To populate data using this event, follow these steps:

1. Create a collection of objects to bind with the GridTree control. In this example, a collection of objects containing employee information has been created.

   ~~~ csharp

		public class EmployeesCollection:List<Employee>

		    {

		        public EmployeesCollection()

		        {          

		            this.Add(new Employee() { Title = "Management", ReportsTo = -1, ID = 2 });

		            this.Add(new Employee() { Title = "Accounts", ReportsTo = -1, ID = 3 });

		            this.Add(new Employee() { Title = "Sales", ReportsTo = -1, ID = 4 });            

		            //Management

		            this.Add(new Employee() { FirstName = "Andrew", LastName = "Fuller",Department = "Management", EmpID = 1001, ID = 9, Salary = 1200000, ReportsTo = 2, Title = "Vice President" });

		            this.Add(new Employee() { FirstName = "Janet", LastName = "Leverling", Department = "Management", EmpID = 1002, ID = 10, Salary = 1000000, ReportsTo = 2, Title = "GM" });           

		            //Accounts

		            this.Add(new Employee() { FirstName = "Nancy", LastName = "Davolio",Department = "Accounts", EmpID = 1004, ID = 12,  Salary = 850000, ReportsTo = 3, Title = "Accounts Manager" });

		            this.Add(new Employee() { FirstName = "Margaret", LastName = "Peacock", Department = "Accounts", EmpID = 1008, ID = 13, Salary = 700000, ReportsTo = 3, Title = "Accountant" });



		            //Sales

		            this.Add(new Employee() { FirstName = "Laura", LastName = "Callahan", Department = "Sales", EmpID = 1005, ID = 16, Salary = 900000, ReportsTo = 4, Title = "Sales Manager" });

		            this.Add(new Employee() { FirstName = "Anne", LastName = "Dodsworth",  Department = "Sales", EmpID = 1011, ID = 17, Salary = 800000, ReportsTo = 4, Title = "Sales Representative" });                  



		        }

		    }



		    public class Employee

		    {

		        int id;       

		        public int ID

		        {

		            get { return id; }

		            set { id = value; }

		        }

		        int? empId;

		        public int? EmpID

		        {

		            get { return empId; }

		            set { empId = value; }

		        }

		        string firstName;

		        public string FirstName

		        {

		            get { return firstName; }

		            set { firstName = value; }

		        }

		        string lastName;

		        public string LastName

		        {

		            get { return lastName; }

		            set { lastName = value; }

		        }

		        string department;

		        public string Department

		        {

		            get { return department; }

		            set { department = value; }

		        }

		        private string title;

		        public string Title

		        {

		            get { return title; }

		            set { title = value; }

		        }

		        double? salary;

		        public double? Salary

		        {

		            get { return salary; }

		            set { salary = value; }

		        }

		        int reportsTo;        

		        public int ReportsTo

		        {

		            get { return reportsTo; }

		            set { reportsTo = value; }

		        }       

		    }

   ~~~
   
2. The RequestTreeItems event can hook in either XAML or code.

   Hooking RequestTreeItems Event in XAML

   ~~~ xaml

		<syncfusion:GridTreeControl Name="treeGrid" 

					RequestTreeItems="treeGrid_RequestTreeItems" 
	
					EnableNodeSelection="False"  

					AutoPopulateColumns="True"  

					PercentSizingBehavior="SizeUntouchedColumns" >

   ~~~

   Hooking RequestTreeItems Event in Code

   ~~~ csharp

		this.treeGrid.RequestTreeItems+=new GridTreeRequestTreeItemsHandler(treeGrid_RequestTreeItems);

   ~~~

3. Handle the RequestTreeItems event to pass the source to the root and child nodes dynamically.

   ~~~ csharp

		EmployeesCollection employees;

		public MainWindow()

		{

		  InitializeComponent();         

		  this.gridTreeControl1.RequestTreeItems += new Syncfusion.Windows.Controls.Grid.GridTreeRequestTreeItemsHandler(treeGrid_RequestTreeItems);

		  employees = new EmployeesCollection();          

		}



		private void treeGrid_RequestTreeItems(object sender, GridTreeRequestTreeItemsEventArgs args)

		{

		    //When ParentItem is null, you need to set args.ChildList to be the root items

		    if (args.ParentItem == null)

		    {

		        //Get the root list-get all employees who have no boss 

		        //Get all employees whose boss' id is -1 (no boss)

		        args.ChildList = employees.Where(x => x.ReportsTo == -1);

		    }

		    else //If ParentItem not null, then set args.ChildList to the child items for the given ParentItem.

		    {   //Get the children of the parent object

		        Employee emp = args.ParentItem as Employee;

		        if (emp != null)

		        {

		            //Get all employees that report to the parent employee

		            args.ChildList = employees.Where(x => x.ReportsTo == emp.ID);

		        }

		    }

		} 


   ~~~

When the application runs, the following output is generated.

![Show the output of WPF GridTreeControl](Getting-Started_images/Getting-Started_img19.png)

#### Samples

To view samples: 

1. Select Start > Programs > Syncfusion > Essential Studio xx.x.x.xx > Dashboard.
2. Click Run Samples for WPF under the User Interface Edition panel.
3. Select GridTreeControl.
4. Expand the Data Population Features item in the Sample Browser.
5. Select On-Demand Loading Demo to launch the sample.

### Binding a Self-Relational Collection to the GridTree Control

A self-relational collection is a collection of objects in which each object has a hierarchy within. Each object acts as a parent and hold its children in an attribute. Each child acts as the next-level parent and holds children in an attribute, and so on. In this example, both child and parent are of the same type (data type/object type). Specifying the child attribute name in ChildPropertyName of GridTreeControl automatically fetches the hierarchy and populate it.

1. Create a self-relational collection of objects to bind with the GridTree control. In this example, we have created a collection of objects containing employee information.

   ~~~ csharp

		 //This code is used to create a list collection of hierarchical data

		 public class EmployeeDetails : List<Employee>

		    {

		        public EmployeeDetails()

		        {        

		            //Management

					//The child list is the ChildCollection of the node

		            List<Employee> childList = new List<Employee>();

		            childList.Add(new Employee() { FirstName = "Andrew", LastName = "Fuller", Department = "Management", EmpID = 1001, ID = 9, Salary = 1200000, ReportsTo = 2, Title = "Vice President" });

		            childList.Add(new Employee() { FirstName = "Janet", LastName = "Leverling", Department = "Management", EmpID = 1002, ID = 10, Salary = 1000000, ReportsTo = 2, Title = "GM" });

		            childList.Add(new Employee() { FirstName = "Steven", LastName = "Buchanan", Department = "Management", EmpID = 1003, ID = 11, Salary = 900000, ReportsTo = 2, Title = "Manager" });

		            this.Add(new Employee() { Title = "Management", ReportsTo = 1, ID = 2, Child = childList });

		            //Accounts

		            childList = new List<Employee>();

		            childList.Add(new Employee() { FirstName = "Nancy", LastName = "Davolio", Department = "Accounts", EmpID = 1004, ID = 12, Salary = 850000, ReportsTo = 3, Title = "Accounts Manager" });

		            childList.Add(new Employee() { FirstName = "Margaret", LastName = "Peacock", Department = "Accounts", EmpID = 1008, ID = 13, Salary = 700000, ReportsTo = 3, Title = "Accountant" });

		            childList.Add(new Employee() { FirstName = "Michael", LastName = "Suyama", Department = "Accounts", EmpID = 1009, ID = 14, Salary = 700000, ReportsTo = 3, Title = "Accountant" });

		            childList.Add(new Employee() { FirstName = "Robert", LastName = "King", Department = "Accounts", EmpID = 1010, ID = 15, Salary = 650000, ReportsTo = 3, Title = "Accountant" });

		            this.Add(new Employee() { Title = "Accounts", ReportsTo = 1, ID = 3, Child=childList });
		        }

		    }

		    public class Employee

		    {
		        int id;

		        public int ID

		        {

		            get { return id; }

		            set { id = value; }

		        }

		        int? empId;

		        public int? EmpID

		        {

		            get { return empId; }

		            set { empId = value; }

		        }

		        string firstName;

		        public string FirstName

		        {

		            get { return firstName; }

		            set { firstName = value; }

		        }

		        string lastName;

		        public string LastName

		        {

		            get { return lastName; }

		            set { lastName = value; }

		        }

		        string department;

		        public string Department

		        {

		            get { return department; }

		            set { department = value; }

		        }

		        private string title;

		        public string Title

		        {

		            get { return title; }

		            set { title = value; }

		        }

		        double? salary;

		        public double? Salary

		        {

		            get { return salary; }

		            set { salary = value; }

		        }

		        int reportsTo;

		        public int ReportsTo

		        {

		            get { return reportsTo; }

		            set { reportsTo = value; }

		        }

		        public List<Employee> Child

		        {

		            get;

		            set;

		        } 

		    }

   ~~~
   
2. Bind ItemsSource of GridTreeControl and assign ChildPropertyName—these can be set in either XAML or code.

   ~~~ xaml

		<syncfusion:GridTreeControl  Name="treeGrid" 

								AutoPopulateColumns="True" 

								ExpandStateAtStartUp="AllNodesExpanded" 

								ChildPropertyName="Child" 

								ItemsSource="{Binding GTCSource}"/>

   ~~~

   ~~~ csharp

		public MainWindow()

		{

		   InitializeComponent();   

		   this.DataContext = this;

		   _gtcSource = new EmployeeDetails();

		}



		 //This property is set as ItemsSource of GridTreeControl

		private EmployeeDetails _gtcSource;

		public EmployeeDetails GTCSource

		{

		   get

		   {

		       return _gtcSource;

		   }

		   set

		   {

				_gtcSource = value;

		   }

		}

		Assigning Items’ Source Code 

		public MainWindow()

		{

		    InitializeComponent();    

			//ItemsSource set to GridTreeControl

		    this.treeGrid.ItemsSource = new EmployeeDetails();

		}

   ~~~

When the application runs, the following output is generated.

![Binding the collection of WPF GridTree control](Getting-Started_images/Getting-Started_img20.png)

#### Samples

To view samples: 

1. Select Start > Programs > Syncfusion > Essential Studio xx.x.x.xx > Dashboard.
2. Click Run Samples for WPF under User Interface Edition panel.
3. Select GridTreeControl.
4. Expand the Data Population Features item in the Sample Browser.
5. Select Self-Relational Data Binding Demo to launch the sample.

### Binding a Data View to the GridTree Control

The following steps explain how to bind a data view from a database to the GridTree control.

1. Connect a database to the current application. The database can be connected several ways, such as ADO.NET, LINQ to SQL, classes, and so on. In this example, a connection has been directly established to a simple northwind.sdf database.
2. Once the connection is established, fetch the required data table from the database. In this example, the data table has been fetched from the northwind.sdf by using SQL DataAdapter.

   N> Before using this procedure, check that System.data.SqlServerCe.dll has been added to your project.

   ~~~ csharp

		// Connect to a data table

		public DataTable GetDataTable()

		{

		   DataSet ds = new DataSet();            

		   if (!LayoutControl.IsInDesignMode)

		   {

		     using (SqlCeConnection con = new SqlCeConnection(connectionString))

		     {

		        con.Open();

		        SqlCeDataAdapter sda = new SqlCeDataAdapter("SELECT * FROM Employees", con);    

		         sda.Fill(ds, "Employee");

		     }  

			//The following line is used to create the hierarchical relations

		     ds.Relations.Add(new DataRelation("Employee_Relation", ds.Tables["Employee"].Columns["Employee ID"], ds.Tables["Employee"].Columns["Reports To"],false));

		   }

		   if (ds.Tables.Count > 0)

		     return ds.Tables[0];

		   else

		     return null;

		}

   ~~~
   
3. Now bind the data table as an ItemsSource of GridTreeControl in either XAML or code.

   ~~~ xaml

		<syncfusion:GridTreeControl Name="treeGrid" 

										AutoPopulateColumns="True"

			                            ItemsSource="{Binding GTCSource}" 

										ExpandStateAtStartUp="AllNodesExpanded" 

										ChildPropertyName="Employee_Relation" />

   ~~~

   ~~~ csharp

		public MainWindow()

		{

		   InitializeComponent();           

		   this.DataContext = this;

		   dataTable = GetDataTable();

		}



		DataTable dataTable;

		public DataView GTCSource

		{

		   get

		   {

		     if (dataTable == null)

		       return null;



		     DataView dataView = new DataView(dataTable);

			 //RowFilter is applied to form the hierarchy

		     dataView.RowFilter = "[Reports To] Is NULL";



		     return dataView;            

		   }

		}

		Assigning the Items’ Source in Code 

		public MainWindow()

		{

		    InitializeComponent();

			//Relation name set as ChildPropertyName

			this.treeGrid.ChildPropertyName = "Employee_Relation";

			dataTable = GetDataTable();    

			//ItemsSource set to GridTreeControl

		    this.treeGrid.ItemsSource = GTCSource;

		}

		DataTable dataTable;

		public DataView GTCSource

		{

		   get

		   {

		     if (dataTable == null)

		       return null;

		     DataView dataView = new DataView(dataTable);

		     dataView.RowFilter = "[Reports To] Is NULL";

		     return dataView;

		     }

		}

   ~~~
   
When the application runs, the following output is generated.

![Binding a data view to the WPF GridTree control](Getting-Started_images/Getting-Started_img21.png)

#### Sample

To view samples: 

1. Select Start > Programs > Syncfusion > Essential Studio xx.x.x.xx > Dashboard.
2. Click Run Samples for WPF under User Interface Edition panel.
3. Select GridTreeControl.
4. Expand the Data Population Features item in the Sample Browser.
5. Select Data View Binding Demo to launch the sample.