---
layout: post
title: Edit Mode in WPF Breadcrumb control | Syncfusion
description: Learn here all about Edit Mode support in Syncfusion WPF Breadcrumb (HierarchyNavigator) control and more.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Edit Mode in WPF Breadcrumb (HierarchyNavigator)

This feature allows you to easily edit a navigation path by setting the [IsEnableEditMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.HierarchyNavigator.html#Syncfusion_Windows_Tools_Controls_HierarchyNavigator_IsEnableEditMode) property to `true`. The filter support is available in edit mode, which suggests matching nodes based on the path entered in the editor like the Windows Explorer.

To start the edit mode, click `HierarchyNavigatorItemsControl` and enter a navigation path that will display a drop-down list of filtered navigation paths, and then select the expected navigation path.

N> If you enter an incorrect path or text in the editor, the dropdown suggestion list will be closed.

{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
		xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
		x:Class="HierarchicalNavigatorSample.MainWindow"
		Title="HierarchicalNavigator Sample" Height="350" Width="525">
	<Grid>
		<!--Adding HierarchicalNavigator control -->
		<syncfusion:HierarchicalNavigator x:Name="hierarchicalNavigator" Width="100" Height="100" IsEnableEditMode="true" VerticalAlignment="Center" HorizontalAlignment="Center"/>
	</Grid>
</Window>

{% endhighlight %}
{% highlight C# %}

using Syncfusion.Windows.Tools;
namespace HierarchicalNavigatorSample
{
	/// <summary>
	/// Interaction logic for MainWindow.xaml
	/// </summary>
	public partial class MainWindow : Window
	{
		public MainWindow()
		{
			InitializeComponent();
			//Creating an instance of HierarchicalNavigator control
			HierarchicalNavigator hierarchicalNavigator = new HierarchicalNavigator();
			hierarchyNavigator.IsEnableEditMode = true;
			
			//Adding HierarchicalNavigator as window content
			this.Content = hierarchicalNavigator;
		}
	}
}

{% endhighlight %}
{% endtabs %}

![Hierarchy Naviagtor with AutoComplete](Edit-Mode_images/AutoComplete_image.png)


## Edit Hierarchy Naviagtor with SearchMemberPath

The [SearchMemberPath] (https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.HierarchyNavigator.html#Syncfusion_Windows_Tools_Controls_HierarchyNavigator_SearchMemberPath) property allows to easily edit when Hierarchical naviagtor item has multiple path and heirarchical data template.The path given in hierarchical data template should be given to the search member path if edit mode is enabled.

The steps to edit Hierarchical naviagtor items in XAML are as follows: 

1. Create a [HierarchyNavigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.HierarchyNavigator.html) control.And bind the path in hierarchical data template 

{% tabs %}
{% highlight XAML %}

<syncfusion:HierarchyNavigator SearchMemberPath="CountryName" ItemsSource="{Binding CloudDirectories}"  Grid.ColumnSpan="3" Grid.Row="1" x:Name="hierarchicalNavigator" IsEnableEditMode="true" VerticalAlignment="Center" HorizontalAlignment="Stretch">
    <syncfusion:HierarchyNavigator.ItemTemplate>
        <HierarchicalDataTemplate  ItemsSource="{Binding SubCollections[Directories]}">
            <TextBlock Text="{Binding Vals[CountryName]}" Margin="2,0" />
        </HierarchicalDataTemplate>
    </syncfusion:HierarchyNavigator.ItemTemplate>
</syncfusion:HierarchyNavigator>

{% endhighlight %}
{% endtabs %}

2.Create a model class for Key row and added keys to the dictionary.And create a ViewModel class for KeyPairs and added the KeyRow values to the Key Table

{% endhighlight %}
{% highlight C# %}

public class KeyTable : ObservableCollection<KeyRow>
    {
        
    }
public class KeyRow
    {

        private void OnPropertyChanged([CallerMemberName] string name = "")
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(name));
        }
        public event PropertyChangedEventHandler PropertyChanged;


        private Dictionary<string, KeyTable> keyValuePairs = new Dictionary<string, KeyTable>();

        public Dictionary<string, KeyTable> SubCollections
        {
            get { return keyValuePairs; }
            set { keyValuePairs = value; OnPropertyChanged(); }
        }



        private Dictionary<string, string> values = new Dictionary<string, string>();
        public Dictionary<string, string> Country { get { return values; } set { values = value; OnPropertyChanged(); } }

        public string this[string key]
        {
            get
            {

                values.TryGetValue(key, out string value);
                return value;
            }
            set
            {

                if (Country.ContainsKey(key))
                {
                    Country[key] = value;
                }
                else
                {
                    Country.Add(key, value);
                }
                OnPropertyChanged("Item[" + key + "]");
                OnPropertyChanged("Country");
            }
        }

    }


public class ViewModel
    {

        private KeyTable cloudDirectories;
        public KeyTable CloudDirectories
        {
            get { return cloudDirectories; }
            set { cloudDirectories = value; OnPropertyChanged(); }
        }

        private void OnPropertyChanged([CallerMemberName] string name = "")
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(name));
        }
        public event PropertyChangedEventHandler PropertyChanged;

        public ViewModel()
        {
            CloudDirectories = new KeyTable();

            var topLevel = new KeyRow();
            topLevel["CountryName"] = "Asia";
            topLevel.SubCollections.Add("Directories", new KeyTable());
            CloudDirectories.Add(topLevel);

            var provider = new KeyRow();     
            provider["CountryName"] = "India";
            provider.SubCollections.Add("Directories", new KeyTable());
            topLevel.SubCollections["Directories"].Add(provider);

            var folder1 = new KeyRow();
            folder1["CountryName"] = "TamilNadu";
          
            folder1.SubCollections.Add("Directories", new KeyTable());
            provider.SubCollections["Directories"].Add(folder1);

            var folder2 = new KeyRow();
            folder2["CountryName"] = "Andra";

            folder2.SubCollections.Add("Directories", new KeyTable());
            provider.SubCollections["Directories"].Add(folder2);

        }
    }



{% endhighlight %}
{% endtabs %}

N> [View sample in GitHub]()
