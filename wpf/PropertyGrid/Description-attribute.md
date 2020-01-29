---
layout: post
title: Description settings in WPF PropertyGrid control | Syncfusion
description: This section explains how a description of the property item has been added through attributes in the WPF PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Description settings for the Properties

Users can display the description about the property through the  Description panel which is placed on the bottom of the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control. Description panel visibility can be managed by [DescriptionPanelVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelVisibility.html) property . The default value of the `DescriptionPanelVisibility` is `Collapsed`. User should enables this property to display the description of the property. User can change Description panel height by setting the [DescriptionPanelHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~DescriptionPanelHeight.html)  property.

## Property Description through Display attribute`s Description field 

Users can use the [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.description?view=netframework-4.8) field of the [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute to give a meaningful description about the properties to be displayed in `PropertyGrid` Description Panel. 

{% tabs %}
{% highlight C# %}

//Model.cs

using System;

using System.ComponentModel.DataAnnotations;

public class Model

{

    [Display(Description = "Name of the employee")] 
    public string Name
    {
        get;

        set;
    } 

    public string ID
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
        Items = new Model() {Name="John", ID = "SF001" };
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
                                 DescriptionPanelVisibility="Visible"  DescriptionPanelHeight="50">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>

{% endhighlight %} 
{% endtabs %} 

![Value specified in the Description field of the Display attribute is displayed in the Description Panel](Attribute-Images\Display-Description-Attribute.png)

Here, the description about the `Name` property  will be displayed in the Description Panel. 

## Property Description through Description attribute

Users can use the [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.descriptionattribute?view=netframework-4.8) attribute to give a meaningful description about the properties to be displayed in `PropertyGrid` Description Panel. Here, the description about the `DOB` property  will be displayed in the Description Panel. 


{% tabs %}
{% highlight C# %}

//Model.cs

using System;

using System.ComponentModel;

public class Model

{
    
    [Description("Birth date of the employee")]
    public string DOB
    {
        get;

        set;
    }

    public string Name
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
        Items = new Model() { Name="Peter", DOB = new DateTime(2000,01,08) };
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
                                 DescriptionPanelVisibility="Visible"  DescriptionPanelHeight="50">>
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


![Value specified in the Description attribute is displayed in the Description Panel](Attribute-Images\Description-Attribute.png)

N> If you use both the `Description` attribute and `Description` field of the `Display` attribute, the `Description` attribute will have higher priority.


## Property Description through AutoGeneratingPropertyGridItem Event

The user can change the Description of the properties by using the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event.
To change the property's Description, you can set the new description to the `AutoGeneratingPropertyGridItemEventArgs`'s `Description` property. It will displayed in the Description panel.

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

![Description of the Properties added and modified by the Description property of the AutoGeneratingPropertyGridItem event](Attribute-Images\Description-AutoGeneratingPropertyGridItem.png)