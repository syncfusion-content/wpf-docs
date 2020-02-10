---
layout: post
title: Filtering items in WPF PropertyGrid control | Syncfusion
description: This section explains about how the property items are filtered through attributes, event and property of WPF PropertyGrid control
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Filtering properties in WPF PropertyGrid

The user can decide the properties which are need to be displayed in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid). 

## Hide the Properties through Collection

The User can hide the properties using the [HidePropertiesCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~HidePropertiesCollection.html) property. It is used to hide the mentioned properties which are already present in [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html). Properties can also be hidden at runtime using  `HidePropertiesCollection`.

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

using System;
using System.Collections.ObjectModel;

public class ViewModel
{
    private Object items = null;
    private ObservableCollection< string > hideItems = new ObservableCollection< string >();

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

    public ObservableCollection<string> HideItems
    {
        get
        {
            return hideItems;
        }
        set
        {
            hideItems = value;
        }
    }

    public ViewModel()
    {
        var model = new Model() { AccountNumber="0058", Bank="ABC Bank", Email="John@gta.com", ID="SF005", Name="Johnson"};
        HideItems.Add(nameof(model.ID));
        HideItems.Add(nameof(model.Bank));
        Items = model;
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" HidePropertiesCollection="{Binding HideItems}" SelectedObject="{Binding Items}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 

![Bank and ID properties are not displayed in PropertyGrid](Filtering-Images\HideItemCollection.png)

Here, the `PropertyGrid` hides the properties `Bank` and `ID` which are specified in the `HidePropertiesCollection`.

N>`HidePropertiesCollection` cannot hide the properties which are added through `DynamicDescriptor`.

## Hide the Properties through Attributes

The User can hide properties by setting the [Browsable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.browsableattribute?view=netframework-4.8) value as `false` or [Bindable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.bindableattribute?view=netframework-4.8) as `false`, which properties will not be displayed in `PropertyGrid`. Functionalities of `Browsable` and `Bindable` attributes are same.  

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;

public class Model
{
    [Browsable(false)]              
    public string Name
    {
        get;
        set;
    }        
   
    [Bindable(false)]
    public string Email
    {
        get;
        set;
    }
    
    [Browsable(true)]
    [Bindable(false)]
    public string Bank
    {
        get;
        set;
    }

    public string ID
    {
        get;
        set;
    }
    
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
        Items = new Model() { AccountNumber="0058", Bank="ABC Bank", Email="John@gta.com", ID="SF005", Name="Johnson"};
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

![Name and Email properties are not displayed in PropertyGrid](Filtering-Images\HideItem-Attribute.png)

Here, the `PropertyGrid` not displayed the `Name` and `Email` properties which are specified `Browsable` and `Bindable` attribute value as `false`. 

N> If you use both the `Browsable` and `Bindable` attributes, the `Browsable` attribute have a higher priority.

## Hide the Properties through AutoGeneratedField

If a property has the value of `Browsable` attribute as `true` and `Bindable` attribute as `true` and the [AutoGeneratedField](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.autogeneratefield?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_AutoGenerateField) of `DisplayAttribute` is `false`, then the property item will not be added to the `Properties` collection of `PropertyGrid` and not visible in the UI. Value of `AutoGeneratedField` has no effect when the property is marked `Browsable` or `Bindable` as `false`.

{% tabs %}
{% highlight C# %}

//Model.cs

using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    public string Name
    {
        get;
        set;
    }

    [Display(AutoGenerateField = false)]
    [Browsable(true)]
    [Bindable(true)]
    public string Bank
    {
        get;
        set;
    }
  
    [Display(AutoGenerateField = true)]
    [Browsable(false)]   
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
        Items = new Model() { Bank = "ABC Bank", Name = "Johnson", ID = "SF008" };
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

![Bank and ID properties are not displayed in PropertyGrid](Filtering-Images\HideItem-AutoField.png)

Here, the `PropertyGrid` not displayed the `Bank` and `ID` properties. The `Bank` property is not displayed by value of `Browsable` attribute as `true` and `Bindable` attribute as `true` and the `AutoGeneratedField` of `DisplayAttribute` is `false`.In `ID` property, the `Browsable` is `false`, then the `AutoGeneratedField` property have no effect. 

## Hide the Properties through AutoGeneratingPropertyGridItem event

Properties of [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SelectedObject.html) has been read and the properties will be added to the `Properties` collection of `PropertyGrid`. From the `Properties` collection of `PropertyGrid`, properties will be displayed in the `PropertyGrid`. Generation of properties in the `Properties` collection of `PropertyGrid` can be restricted through [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event by setting `Cancel` property as `true`.  `AutoGeneratingPropertyGridItemEventArgs` provides the information about the properties available in the `PropertyGrid`.


{% tabs %}
{% highlight C# %}

//Model.cs

using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    public string Name
    {
        get;

        set;
    }

    public string Country
    {
        get;

        set;
    }

    public string ID
    {
        get;

        set;
    }

    public string Designation
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
        Items = new Model() { Name = "Johnson", ID = "SF008", Age=30, Country="UnitedStates", Designation="Team Lead"};
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}" AutoGeneratingPropertyGridItem="PropertyGrid1_AutoGeneratingPropertyGridItem">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e)
{           
    //Designation and Age properties will not be displayed in PropertyGrid
    if (e.DisplayName == "Designation" || e.DisplayName =="Age")
    {
        e.Cancel = true;
    }
}
      
{% endhighlight %} 
{% endtabs %}

![Designation and Age properties are not displayed in PropertyGrid](Filtering-Images\AutoGeneratingPropertyGridItem.png)

Here, the `Designation` and `Age` properties are not displayed in the `PropertyGrid`, since the properties was restricted to be added in `Properties` collection of the `PropertyGrid`.






