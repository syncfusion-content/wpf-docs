---
layout: post
title: Getting Started | PinnableListBox | WPF | Syncfusion
description: A quick tour to initial users on Syncfusion PinnableListBox control for WPF
platform: WPF
control: PinnableListBox
documentation: ug
---

# Getting Started

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#pinnablelistbox) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Create a simple application with PinnableListBox

You can create a WPF application with the PinnableListBox control using the following steps:

## Create a project

Create a new WPF project in Visual Studio to display the PinnableListBox with functionalities.

## Add control through designer

The PinnableListBox control can be added to an application by dragging it from the toolbox to a designer view. The **Syncfusion.Shared.WPF** assembly reference will be added automatically to the project.

![wpf pinnable list box control added by designer](Getting-Started-images/wpf-pinnable-list-box-control-added-by-designer.png)

## Add control manually in XAML

To add the control manually in XAML, follow the given steps:

1. Add the **Syncfusion.Shared.WPF** assembly reference to the project.
2. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3. Declare the PinnableListBox control in the XAML page.

{% tabs %}
{% highlight XAML %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="PinnableListBoxSample.MainWindow"
        Title="PinnableListBox Sample" Height="350" Width="525">
    <Grid>
        <!-- Adding PinnableListBox control -->
        <syncfusion:PinnableListBox x:Name="pinnableListBox" HorizontalAlignment="Center" VerticalAlignment="Center" Width="100"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

## Add control manually in C\#

To add the control manually in C#, follow the given steps:

1. Add the **Syncfusion.Shared.WPF** assembly reference to the project. 
2. Import the PinnableListBox namespace **using Syncfusion.Windows.Shared;**.
3. Create a PinnableListBox instance, and add it to the window.

{% tabs %}
{% highlight C# %}
using Syncfusion.Windows.Shared;
namespace PinnableListBoxSample
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            //Creating an instance of PinnableListBox control
            PinnableListBox pinnableListBox = new PinnableListBox();
            //Adding PinnableListBox as window content
            this.Content = pinnableListBox;
        } 
    }
}
{% endhighlight %}
{% endtabs %}

## Add items using PinnableListBoxItem

You can add the items inside the PinnableListBox control using [PinnableListBoxItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.PinnableListBoxItem.html).

{% tabs %}
{% highlight XAML %}
<syncfusion:PinnableListBox x:Name="pinnableListBox" Height="200" Width="200">
  <syncfusion:PinnableListBoxItem Content="PivotGrid"/>
  <syncfusion:PinnableListBoxItem Content="DoubleTextBox"/>
  <syncfusion:PinnableListBoxItem Content="UpDown"/>
  <syncfusion:PinnableListBoxItem Content="MaskedTextBox"/>
  <syncfusion:PinnableListBoxItem Content="AutoComplete"/>
</syncfusion:PinnableListBox>
{% endhighlight %}
{% highlight C# %}
pinnableListBox.Items.Add(new PinnableListBoxItem() { Content = "PivotGrid" });
pinnableListBox.Items.Add(new PinnableListBoxItem() { Content = "DoubleTextBox" });
pinnableListBox.Items.Add(new PinnableListBoxItem() { Content = "UpDown" });
pinnableListBox.Items.Add(new PinnableListBoxItem() { Content = "MaskedTextBox" });
pinnableListBox.Items.Add(new PinnableListBoxItem() { Content = "AutoComplete" });
{% endhighlight %}
{% endtabs %}

## Bind data

You can populate the PinnableListBox control using the [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssourceproperty?view=netframework-4.7.2) property. 

* **Model.cs**

{% tabs %}
{% highlight C# %}
public class Model
{
    public string Header
	{
	    get;
	    set;
	}
}
{% endhighlight %}
{% endtabs %}

* **ViewModel.cs**

{% tabs %}
{% highlight C# %}
public class ViewModel
{
	private ObservableCollection<Model> pinItems;
	public ObservableCollection<Model> PinItems
	{
	   get { return pinItems; }
	   set { pinItems = value; }
	}
	public ViewModel()
	{
		PinItems = new ObservableCollection<Model>();
		populateItems();
	}
	private void populateItems()
	{
		PinItems.Add(new Model() { Header = "DoubleTextBox" });
		PinItems.Add(new Model() { Header = "UpDown" });
		PinItems.Add(new Model() { Header = "AutoComplete" });
		PinItems.Add(new Model() { Header = "PivotGrid" });
		PinItems.Add(new Model() { Header = "MaskedTextBox" });
	}
}
{% endhighlight %}
{% endtabs %}

* **MainWindow.Xaml**

{% tabs %}
{% highlight XAML %}
<syncfusion:PinnableListBox DisplayMemberPath="Header" ItemsSource="{Binding pinItems}" Width="200"/>
{% endhighlight %}
{% endtabs %}

![wpf pinnable lixt box data binding](Binding-Support_images/Binding-Support_img1.png)