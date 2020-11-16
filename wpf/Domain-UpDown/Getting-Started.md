---
layout: post
title: Getting Started | DomainUpDown | WPF | Syncfusion
description: This section gives a detailed description of how to implement the SfDomainUpDown control in WPF application.
platform: WPF
control: DomainUpDown
documentation: ug
---

# Getting Started with WPF SfDomainUpDown 

This section provides you an overview of working with [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) for WPF and provides a walk through to configure the `SfDomainUpDown` control in a real time scenario.

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfdomainupdown) section to get the list of assemblies or NuGet package needs to be added as a reference to use the control in any application.

Further information on installing the NuGet package can be found in the following link. [How to install nuget packages](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages). You can also use the [Syncfusion Reference Manager](https://help.syncfusion.com/wpf/visual-studio-integration/visual-studio-extensions/add-references) to refer to the SfDomainUpDown's dependent assemblies.

## Creating Application with SfDomainUpDown control

In this walk through, you will create a WPF application that contains the [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control.

## Creating project

Create a new WPF project to show the [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control in Visual Studio.

## Adding control via designer

The [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control can be added to the application by dragging it from Toolbox and dropping it in the designer. The required [assemblies](https://help.syncfusion.com/wpf/control-dependencies#sfdomainupdown) will be added automatically.

![Adding control via designer](Getting-Started_images/SfDomainUpDown_GettingStarted_img2.png)

## Adding control manually in XAML

To add the control manually in XAML page, follow the given steps:

1.Add the following required assembly references to the project,

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

2.Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page or Syncfusion.Windows.Tools.Controls namespace.

3.Declare [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) in XAML page.

{% tabs %}

{% highlight xaml %}

<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:GettingStartedComboBox"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="GettingStartedComboBox.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:SfDomainUpDown Height="30" Width="150" Value="40" />
    </Grid>
</Window>

{% endhighlight %}

{% endtabs %}

## Adding control manually in C#

To add the control manually in C#, follow the given steps:

1.Add the following required assembly references to the project,

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

2.Import the `SfDomainUpDown` namespace **Syncfusion.Windows.Controls.Input**.

3.Create the `SfDomainUpDown` control instance and add it to the page.

{% tabs %}

{% highlight c# %}

using System.Windows;
using Syncfusion.Windows.Controls.Input;
namespace ComboBox
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfDomainUpDown sfDomainUpDown1 = new SfDomainUpDown();
            this.Content = sfDomainUpDown1;
            sfDomainUpDown1.Height = 30;
            sfDomainUpDown1.Width = 150;
            sfDomainUpDown1.Value = 40;
        }
    }
}
{% endhighlight %}

{% endtabs %}

![SfDomainUpDown control implemented](Getting-Started_images/Spin-Button_img6.png)


## Populating by DataBinding

You can populate the [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control using the [ItemsSource](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.itemscontrol.itemssourceproperty?view=netframework-4.7.2) property.

1.You can create a data object class named **Employee** as Model and declare properties as shown below,

{% tabs %}
{% highlight C# %}

public class Employee
{
    private string name;
    private string email;

    public string Email
    {
        get { return email; }
        set { email = value; }
    }

    public string Name
    {
        get { return name; }
        set { name = value; }
    }
}

{% endhighlight %}
{% endtabs %}

2.You can create a **ViewModel** class with several data objects in constructor.

{% tabs %}
{% highlight C# %}

public class ViewModel
{
	private List<Employee> employees;
	public List<Employee> Employees
	{
		get { return employees; }
		set { employees = value; }
	}
	public ViewModel()
	{
		Employees = new List<Employee>();
		populateItem();
	}
	private void populateItem()
	{
		Employees.Add(new Employee { Name = "Lucas", Email = "lucas@syncfusion.com" });
		Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });
		Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });
	}
}

{% endhighlight %}
{% endtabs %}

3.You can bind the Employees property from the ViewModel class to the ItemSource property of `SfDomainUpDown` control and the control is set to display content based on the Name inside the [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html#Syncfusion_Windows_Controls_Input_SfDomainUpDown_ContentTemplateProperty) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDomainUpDown x:Name="domainUpDown" HorizontalAlignment="Center" VerticalAlignment="Center" Width="200" ItemsSource="{Binding Employees}">
    <syncfusion:SfDomainUpDown.ContentTemplate>
        <DataTemplate>
            <StackPanel Orientation="Horizontal">
                <TextBlock Text="{Binding Name}"/>
            </StackPanel>
        </DataTemplate>
    </syncfusion:SfDomainUpDown.ContentTemplate>
</syncfusion:SfDomainUpDown>

{% endhighlight %}
{% endtabs %}

![wpf domain up down control added by code](Getting-Started_images/wpf-domain-updown-control-data-binding.png)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/WPF-GettingStarted-Databinding).

## Spin button alignment

You can customize the position of the spin button in the [SfDomainUpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html) control using the [SpinButtonsAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDomainUpDown.html#Syncfusion_Windows_Controls_Input_SfDomainUpDown_SpinButtonsAlignment) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDomainUpDown x:Name="domainUpDown" Height="35" Width="150" SpinButtonsAlignment="Right" Value="James" />

{% endhighlight %}
{% highlight C# %}

SfDomainUpDown domainUpDown1 = new SfDomainUpDown();
domainUpDown1.Height = 30;
domainUpDown1.Width = 150;
domainUpDown1.SpinButtonsAlignment = Syncfusion.Windows.Controls.SpinButtonsAlignment.Right;

{% endhighlight %}
{% endtabs %}

1.Right

![SpinButton aligned right](Getting-Started_images/Spin-Button-Alignment_img1.png)

2.Left

![SpinButton aligned left](Getting-Started_images/Spin-Button-Alignment_img3.png)

3.Both

![SpinButton aligned both](Getting-Started_images/Spin-Button-Alignment_img5.png)
