---
layout: post
title: Data binding | TabNavigation | WPF | Syncfusion
description: This section describes how to add tabnavigation items through items source in tab navigation control.
platform: WPF
control: TabNavigation
documentation: ug
---

# Data binding

Business object collections can be easily bound to the TabNavigation control using [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssourceproperty?view=netframework-4.7.2) property. The following types of collections can be bound:

* Observable Collection 
* ILIST binding 
* XML binding 

## Observable collection 

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

## ILIST binding

{% tabs %}
{% highlight XAML %}
<syncfusion:TabNavigationControl TransitionEffect="Slide" ItemsSource="{Binding MyCollection}"/>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C#  %}
namespace TabNavigationSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    { 
        public MainWindow()
        {
            InitializeComponent();
			TabNavigationItem temp;
			MyCollection = new List<TabNavigationItem>();
			for (int i = 0; i < 10; i++)
			{
				temp = new TabNavigationItem();
				temp.Header = i;
				temp.Content= "Item " + i.ToString();
				MyCollection.Add(temp);
			}
			DataContext = this;
		}
		public IList<TabNavigationItem> MyCollection
		{
			get { return (IList<TabNavigationItem>)GetValue(MyCollectionProperty); }
			set { SetValue(MyCollectionProperty, value); }
		}
		// Using a DependencyProperty as the backing store for MyCollection.  This enables animation, styling, binding and so on
		public static readonly DependencyProperty MyCollectionProperty =
		DependencyProperty.Register("MyCollection", typeof(IList<TabNavigationItem>), typeof(MainWindow), new PropertyMetadata(null));
	}
}
{% endhighlight %}
{% endtabs %}

![wpf tabnavigation control supports data binding](Data-binding_images/Adding-items-through-Items-Source_img1.png)

## XML binding 

To bind XML data to a TabNavigation control, convert the XML data to a collection like Observable collection or ILIST collection, and then bind the collection by using the ItemsSource property of the TabNavigation control.

{% tabs %}
{% highlight XML %}
<?xml version="1.0" encoding="utf-8" ?>
<categories>
  <category name="WPF Products" content="EssentialStudio WPF edition includes 8 comprehensive products with dozens of components that ease and speed up your development."/>
  <category name="TabNavigationControl" content="Tab Navigation is a new control for displaying the contents of the control with transition effects. "/>
  <category name="Rich Text Editor" content="An Editor control which allows all kind of Import/Export functionalities and complete formatting."/>
</categories>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight C# %}
namespace TabNavigationSample
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
			ObservableCollection<TabNavigationItems> categories = new ObservableCollection<TabNavigationItems>();
			XDocument XMLItemSource = XDocument.Load(@"assets/XMLFile1.xml");
			categories = this.GetCategories(XMLItemSource.Element("categories"));
			MyCollection = new ObservableCollection<TabNavigationItem>();
			for (int i=0;i<categories.Count;i++)
			{
				tab = new TabNavigationItem();
				tab.Header = categories[i].Name.ToString();
				tab.Content = categories[i].Content.ToString();
				MyCollection.Add(tab);
			}
			tabNavigation.ItemsSource = MyCollection;
		}
		//Convert XML data into ObservableCollection
		private ObservableCollection<TabNavigationItems> GetCategories(XElement xElement)
		{
			var item = from category in xElement.Elements("category")  select category;
			var itemsObservableCollection = new ObservableCollection<TabNavigationItems>();
			foreach (var itm in item)
			{
				var subitm = new TabNavigationItems();
				subitm.Name = itm.Attribute("name").Value;
				subitm.Content = itm.LastAttribute.Value;
				itemsObservableCollection.Add(subitm);
			}
			return itemsObservableCollection;
		}
		public class TabNavigationItems
		{
			public string Name { get; set; }
		}
		//For binding object
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

{% tabs %}
{% highlight XAML %}
<syncfusion:TabNavigationControl TransitionEffect="Slide"/>
{% endhighlight %}
{% endtabs %}
