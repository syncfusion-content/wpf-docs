---
layout: post
title: Data binding in WPF Tab Navigation control | Syncfusion
description: Learn about Data binding support in Syncfusion Essential Studio WPF Tab Navigation control, its elements and more.
platform: WPF
control: TabNavigation
documentation: ug
---

# Data binding in WPF Tab Navigation

Business object collections can be easily bound to the TabNavigation control using [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssourceproperty?view=netframework-4.7.2) property. 

## Binding IEnumerable

{% tabs %}
{% highlight XAML %}
<syncfusion:TabNavigationControl TransitionEffect="Slide" ItemsSource="{Binding MyCollection}"/>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}
namespace TabNavigationSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    { 
		TabNavigationItem temp;
        public MainWindow()
        {
            InitializeComponent();
			MyCollection = new ObservableCollection<TabNavigationItem>();
			for (int i = 0; i < 10; i++)
			{
				temp = new TabNavigationItem();
				temp.Header = i;
				temp.Content= "Item " + i.ToString();
				MyCollection.Add(temp);
			}
			this.DataContext = this;
		}
		public ObservableCollection<TabNavigationItem> MyCollection 
		{
			get { return (ObservableCollection<TabNavigationItem>)GetValue(MyCollectionProperty); }
			set { SetValue(MyCollectionProperty, value); }
	    }
		// Using a DependencyProperty as the backing store for MyCollection.  This enables animation, styling, binding and so on
		public static readonly DependencyProperty MyCollectionProperty = DependencyProperty.Register("MyCollection", typeof(ObservableCollection<TabNavigationItem>), typeof(MainWindow), new PropertyMetadata(null));
	}
}
{% endhighlight %}
{% endtabs %}

![wpf tabnavigation control supports data binding](Data-binding_images/Adding-items-through-Items-Source_img1.png)

## Binding data from XML

To bind XML data to a TabNavigation control, convert the XML data to a collection like Observable collection or ILIST collection, and then bind the collection by using the ItemsSource property of the TabNavigation control.


* **Create a xml file**


{% tabs %}
{% highlight XML %}
<?xml version="1.0" encoding="utf-8" ?>
<Books>
  <book>
    <title>XML Developer's Guide</title>
    <description>An indent look at creating applications with XML.</description>
  </book>
  <book>
    <title>Midnight Rain</title>
    <description>A former architect battles corporate zombies, an evil sorceress, and her own childhood to become queen of the world.</description>
  </book>
  <book>
    <title>Oberon's Legacy</title>
    <description>In post apocalypse England, the mysterious agent known only as Oberon helps to create a new life for the inhabitants of London. Sequel to Mae Ascendant.</description>
  </book>
  <book>
    <title>Lover Birds</title>
    <description>When Carla meets Paul at an ornithology conference, tempers fly as feathers get ruffled.</description>
  </book>
  <book>
    <title>Split Splash</title>
    <description>A deep sea diver finds true love twenty thousand leagues beneath the sea.</description>
  </book>
</Books>
{% endhighlight %}
{% endtabs %}

* **Model.cs**

{% tabs %}
{% highlight C# %}
namespace TabNavigationXMLBinding
{
	public class Model : NotificationObject
	{
		public Model()
		{

		}
	}
	public class BookModel : NotificationObject
	{
		public BookModel()
		{

		}

		private string bookName;
		public string BookName
		{
			get
			{
				return bookName;
			}
			set
			{
				bookName = value;
				this.RaisePropertyChanged("BookName");
			}
		}

		private string description;
		public string Description
		{
			get
			{
				return description;
			}
			set
			{
				description = value;
				this.RaisePropertyChanged("Description");
			}
		}
	}
}
{% endhighlight %}
{% endtabs %}

* **ViewModel.cs**

{% tabs %}
{% highlight C# %}
namespace TabNavigationXMLBinding
{
	public class ViewModel : NotificationObject
	{

		private ObservableCollection<Model> modelItems;
		public ObservableCollection<Model> ModelItems
		{
			get
			{
				return modelItems;
			}

			set
			{
				modelItems = value;
			}
		}
		private ObservableCollection<BookModel> bookModelItems;
		public ObservableCollection<BookModel> BookModelItems
		{
			get
			{
				return bookModelItems;
			}

			set
			{
				bookModelItems = value;
			}
		}
		public  ViewModel()
		{
			modelItems = new ObservableCollection<Model>();
			bookModelItems = new ObservableCollection<BookModel>();
			XDocument xDocument = XDocument.Load(@"assets\Books.xml");
			IEnumerable<XElement> query = from xElement in xDocument.Descendants("book")
										  select xElement;
			foreach (XElement xElement in query)
			{
				BookModel bookModel = new BookModel
				{
					BookName = xElement.Element("title").Value,
					Description = xElement.Element("description").Value
				};
				bookModelItems.Add(bookModel);
			}
		}
	}
}
{% endhighlight %}
{% endtabs %}

* **MainWindow.Xaml.cs**

{% tabs %}
{% highlight C# %}
namespace TabNavigationXMLBinding
{
	/// <summary>
	/// Interaction logic for MainWindow.xaml
	/// </summary>
	public partial class MainWindow : ChromelessWindow
	{
		public MainWindow()
		{
			InitializeComponent();
			TabNavigationItem tab;
			ViewModel view = new ViewModel();
			BookCollection = new ObservableCollection<TabNavigationItem>();
			for (int i = 0; i < view.BookModelItems.Count; i++)
			{
				tab = new TabNavigationItem();
				tab.Header = view.BookModelItems[i].BookName;
				tab.Content = view.BookModelItems[i].Description;
				BookCollection.Add(tab);
			}
			this.DataContext = this;
		}

		public ObservableCollection<TabNavigationItem> BookCollection
		{
			get { return (ObservableCollection<TabNavigationItem>)GetValue(BookCollectionProperty); }
			set
			{
				SetValue(BookCollectionProperty, value);
			}
		}
		// Using a DependencyProperty as the backing store for MyCollection.  This enables animation, styling, binding and so on
		public static readonly DependencyProperty BookCollectionProperty =
		DependencyProperty.Register("BookCollection", typeof(ObservableCollection<TabNavigationItem>), typeof(MainWindow), new PropertyMetadata(null));
	}	
}
{% endhighlight %}
{% endtabs %}

* **MainWindow.Xaml**

{% tabs %}
{% highlight XAML %}
<Window.DataContext>
	<local:ViewModel/>
</Window.DataContext>

<!--TabNavigationControl-->
<syncfusion:TabNavigationControl x:Name="TabNavigation" Grid.Column="1" Grid.Row="1"  ItemsSource="{Binding BookCollection}"/>
{% endhighlight %}
{% endtabs %}
