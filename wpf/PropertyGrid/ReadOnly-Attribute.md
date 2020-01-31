---
layout: post
title: ReadyOnly and Editable attributes in WPF PropertyGrid | Syncfusion
description: Learn about make the properties of selected object as readonly in Syncfusion WPF PropertyGrid control and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# ReadOnly properties properties in WPF PropertyGrid

The user can decide the properties which are need to be readonly(non-editable) in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid). It can be achieved by attributes and event.

## Non-Editable properties through attributes

The user can makes the properties as non-editable by using the [ReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.readonlyattribute?view=netframework-4.8) and [Editable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.editableattribute?view=netframework-4.8) attributes. When the property is marked as `ReadOnly` or `Editable` as `false`, the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) will not allow the user to change the property values.

`Password` property is marked as Editable false and `DOB` is marked as ReadOnly.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Model
{
    public string Name
    {
        get;

        set;
    }

    [ReadOnly(true)]
    public DateTime DOB
    {
        get;

        set;
    }

    [Editable(false)]
    public Gender Gender
    {
        get;

        set;
    }
}

public enum Gender
{
    Male,
    Female
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
        <syncfusion:PropertyGrid x:Name="propertyGrid1" Width="350" Height="200" SelectedObject="{Binding Items}">
        </syncfusion:PropertyGrid>
    </Grid>
</Window>
{% endhighlight %} 
{% endtabs %} 


Here, the `DOB` and `Gender` properties not editable,

![DOB and Gender is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)

## Non-Editable properties through AutoGeneratingPropertyGridItem event

The user can makes the properties as non-editable by using the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~AutoGeneratingPropertyGridItem_EV.html) event .
When `AutoGeneratingPropertyGridItemEventArgs`'s `ReadOnly` property value sets as `true`, the property will be classified as ReadOnly, then the `PropertyGrid` will not allow the user to change the property values. The Default value of `AutoGeneratingPropertyGridItemEventArgs`'s `ReadOnly` property is `false`.

{% tabs %}
{% highlight C# %}

//Model.cs

using System;

public class Model
{
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
   
    public Gender Gender
    {
        get;

        set;
    }
}

public enum Gender
{
    Male,

    Female
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
    //DOB and Gender properties will not be editable in PropertyGrid
    if (e.DisplayName == "DOB" || e.DisplayName == "Gender")
    {
        e.ReadOnly = true;
    }
}
      
{% endhighlight %} 
{% endtabs %}

Here, the `DOB` and `Gender` properties not editable,

![DOB and Gender is not editable in PropertyGrid](Attribute-Images\ReadOnly-Editable-Attribute.png)