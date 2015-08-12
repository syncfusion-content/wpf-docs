---
layout: post
title: Binding-data-with-WCF-Service
description: binding data with wcf service 
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Binding data with WCF Service 

XML data can be bound through WCF Services by using a WPF application enabled with WCF Services.

The steps to bind XML data with WCF Services are as follows:

1. Create the XML and class objects (for WCF, refer the XML data-binding class and the XML used in the Binding XML data section).
2. Add an ASP.NET Web application to the sample application, and then add a new WCF Service item to the Web application, to create a WCF Service application.
3. Create an Observable Collection from XML data to bind with ItemsSource, as shown below in the service class that has a return type of ObservableCollection.

   ~~~ cs

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
   {:.prettyprint }

4. Connect WCF Services with the sample application, as shown in the following code snippet:

   ~~~ cs
   
		namespace WCFServicesInHierarchy
		{    
			public partial class MainPage : UserControl
			{ 
				public MainPage()
				{
					InitializeComponent();
				}
			}
			public class CustomSource 
			{
				public CustomSource()
				{ 
					//This loads WCF Service
					Service1Client client = new Service1Client(); 
					client.CreateXMLDataItemsCompleted += new EventHandler<CreateXMLDataItemsCompletedEventArgs>(client_CreateXMLDataItemsCompleted); 
					client.CreateXMLDataItemsAsync();
					this.Categories = new ObservableCollection<HierarchyItem>();
				}   
				private void client_CreateXMLDataItemsCompleted(object sender, CreateXMLDataItemsCompletedEventArgs e)
				{      
					if (e.Error == null && e.Result != null) 
					{         
						foreach (HierarchyItem c in e.Result) 
						{             
							this.Categories.Add(c);    
						}  
					}
				}       
				public ObservableCollection<HierarchyItem> Categories 
				{      
					get;
					set;
				}  
			}
		}
		
   ~~~
   {:.prettyprint }
   
   ~~~ xml
   
		<Window
			 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
			 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" 
			 xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
			 xmlns:local="clr-namespace:WCFServicesInHierarchy" 
			 x:Class="WCFServicesInHierarchy.MainWindow"
			 x:Name="Window" Title="MainWindow" UseLayoutRounding="True" Width="640" Height="480">
			 <Window.DataContext> 
			        <local:CustomSource/> 
			    </Window.DataContext>  
			   <Grid x:Name="LayoutRoot">  
			       <syncfusion:HierarchyNavigator Name="hierarchyNavigator1" VerticalAlignment="Center" ItemsSource="{Binding Categories}"> 
			           <syncfusion:HierarchyNavigator.ItemTemplate>  
			               <HierarchicalDataTemplate ItemsSource="{Binding HierarchyItems}">
			                    <Border>
			                        <TextBlock Text="{Binding ContentStr}" Margin="2,0"/>     
			                </Border>    
			            </HierarchicalDataTemplate>    
			        </syncfusion:HierarchyNavigator.ItemTemplate> 
			       </syncfusion:HierarchyNavigator> 
			   </Grid>
		</Window>

   ~~~
   {:.prettyprint }
