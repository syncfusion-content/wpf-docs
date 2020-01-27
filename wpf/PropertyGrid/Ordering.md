---
layout: post
title: Ordering the Properties in WPF PropertyGrid control | Syncfusion
description: This section explains how the property items can be ordered into the WPF PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Ordering the Properties

Users can order the properties according to their needs. You can change the order of the properties by [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) Attribute's [Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8) field of the property.

## Ordering using Attribute

The properties in `PropertyGrid` will be ordered based on the value specified in the [Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8) field of [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute. If you need to change the order of the properties, you should set the `SortDirection` property to `null`. The properties can be ordered on the basis of with and without grouping mode. 

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;

public class Model
{
    [Display(Order = 4)]
    public String Gender
    {
        get;

        set;
    }

    [Display(Order = 7)]
    [Category("Address")]        
    public String Country
    {
        get;

        set;
    }
    
    [Display(Order = 6)]
    [Category("Contact Details")]
    public string Email
    {
        get;

        set;
    }

    [Display(Order = 0)]
    [Category("Identity")]        
    public string FirstName
    {
        get;

        set;
    }

    public string Designation
    {
        get;

        set;
    }
    
    [Display(Order = 1)]
    [Category("Identity")]
    public string LastName
    {
        get;

        set;
    }
   
    public string ID
    {
        get;

        set;
    }

    [Display(Order = 4)]
    public DateTime DOB
    {
        get;

        set;
    }

    
    [Display(Order = 5)]
    [Category("Contact Details")]
    public string Mobile
    {
        get;

        set;
    }

    [Display(Order = 2)]
    public int Age
    {
        get;

        set;
    }
}
        
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight C# %}

//ViewModel.cs

public class ViewModel
{
    private Object items = null;
   
    public Object Items
    {
        get
        {
            return items;
        }
        set
        {
            items = value;
        }
    }

    public ViewModel()
    {
        Items = new Model() { FirstName = "Carl", LastName = "johnson", Age =30, Country= "United States", Designation="Team Lead", DOB= new DateTime(2000, 12, 01), Email="carljanson@gta.com", Gender="Male", ID="SF001", Mobile="1234567890" };
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<Window x:Class="PropertyGrid_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:PropertyGrid_WPF"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d" WindowStartupLocation="CenterScreen"
        Title="MainWindow" Height="572" Width="800">
    <Window.DataContext>
        <local:ViewModel></local:ViewModel>
    </Window.DataContext>
    <Grid x:Name="LayoutRoot" Background="White" HorizontalAlignment="Stretch" VerticalAlignment="Stretch">
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}"
                                 SortDirection="{x:Null}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


### Ordering With Grouping mode

Based on the value specified in the `Order` field of `Display` attribute, the property items will be ordered and grouped. Groups are ordered according to which group contains the lower ordered property

![Properties are in ordered based on the value specified in the Order field of the Display attribute](Sorting-Images\Categories-Ordering.png)

Here, the `FirstName` property contains the lower order as `0` and categorized under the `Identity` category. Then the `Identity` category ordered as first. After that, `Age` property contains the lower order as `2` from another category, So `Misc` category ordered as `second`  and vice versa.

### Ordering Without Grouping mode

If more than one property has same `Order` value, then the properties with distinct numbers will be added first then the duplicate order properties will be added. Also, if any of the properties doesn’t have order, that properties will be arranged at last based on the order in which they were added in the class.

![Properties are in ordered based on the value specified in the Order field of the Display attribute](Sorting-Images\Properties-Ordering.png)

Here, the property `DOB` and `Gender` has same order but the property `Gender` property is added prior than `DOB`. So the `Gender` property will be arranged in `4th` place, and the `DOB` is arranged after Country property. And the other non-specified order properties are arranged based on the order in which they were added to the Class.

## Ordering without Attributes

The Ordering can be performed without using any Attributes. If the `SortDirection` property is `null` and the properties have no custom order then the properties will be ordered according to the order in which they were added to the class.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;

public class Model
{
    [Category("Identity")]
    public String Gender
    {
        get;

        set;
    }
    
    [Category("Address")]
    public String Country
    {
        get;

        set;
    }
    
    [Category("Contact Details")]
    public string Email
    {
        get;

        set;
    }
            
    [Category("Identity")]
    public string FirstName
    {
        get;

        set;
    }

    public string Designation
    {
        get;

        set;
    }

    [Category("Identity")]
    public string LastName
    {
        get;

        set;
    }

    public string ID
    {
        get;

        set;
    }

    public DateTime DOB
    {
        get;

        set;
    }

    [Category("Contact Details")]
    public string Mobile
    {
        get;

        set;
    }

    public int Age
    {
        get;

        set;
    }
}
        
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight C# %}

//ViewModel.cs

public class ViewModel
{
    private Object items = null;
   
    public Object Items
    {
        get
        {
            return items;
        }
        set
        {
            items = value;
        }
    }

    public ViewModel()
    {
        Items = new Model() { FirstName = "Carl", LastName = "johnson", Age =30, Country= "United States", Designation="Team Lead", DOB= new DateTime(2000, 12, 01), Email="carljanson@gta.com", Gender="Male", ID="SF001", Mobile="1234567890" };
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<Window x:Class="PropertyGrid_WPF.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:PropertyGrid_WPF"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d" WindowStartupLocation="CenterScreen"
        Title="MainWindow" Height="572" Width="800">
    <Window.DataContext>
        <local:ViewModel></local:ViewModel>
    </Window.DataContext>
    <Grid x:Name="LayoutRoot" Background="White" HorizontalAlignment="Stretch" VerticalAlignment="Stretch">
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}"
                                 SortDirection="{x:Null}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 

![Properties are in ordered based on they added into the Class](Sorting-Images\Property-Default-Ordering.png)

Here, the properties are arranged from the `Gender` property and end with `Age` property by the order in which they were added to the class. 


![Categories are in ordered based on they added into the Class](Sorting-Images\Category-Default-Ordering.png)

Here, the `Gender` property added in the class at `first` and categorized under the `Identity` category. Then the `Identity` category ordered as `first`. After that, `Country` property added in the class from another category, So `Address` category ordered as `second` and vice versa.

N>If you use both `Ordering` and `Sorting`, `Sorting` have higher priority. So the properties are arranged either `Ascending` or `Descending` order according to the sorting value.