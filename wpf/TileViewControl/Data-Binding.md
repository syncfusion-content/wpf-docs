---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: TileView Control
documentation: ug
---

# Data Binding

The topics under this section explain the data binding support for the TileViewControl.

## Data-Binding to Objects

The TileViewControl supports binding to objects. The following code example illustrates this.

1. Create a class that act as a model for TileViewItem.



[C#]

public class Model

    {

        public string Header { get; set; }

        public string Content { get; set; }

    }



1. Create a ViewModel class and initialize the items as follows:



[C#]

public class ViewModel

    {

        public ObservableCollection<Model> TileItems { get; set; }

        public ViewModel()

        {

            TileItems = new ObservableCollection<Model>();

            PopulateData();

        }

        private void PopulateData()

        {

            Model model1 = new Model() { Header = "Item1", Content = "TileViewItem1" };

            Model model2 = new Model() { Header = "Item2", Content = "TileViewItem2" };

            Model model3 = new Model() { Header = "Item3", Content = "TileViewItem3" };

            Model model4 = new Model() { Header = "Item4", Content = "TileViewItem4" };           

            TileItems.Add(model1);

            TileItems.Add(model2);

            TileItems.Add(model3);

            TileItems.Add(model4);



        }

    }





2. Create a _ViewModel_ instance and use it as _DataContext_ for the root window.



[XAML]

&lt;Window.DataContext&gt;

   &lt;local:ViewModel/&gt;

&lt;/Window.DataContext&gt;



3. Configure the _ItemsSource_ and _ItemContainerStyle_ of the TileViewControl.



[XAML]

  &lt;syncfusion:TileViewControl ItemsSource="{Binding TileItems}" &gt;

            &lt;syncfusion:TileViewControl.ItemContainerStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:TileViewItem}"&gt;

                    &lt;Setter Property="Header" Value="{Binding Header}" /&gt;

                    &lt;Setter Property="Content" Value="{Binding Content}"/&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:TileViewControl.ItemContainerStyle&gt;

        &lt;/syncfusion:TileViewControl&gt;





This creates the following TileViewControl.



{ ![](Data-Binding_images/Data-Binding_img1.png) | markdownify }
{:.image }




## Data-Binding with XML

An XML file can also be used as _ItemsSource_ for the TileViewControl. The following example illustrates this.

1. Create an XML file with the following details and name it as Data.xml.



[XML]

&lt;?xml version="1.0" encoding="utf-8" ?&gt;

&lt;Books&gt;



  &lt;Book Name="Programming C# 4.0" Description="Learn C# fundamentals, such as variables, flow control, loops, and methods"/&gt;

  &lt;Book Name="Programming WPF" Description="A tutorial on XAML, the new HTML-like markup language for declaring Windows UI"/&gt;

  &lt;Book Name="Essential WPF" Description="Visuals and media, including 2D, 3D, video, and animation"/&gt;

  &lt;Book Name="WPF Unleashed" Description="Examines the WPF feature areas in incredible depth: controls, layout, resources, data binding, styling, graphics, animation, and more"/&gt;





&lt;/Books&gt;







2. Add _XmlDataProvider_ for the above XML document.



[XAML]

&lt;XmlDataProvider Source="Data.xml" x:Key="xmlSource" XPath="Books"/&gt; 





3. Set _ItemsSource_ property for the TileViewControl as follows.



[XAML]

&lt;syncfusion:TileViewControl ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}"   &gt;

            &lt;syncfusion:TileViewControl.ItemContainerStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:TileViewItem}"&gt;

                    &lt;Setter Property="Header" Value="{Binding XPath=@Name}" /&gt;

                    &lt;Setter Property="ContentTemplate"&gt;

                        &lt;Setter.Value&gt;

                            &lt;DataTemplate&gt;

                                &lt;TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap"/&gt;

                            &lt;/DataTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;                    

                &lt;/Style&gt;

            &lt;/syncfusion:TileViewControl.ItemContainerStyle&gt;

&lt;/syncfusion:TileViewControl&gt;





This will create the following TileViewControl.



{ ![](Data-Binding_images/Data-Binding_img2.png) | markdownify }
{:.image }




