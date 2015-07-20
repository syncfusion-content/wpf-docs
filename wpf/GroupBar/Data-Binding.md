---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: GroupBar
documentation: ug
---

# Data Binding

You can bind the custom object to the DataContext property of the GroupBar control and their corresponding elements can be binded with the children of the GroupBar control. When a DataContext is set to a window or to a GroupBar, it gets inherited to all its logical children. The OnInitialized method will get this DataContext value. As you use this DataContext in the template with DataTriggers, you need to set that property to active host tab or null.

Use the code snippet to apply a DataContext to the GroupBar control.



<table>
<tr>
<td>
[XAML]<Window x:Class="WpfApplication1.Window1"    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"    xmlns:local="clr-namespace:WpfApplication1"    Title="Window1" Height="300" Width="300">  &lt;Window.Resources&gt;    &lt;!--Custom object which is defined in the code behind can be accessed through the key logic in XAML--&gt;    &lt;local:GroupData x:Key="groupData" /&gt;  &lt;/Window.Resources&gt;  &lt;Grid Margin="30"&gt;    &lt;!-- Adding GroupBar --&gt;    <syncfusion:GroupBar Height="200" DataContext="{Binding groupData}"    VisualMode="Default" AllowCollapse="True" Width="230" Name="groupBar">      &lt;!-- Adding GroupBarItem --&gt;      &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="{Binding Header}"&gt;        &lt;!-- Adding content for GroupBar item using panel --&gt;        &lt;StackPanel Orientation="Vertical"&gt;          &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;          <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>          <RadioButton Margin="4,2,2,2">Vertical</RadioButton>          &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;          <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>          <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>        &lt;/StackPanel&gt;      &lt;/syncfusion:GroupBarItem&gt;      &lt;!-- Adding GroupBarItem --&gt;      &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;        &lt;!-- Adding content for GroupBar item using GroupView --&gt;        &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;          &lt;syncfusion:GroupViewItem Text="{Binding ListView}"/&gt;          &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;          &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;        &lt;/syncfusion:GroupView&gt;      &lt;/syncfusion:GroupBarItem&gt;    &lt;/syncfusion:GroupBar&gt;  &lt;/Grid&gt;&lt;/Window&gt;</td></tr>
<tr>
<td>
[C#]/// &lt;summary&gt;/// Interaction logic for the class GroupData/// &lt;/summary&gt;public class GroupData{    /// &lt;summary&gt;    /// Initializes a new instance of the &lt;see cref="GroupData"/&gt; class.    /// &lt;/summary&gt;    public GroupData()    {        this.Header = "GroupBarItem1";        this.ListView = "ListViewItem";    }    /// &lt;summary&gt;    /// Gets or sets the header.    /// &lt;/summary&gt;    /// <value>The header.&lt;/value&gt;    public string Header    {        get;        set;    }    /// &lt;summary&gt;    /// Gets or sets the list view.    /// &lt;/summary&gt;    /// <value>The list view.&lt;/value&gt;    public string ListView    {        get;        set;    }}</td></tr>
</table>
## Data-Binding to Objects

The GroupBar control also supports binding to objects. The following example demonstrates this.

1. Create a class that acts as a model for the GroupBar control.



[C#]

public class Model

    {

        public string Header { get; set; }

        public string Content { get; set; }

public bool IsSelected { get; set; }



    }



2. Create a ViewModel class and initialize the items as follows.



[C#]

   public class ViewModel

    {

        public ObservableCollection<Model> GroupItems { get; set; }

        public ViewModel()

        {

            GroupItems = new ObservableCollection<Model>();

            PopulateData();

        }

        private void PopulateData()

        {

            Model model1 = new Model() { Header = "Item1", Content = "GroupBarItem1", IsSelected = true };

            Model model2 = new Model() { Header = "Item2", Content = "GroupBarItem2" };

            Model model3 = new Model() { Header = "Item3", Content = "GroupBarItem3" };

            Model model4 = new Model() { Header = "Item4", Content = "GroupBarItem4" };

            GroupItems.Add(model1);

            GroupItems.Add(model2);

            GroupItems.Add(model3);

            GroupItems.Add(model4);



        }

    }





3. Create a ViewModel instance and use it as DataContext for the root window.



[XAML]

&lt;Window.DataContext&gt;

   &lt;local:ViewModel/&gt;

&lt;/Window.DataContext&gt;





4. Now configure the ItemsSource and ItemContainerStyle of GroupBar.



[XAML]

    &lt;syncfusion:GroupBar Name="groupBar1" ItemsSource="{Binding GroupItems}" VisualMode="StackMode"&gt;

            &lt;syncfusion:GroupBar.ItemContainerStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:GroupBarItem}"&gt;

                    &lt;Setter Property="HeaderText" Value="{Binding Header}"/&gt;

                    &lt;Setter Property="Content" Value="{Binding Content}"/&gt;

                    &lt;Setter Property="IsSelected" Value="{Binding IsSelected}" /&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:GroupBar.ItemContainerStyle&gt;        

        &lt;/syncfusion:GroupBar&gt;





This creates the following GroupBar control. 



{ ![](Data-Binding_images/Data-Binding_img1.png) | markdownify }
{:.image }


## Data-Binding with XML

An XML file can also be used as the ItemsSource for the GroupBar control. The following example illustrates this.

1. Create an XML file with the following information and name it Data.xml.



[XML]

&lt;?xml version="1.0" encoding="utf-8" ?&gt;

&lt;Books&gt;



  &lt;Book Name="Programming C# 4.0" Description="Learn C# fundamentals, such as variables, flow control, loops, and methods" ImagePath="programming-c-sharp-four.png"/&gt;

  &lt;Book Name="Programming WPF" Description="A tutorial on XAML, the new HTML-like markup language for declaring Windows UI" ImagePath="programming-wpf.png"/&gt;

  &lt;Book Name="Essential WPF" Description="Visuals and media, including 2D, 3D, video, and animation" ImagePath="essential_wpf.png"/&gt;

  &lt;Book Name="WPF Unleashed" Description="Examines the WPF feature areas in incredible depth: controls, layout, resources, data binding, styling, graphics, animation, and more" ImagePath="wpf-unleashed.png"/&gt;



&lt;/Books&gt;





2. Add the XmlDataProvider for the XML document.



[XAML]

&lt;XmlDataProvider Source="Data.xml" x:Key="xmlSource" XPath="Books"/&gt; 





3. ItemsSource property for the GroupBar control.



[XAML]

<syncfusion:GroupBar Name="groupBar1" Margin="20" ItemsSource="{Binding Source={StaticResource xmlSource}, XPath=Book}" VisualMode="MultipleExpansion"  

  >

            &lt;syncfusion:GroupBar.ItemContainerStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:GroupBarItem}"&gt;

                     &lt;Setter Property="HeaderTemplate"&gt;

                        &lt;Setter.Value&gt;

                            &lt;DataTemplate&gt;

                                &lt;Grid&gt;

                                    &lt;TextBlock Text="{Binding XPath=@Name}" /&gt;

                                &lt;/Grid&gt;

                            &lt;/DataTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;

                    &lt;Setter Property="ContentTemplate"&gt;

                        &lt;Setter.Value&gt;

                            &lt;DataTemplate&gt;

                                &lt;Grid&gt;

                                    &lt;Grid.ColumnDefinitions&gt;

                                        &lt;ColumnDefinition Width="4*"/&gt;

                                        &lt;ColumnDefinition Width="6*"/&gt;

                                    &lt;/Grid.ColumnDefinitions&gt;

                                    &lt;Image Source="{Binding XPath=@ImagePath}"/&gt;

                                    &lt;TextBlock Text="{Binding XPath=@Description}" TextWrapping="Wrap" Grid.Column="1"/&gt;

                                &lt;/Grid&gt;                               

                            &lt;/DataTemplate&gt;

                        &lt;/Setter.Value&gt;

                    &lt;/Setter&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:GroupBar.ItemContainerStyle&gt;        

        &lt;/syncfusion:GroupBar&gt;





This will create the following GroupBar control.



{ ![](Data-Binding_images/Data-Binding_img2.png) | markdownify }
{:.image }


