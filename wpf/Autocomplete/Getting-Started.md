---
layout: post
title: Getting Started | SfTextBoxExt | wpf | Syncfusion
description: This section provides details about AutoComplete and how to bind the data to the AutoComplete of SfTextBoxExt control.
platform: wpf
control: SfTextBoxExt
documentation: ug
---

# Getting Started

## Assembly deployment

Refer to this [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sftextboxext) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

Refer to this [How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages) documentation to find more details about installing the NuGet package in a WPF application.

## Creating a simple application

Create a WPF application with SfTextBoxExt control using the following steps:

### Create a project

Create a new WPF project in Visual Studio to display the SfTextBoxExt control with their functionalities.

### Add a control using the designer

The SfTextBoxExt control can be added to an application by dragging it from the toolbox to a designer view. The following required assembly references will be added automatically:

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

![DesignerView](GettingStarted_images/Designer.png)

### Adding control manually in XAML

To add the control manually in XAML, follow the given steps:

1. Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF
    * Syncfusion.SfShared.WPF
2. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3. Declare the SfTextBoxExt control in the XAML page.

{% tabs %}
{% highlight XAML %}

        <Grid>
            <editors:SfTextBoxExt HorizontalAlignment="Center" 
                                  VerticalAlignment="Center" 
                                  HorizontalContentAlignment="Center"
                                  Height="40"
                                  Width="200" 
                                  Text="Hello! World..."/>
        </Grid>
  
{% endhighlight %}
{% endtabs %}

### Add a control manually in C#

To add the control manually in C#, follow the given steps:

1. Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF
    * Syncfusion.SfShared.WPF
2. Import the SfTextBoxExt namespace using **Syncfusion.Windows.Controls.Input;**.
3. Create an SfTextBoxExt instance, and add it to the window.

{% tabs %}
{% highlight C# %}

            SfTextBoxExt textBoxExt = new SfTextBoxExt()
            {
                HorizontalContentAlignment = HorizontalAlignment.Center,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center,
                Width = 200,
                Height = 40,
                Text = "Hello! World..."
            };

{% endhighlight %}
{% endtabs %}

![GettingStarted](GettingStarted_images/GettingStarted.png)

## Populating AutoComplete with Data

To populate the AutoComplete with data, set the [AutoCompleteSource](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~AutoCompleteSource.html) property to `IEnumerable` implementation.

For further details, refer to [AutoComplete with Data](https://help.syncfusion.com/wpf/autocomplete/auto-complete).

For illustration, let us create a textbox, which will populate a list of employees.

The Employee model will be as follows.


{% highlight c# %}

public class Employee
    {
        public string Name { get; set; }
        public string Email { get; set; }
    }
	
{% endhighlight %}


Create a collection attribute and populate the collection with items.

{% highlight c# %}

 public class EmployeeViewModel
    {
        private List<Employee> employees;
        public List<Employee> Employees
        {
            get { return employees; }

            set { employees = value; }
        }
        public EmployeeViewModel()
        {
            Employees = new List<Employee>();
            Employees.Add(new Employee { Name = "Lucas", Email = "lucas@syncfusion.com" });
            Employees.Add(new Employee { Name = "James", Email = "james@syncfusion.com" });
            Employees.Add(new Employee { Name = "Jacob", Email = "jacob@syncfusion.com" });
        }
    }

{% endhighlight %}

{% tabs %}
{% highlight xaml %}

        <editors:SfTextBoxExt HorizontalAlignment="Center" 
                              VerticalAlignment="Center" 
                              Width="300"
                              Height="40"
                              SearchItemPath="Name"
                              AutoCompleteMode="Suggest"
                              AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% endtabs %}

![GettingStarted](GettingStarted_images/AutoCompleteSource.png)

Find sample from [this](https://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoComplete_WPF958872664) link.

## Autocomplete modes 

Suggestions can be shown in number of ways. TextBoxExt supports the following.

<table>
<tr>
<th>AutoCompleteMode</th>
<th>Description</th>
</tr>
<tr>
<td>Suggest</td>
<td>
Shows the suggestion in the drop-down list user.
</td>
</tr>
<tr>
<td>Append</td>
<td>
Appends the first suggestion to the text.
</td>
</tr>
<tr>
<td>SuggestAppend</td>
<td>
Shows the suggestion in the drop-down list and appends the first suggestion to the text.
</td>
</tr>
<tr>
<td>None</td>
<td>
In None mode, the search algorithm starts even when the item is not available in the data source.
</td>
</tr>
</table>

The default value of [AutoCompleteMode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~AutoCompleteModeProperty.html) is None.


{% tabs %}
{% highlight xaml %}

        <editors:SfTextBoxExt HorizontalAlignment="Center" 
                                 VerticalAlignment="Center" 
                                 Width="300"
                                 Height="40"
                                 SearchItemPath="Name"
                                 AutoCompleteMode="Suggest"
                                 SuggestionMode="StartsWith"
                                 AutoCompleteSource="{Binding Employees}" />

{% endhighlight %}
{% endtabs %}

![Suggest](Auto-Complete_images/Auto-Complete_img2.png)

Filtered suggestions displayed in drop-down list
{:.caption}

## Selection 

Index of the selected items can be retrieved by using the [SuggestionIndex](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~SuggestionIndex.html) property. The selected items of the AutoComplete can be retrieved by using the [SelectedItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTextBoxExt~SelectedItem.html) property.

For further details, refer to [Retrieving selected values](https://help.syncfusion.com/wpf/autocomplete/retrieving-selected-values).