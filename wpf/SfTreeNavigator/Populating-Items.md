---
layout: post
title: Populating-Items
description: populating items 
platform: wpf
control: Tree Navigator 
documentation: ug
---

# Populating Items 

## Items Source 

Tree Navigator items can be populated with the business object collection. Let us create a Tree Navigator which will show the list of Syncfusion Enterprise Toolkit products.  

Create a Model class with the necessary properties. 


{% highlight  %}
[C#]

  public class TreeModel : NotificationObject

    {

        public TreeModel()

        {

            Models = new ObservableCollection<TreeModel>();

        }



        private string header;

        public string Header

        {

            get { return header; }

            set

            {

                header = value;

                RaisePropertyChanged("Header");

            }

        }



        private ObservableCollection<TreeModel> models;

        public ObservableCollection<TreeModel> Models

        {

            get { return models; }

            set { models = value; }

        }



    }
{% endhighlight %}


> _Note: NotificationObject is a class which implements INotifyPropertyChanged interface._



Create a View Model class with the hierarchical items as follows.  


{% highlight  %}
[C#]

public class TreeViewModel 

    {

        private List<TreeModel> models;



        public List<TreeModel> Models

        {

            get { return models; }

            set { models = value; }

        }



        public TreeViewModel()

        {

            Models = new List<TreeModel>();



            TreeModel winrt = new TreeModel() {Header = "WinRT (XAML)"};

            TreeModel metroStudio = new TreeModel() {Header = "Metro Studio"};



            TreeModel winrt_chart = new TreeModel() {Header = "Chart"};

            TreeModel winrt_tools = new TreeModel() {Header = "Tools"};



            winrt.Models.Add(winrt_chart);

            winrt.Models.Add(winrt_tools);



            Models.Add(winrt);

            Models.Add(metroStudio);

        }

    }
{% endhighlight %}




 Bind the Models collection to the ItemsSource property of the Tree Navigator control as follows. 


{% highlight xml %}
[XAML]

<navigation:SfTreeNavigator ItemsSource="{Binding Models}"  

                            Header="Enterprise Toolkit"

                            Width="300" Height="400"

                            HorizontalAlignment="Center"

                            VerticalAlignment="Center" />


{% endhighlight %}


 This will populate the Tree Navigator as shown below. 



![](Populating-Items_images/Populating-Items_img1.png)





## Item Template 

ItemTemplate property of the Tree Navigator can be used to customize the display of business objects. 


{% highlight xml %}
[XAML]

<navigation:SfTreeNavigator ItemsSource="{Binding Models}"  

                                    Header="Enterprise Toolkit"

                                    Width="300" Height="400"

                                    HorizontalAlignment="Center"

                                    VerticalAlignment="Center"

                                    >

        <navigation:SfTreeNavigator.ItemTemplate>

            <primitives:HierarchicalDataTemplate ItemsSource="{Binding Models}">

                <DataTemplate>

                    <StackPanel Orientation="Horizontal">

                        <TextBlock Text="{Binding Header}" 

                                   Foreground="Green" FontWeight="Bold" 

VerticalAlignment="Center" Margin="18 0 0 0"/>

                    </StackPanel>

                </DataTemplate>

                </primitives:HierarchicalDataTemplate>

        </navigation:SfTreeNavigator.ItemTemplate>

 </navigation:SfTreeNavigator>
{% endhighlight %}




This will populate the Tree Navigator as follows.



![3](Populating-Items_images/Populating-Items_img2.png)





> _Note: HierarchicalDataTemplate available in Syncfusion.SfShared.WPF dll under the Syncfusion.Windows.Primitives namespace_



