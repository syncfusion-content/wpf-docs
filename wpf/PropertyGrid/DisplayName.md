---
layout: post
title: DisplayName of the Properties in WPF PropertyGrid control | Syncfusion
description: This section explains how the display name of the property item has been customized through attributes.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# DisplayName of the Properties in WPF PropertyGrid

This sections explains about how the name of the property item works based on `Display` and `DisplayName` attributes. 

## Naming through Display attribute`s Name field

Users can use the [Name](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.name?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_Name) field of the [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute to give a meaningful name for the properties to be displayed in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) instead of the property name.
Here, the `Name` and `ID` properties will be displayed as `Employee Name` and  `Employee ID`  respectively. 

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel.DataAnnotations;

public class Model
{
    [Display(Name = "Employee Name")] 
    public string Name
    {
        get;

        set;
    }

    [Display(Name = "Employee ID")]  
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight %} 
{% endtabs %} 


![Value specified in the Name field of the Display attribute is displayed as Name of the property in PropertyGrid](Attribute-Images\Display-Name-Attribute.png)

## Naming through DisplayName attribute

User can use the [DisplayName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.displaynameattribute?view=netframework-4.8) attribute to provide a meaningful name for the properties in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) instead of the property name. Here, the property `ID` and `DOB` will be displayed as `Employee ID` and `Date of Birth` respectively. 

{% tabs %}
{% highlight C# %}

//Model.cs

using System;

using System.ComponentModel;

public class Model

{

    public string Name
    {
        get;

        set;
    }

    [DisplayName("Employee ID")]
    public string ID
    {
        get;

        set;
    }

    [DisplayName("Date of Birth")]
    public DateTime DOB
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


![Value specified in the DisplayName attribute is displayed as Name of the property in PropertyGrid](Attribute-Images\DisplayName-Attribute.png)

N> If you use both the `DisplayName` attribute and `Name` field of the `Display` attribute, the `Name` field of the `Display` attribute will have higher priority.

## Naming through AutoGeneratingPropertyGridItem Event

The user can change the name of the properties by using the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event.
To change the property's display name, you can set the new name to the `AutoGeneratingPropertyGridItemEventArgs`'s `DisplayName` property. It will displayed as a name of the property in `PropertyGrid`.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    [Description("Employee Name")]
    public string Name
    {
        get;

        set;
    }        
    
    public DateTime DOB
    {
        get;

        set;
    }

    [Display(Description = "Gender of the Employee")]
    public Gender Gender
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
        Items = new Model() { Name = "Johnson", Gender= Gender.Male, DOB = new DateTime(2000,01,25), };
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" AutoGeneratingPropertyGridItem="PropertyGrid1_AutoGeneratingPropertyGridItem" SelectedObject="{Binding Items}" 
                                 DescriptionPanelVisibility="Visible"  DescriptionPanelHeight="50">
        </syncfusion:PropertyGrid>
    </Grid>

</Window>
{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e)
{
    //DOB property new description assigned.
    if (e.DisplayName == "DOB")
    {
        e.Description = "Birth date of the Employee";
    }

    //Name property description changed.
    if (e.DisplayName == "Name")
    {
        e.Description = "Name of the Employee";
    }
}
      
{% endhighlight %} 
{% endtabs %}
