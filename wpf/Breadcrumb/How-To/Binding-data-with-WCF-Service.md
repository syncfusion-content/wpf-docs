---
layout: post
title: Binding data with WCF Service| Hierarchical Navigator | Wpf | Syncfusion
description: binding data with wcf service 
platform: wpf
control: Hierarchical Navigator
 documentation: ug
---

## Binding data with WCF Service 

XML data can be bound through WCF Services by using a WPF application enabled with WCF Services.

The steps to bind XML data with WCF Services are as follows:

1. Create the XML and class objects (for WCF, refer the XML data-binding class and the XML used in the Binding XML data section).
2. Add an ASP.NET Web application to the sample application, and then add a new WCF Service item to the Web application, to create a WCF Service application.
3. Create an Observable Collection from XML data to bind with ItemsSource, as shown below in the service class that has a return type of ObservableCollection.




   ~~~csharp

		[ServiceContract(Namespace = "")]

		[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]

		public class Service1

		{

		[OperationContract]

		public ObservableCollection<HierarchyItem> CreateXMLDataItems()

		{

		ObservableCollection<HierarchyItem> categories = new ObservableCollection<HierarchyItem>();

		XDocument XMLItemSource = XDocument.Load("YourXMLLocation/HierarchyItems.xml");

		categories = this.GetCategories(XMLItemSource.Element("categories"));

		return categories;

		}



		private ObservableCollection<HierarchyItem> GetCategories(XElement element)

		{

		var item = from category in element.Elements("category")

		select category;



		var itemsObservableCollection = new ObservableCollection<HierarchyItem>();



		foreach (var itm in item)

		{

		var subitm = new HierarchyItem();

		subitm.ContentStr = itm.Attribute("name").Value;

		subitm.HierarchyItems = this.GetCategories(itm);

		itemsObservableCollection.Add(subitm);

		}



		return itemsObservableCollection;

		}

		}

   ~~~

4. Connect WCF Services with the sample application, as shown in the following code snippet:
   
   ~~~ csharp			
			 namespace 
			 WCFServicesInHierarchy
			 {    public partial class MainPage : UserControl    
			 {        public MainPage()        
			 {            InitializeComponent();       
			 }   
			 }    
			 public class CustomSource   
			 {        public CustomSource()        
			 {            
			 //This loads WCF Service            
			 Service1Client client = new Service1Client();            
			 client.CreateXMLDataItemsCompleted += new EventHandler<CreateXMLDataItemsCompletedEventArgs>(client_CreateXMLDataItemsCompleted);         
			 client.CreateXMLDataItemsAsync();            
			 this.Categories = new ObservableCollection<HierarchyItem>();        
			 }      
			 private void client_CreateXMLDataItemsCompleted(object sender, CreateXMLDataItemsCompletedEventArgs e)        
			 {            if (e.Error == null && e.Result != null)           
			 {                foreach (HierarchyItem c in e.Result)              
			 {                    this.Categories.Add(c);              
			 }          
			 }       
			 }        
			 public ObservableCollection<HierarchyItem> Categories        
			 {            get;            set;        
			 }   
			 }}
			 
   ~~~
  
   ~~~xaml  
		
			
		   <Window<br>     
		   xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"     
		   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"<br>    
		   xmlns:syncfusion="http://schemas.syncfusion.com/wpf"<br>     
		   xmlns:local="clr-namespace:WCFServicesInHierarchy" <br>     
		   x:Class="WCFServicesInHierarchy.MainWindow"<br>x:Name="Window" 
		   Title="MainWindow" UseLayoutRounding="True" Width="640" Height="480"><br>   
		    <Window.DataContext><br>        <local:CustomSource/><br>  
		     </Window.DataContext><br><br>    <Grid x:Name="LayoutRoot"><br>        
		   <syncfusion:HierarchyNavigator Name="hierarchyNavigator1" VerticalAlignment="Center" ItemsSource="{Binding Categories}"><br>            
		   <syncfusion:HierarchyNavigator.ItemTemplate><br>               
		    <HierarchicalDataTemplate ItemsSource="{Binding HierarchyItems}"><br>          
		             <Border><br>                     
		      <TextBlock Text="{Binding ContentStr}" Margin="2,0"/><br>                 
		      </Border><br>                </HierarchicalDataTemplate><br>            
		   </syncfusion:HierarchyNavigator.ItemTemplate><br>      
		     </syncfusion:HierarchyNavigator><br>    
		   </Grid><br>
		   </Window>
		

   ~~~
