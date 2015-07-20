---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: MenuAdv
documentation: ug
---

# Data Binding

The topics under this section explain the data binding support for the MenuAdv control.

## Data-Binding to Objects

The MenuAdv control also supports binding to objects. The following example shows this.

1. Create a class that act as a model for MenuAdv.

[C#]

public class Model

    {

        public Model()

        {

            SubItems = new ObservableCollection<Model>();

        }



        public string Header { get; set; }



        public ObservableCollection<Model> SubItems { get; set; }



    }







2. Create a ViewModel class and initialize the items.

[C#]

  public class ViewModel

    {

        public ViewModel()

        {

            MenuItems = new ObservableCollection<Model>();

            PopulateData();

        }



        public ObservableCollection<Model> MenuItems { get; set; }



        private void PopulateData()

        {

            Model product = new Model() { Header = "Products" };

            PopulateSubSubItems(product);

            MenuItems.Add(product);            

        }



        private void PopulateSubSubItems(Model product)

        {

            Model bi = new Model() { Header = "Business Intelligence" };



            Model ui = new Model() { Header = "User Interface" };



            Model wpf = new Model() { Header = "WPF" };



            Model tools = new Model() { Header = "Tools" };

            Model chart = new Model() { Header = "Chart" };

            Model grid = new Model() { Header = "Grid" };

            Model diagram = new Model() { Header = "Diagram" };

            Model gauge = new Model() { Header = "Gauge" };

            Model schedule = new Model() { Header = "Schedule" };

            Model edit = new Model() { Header = "Edit" };



            wpf.SubItems.Add(tools);

            wpf.SubItems.Add(chart);

            wpf.SubItems.Add(grid);

            wpf.SubItems.Add(diagram);

            wpf.SubItems.Add(gauge);

            wpf.SubItems.Add(schedule);

            wpf.SubItems.Add(edit);



            Model sl = new Model() { Header = "Silverlight" };

            ui.SubItems.Add(wpf);

            ui.SubItems.Add(sl);



            Model reporting = new Model() { Header = "Reporting" };

            product.SubItems.Add(bi);

            product.SubItems.Add(ui);

            product.SubItems.Add(reporting);



        }

    }







3. Create a ViewModel instance and use it as DataContext for the root window.

[XAML]

&lt;Window.DataContext&gt;

   &lt;local:ViewModel/&gt;

&lt;/Window.DataContext&gt;



4. Now configure the ItemsSource and ItemTemplate of MenuAdv.

[XAML]

&lt;syncfusion:MenuAdv ItemsSource="{Binding MenuItems}"&gt;



            &lt;syncfusion:MenuAdv.ItemTemplate&gt;



                &lt;HierarchicalDataTemplate ItemsSource="{Binding SubItems}"&gt;

                    &lt;TextBlock Text="{Binding Header}" /&gt;

                &lt;/HierarchicalDataTemplate&gt;



            &lt;/syncfusion:MenuAdv.ItemTemplate&gt;



        &lt;/syncfusion:MenuAdv&gt;





Implementing the above code will generate the following control.

{ ![](Data-Binding_images/Data-Binding_img1.png) | markdownify }
{:.image }


## Data-Biding with XML

An XML file can also be used as _ItemsSource_ for the MenuAdv control. The following example illustrates this.

1. Create an XML file with the following details as follows and name it as Data.xml.

[XML]

&lt;Categories&gt;



  &lt;Root Name="Products" &gt;



    &lt;SubItem Name="User Interface" &gt;

      &lt;SubItem Name="ASP .NET"/&gt;

      &lt;SubItem Name="ASP .NET MVC"/&gt;

      &lt;SubItem Name="WPF"&gt;

        &lt;SubItem Name="Tools"/&gt;

        &lt;SubItem Name="Chart"/&gt;

        &lt;SubItem Name="Grid"/&gt;

        &lt;SubItem Name="Diagram"/&gt;

        &lt;SubItem Name="Gauge"/&gt;

        &lt;SubItem Name="Schedule"/&gt;

        &lt;SubItem Name="Edit"/&gt;

      &lt;/SubItem&gt;



      &lt;SubItem Name="Silverlight"/&gt;

      &lt;SubItem Name="Mobile MVC"/&gt;

      &lt;SubItem Name="Windows Phone"/&gt;

      &lt;SubItem Name="Windows Forms"/&gt;

    &lt;/SubItem&gt;



    &lt;SubItem Name="Business Intelligence"&gt;

      &lt;SubItem Name="WPF"/&gt;

      &lt;SubItem Name="ASP.NET"/&gt;

      &lt;SubItem Name="ASP.NET MVC"/&gt;

      &lt;SubItem Name="Silverlight"/&gt;

    &lt;/SubItem&gt;



    &lt;SubItem Name="Reporting"&gt;

      &lt;SubItem Name="WPF"/&gt;

      &lt;SubItem Name="Windows Forms"/&gt;

    &lt;/SubItem&gt;   



  &lt;/Root&gt;



&lt;/Categories&gt;



2. Add XmlDataProvider for the above XML document.

[XAML]

&lt;XmlDataProvider Source="Data.xml" x:Key="xmlSource" XPath="Categories"/&gt; 





3. Set ItemsSource property for the MenuAdv.

[XAML]

  &lt;syncfusion:MenuAdv	ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Root}" &gt;



       &lt;syncfusion:MenuAdv.ItemTemplate&gt;



            &lt;HierarchicalDataTemplate ItemsSource="{Binding 			XPath=SubItem}"&gt;



                    &lt;TextBlock Text="{Binding XPath=@Name}" /&gt;



                &lt;/HierarchicalDataTemplate&gt;



            &lt;/syncfusion:MenuAdv.ItemTemplate&gt;



        &lt;/syncfusion:MenuAdv&gt;







This will create the following MenuAdv control.

{ ![](Data-Binding_images/Data-Binding_img2.png) | markdownify }
{:.image }


