---
layout: post
title: Sorting the Properties in WPF PropertyGrid control | Syncfusion
description: This section explains how the property items can be sorted into the WPF PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---



# Sorting and ordering the Properties

Users can sorting and ordering the properties according to their needs. You can change the sorting order of the properties by [SortDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SortDirection.html) property and ordering the properties by [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) Attribute's [Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8) field of the property. 

Values of `SortDirection` property is `Ascending`, `Descending` and `Null`. The Default value of the `SortDirection` property is `Ascending` order.

## Sorting without Ordering

Properties in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) are sorted by using the `SortDirection` property as the `Ascending` or `Descending` order based on the property name. If the properties are in the grouped state, then the groups are sorted based on the group name. 

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;

public class Model
{
    [Category("Identity")]
    public string Name
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

    [Category("Account Details")]
    public string Bank
    {
        get;
        set;
    }

    [Category("Identity")]
    public string ID
    {
        get;
        set;
    }
    
    [Category("Account Details")]
    public string AccountNumber
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
        Items = new Model() {Name="John",DOB = new DateTime(2000,12,02), ID = "SF001" };
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
                                 SortDirection="Ascending">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


![Value specified in the DisplayName attribute is displayed as Name of the property in PropertyGrid](Attribute-Images\DisplayName-Attribute.png)


