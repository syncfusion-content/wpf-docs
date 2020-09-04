---
layout: post
title: Filtering items in WPF PropertyGrid control | Syncfusion
description: This section explains about how the property items are filtered through attributes, event and property of WPF PropertyGrid control
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Filtering and Searching the properties in WPF PropertyGrid

We can decide the properties which are need to be displayed in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) by hiding the unwanted properties using collection and attributes. We can navigate to the particular property by using the default SearchBox.

## Hide the Properties using Collection

We can hide the properties using the [HidePropertiesCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html#Syncfusion_Windows_PropertyGrid_PropertyGrid_HidePropertiesCollection) property. It is used to hide the mentioned properties which are already present in [SelectedObject](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html#Syncfusion_Windows_PropertyGrid_PropertyGrid_SelectedObject). Properties can also be hidden at runtime using  `HidePropertiesCollection`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public string Name { get; set; }
    public string Email { get; set; }
    public string Bank { get; set; }
    public string ID { get; set; }
    public string AccountNumber { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

 public class ViewModel {
    private ObservableCollection<string> hidePropertyItems = new ObservableCollection<string>();
    public Object SelectedEmployee { get; set; }
    public ObservableCollection<string> HidePropertyItems
    {
        get { return hidePropertyItems; }
        set { hidePropertyItems = value; }
    }
    public ViewModel() {
        var employee = new Employee()
        { 
            Email = "john@gta.com",
            AccountNumber="23456784",
            Bank="ABC bank",
            Name = "Johnson",
            Experience=5,
            ID = "895",
            Age = 35,
        };
        HidePropertyItems.Add(nameof(employee.AccountNumber));
        HidePropertyItems.Add(nameof(employee.Email));
        HidePropertyItems.Add(nameof(employee.Bank));
        SelectedEmployee = employee;
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid HidePropertiesCollection="{Binding HidePropertyItems}" 
                         SelectedObject="{Binding SelectedEmployee}" 
                         x:Name="propertyGrid1" Width="350" Height="200" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));

{% endhighlight %} 
{% endtabs %} 

![AccountNumber, Bank and Email properties are not displayed in PropertyGrid](Filtering-Images\HideItemCollection.png)

Here, the `PropertyGrid` hides the properties `AccountNumber`, `Bank` and `Email` properties which are specified in the `HidePropertiesCollection`.

N>`HidePropertiesCollection` cannot hide the properties which are added using `DynamicDescriptor`.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/HidePropertyByCollection) to download the sample that showcases the filtering  support using the `HidePropertiesCollection`.

## Hide the Properties using Attributes

We can hide properties by setting the [Browsable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.browsableattribute?view=netframework-4.8) value as `false` or [Bindable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.bindableattribute?view=netframework-4.8) as `false`, which properties will not be displayed in `PropertyGrid`. Functionalities of `Browsable` and `Bindable` attributes are same.  

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;

public class Employee {
    [Browsable(false)]
    public string Bank { get; set; }
    [Bindable(false)]
    public string AccountNumber { get; set; }
    [Browsable(false)]
    public string Email { get; set; }
    public string Name { get; set; } 
    public string ID { get; set; }       
    public int Age { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Email = "john@gta.com",
            AccountNumber = "23456784",
            Bank = "ABC bank",
            Name = "Johnson",
            Experience = 5,
            ID = "895",
            Age = 35,
        };
    }
}

{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"                   
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));

{% endhighlight %}
{% endtabs %} 

![AccountNumber, Bank and Email properties are not displayed in PropertyGrid](Filtering-Images\HideItem-Attribute.png)

Here, the `PropertyGrid` not displayed the `AccountNumber`, `Bank` and `Email` properties which are specified `Browsable` and `Bindable` attribute value as `false`. 

N> If we use both the `Browsable` and `Bindable` attributes, the `Browsable` attribute have a higher priority.

### Hide the Properties using Display.AutoGeneratedField

If a property has the value of `Browsable` attribute as `true` and `Bindable` attribute as `true`, then properties are not hidden. We can hide the property by using the [AutoGeneratedField](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.autogeneratefield?view=netframework-4.8#System_ComponentModel_DataAnnotations_DisplayAttribute_AutoGenerateField) of `Display` as `false`. Value of `AutoGeneratedField` has no effect when the property is marked `Browsable` or `Bindable` as `false`.

{% tabs %}
{% highlight C# %}

public class Employee
{        
    [Browsable(true)]
    [Bindable(true)]
    [Display(AutoGenerateField = false)]
    public string Bank { get; set; }
    [Display(AutoGenerateField = false)]
    [Browsable(true)]
    [Bindable(true)]
    public string AccountNumber { get; set; }  
    [Browsable(false)]
    [Bindable(true)]
    [Display(AutoGenerateField = false)]
    public string ID { get; set; }      
    public string Email { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Email = "john@gta.com",
            AccountNumber = "23456784",
            Bank = "ABC bank",
            Name = "Johnson",
            Experience = 5,
            ID = "895",
            Age = 35,
        };
    }
}

{% endhighlight %} 
{% endtabs %} 


{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"          
                         x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));

{% endhighlight %} 
{% endtabs %} 

![AccountNumber and Bank properties are not displayed in PropertyGrid](Filtering-Images\HideItem-AutoField.png)

Here, the `PropertyGrid` not displayed the `Bank` and `AccountNumber` properties. The `Bank` and `AccountNumber` property are not displayed by value of `Browsable` attribute as `true` and `Bindable` attribute as `true` and the `AutoGeneratedField` of `DisplayAttribute` is `false`.In `ID` property, the `Browsable` is `false`, then the `AutoGeneratedField` property have no effect. 

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/HidePropertyByAttribute) to download the sample that showcases the filtering  support using the attributes.

## Hide the Properties at runtime

We can hide the properties in the `PropertyGrid` without using the attributes at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html) event with [AutoGeneratingPropertyGridItemEventArgs.Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html) property as `true`.
   
{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public int Experience { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }

    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Experience = 5;
        };
    }
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGeneratingPropertyGridItem="PropertyGrid1_AutoGeneratingPropertyGridItem"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid1.AutoGeneratingPropertyGridItem += PropertyGrid1_AutoGeneratingPropertyGridItem;

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e) {
    //Name and Experience properties hided in the PropertGrid control.
    if (e.DisplayName == "Experience") {
        e.Cancel = true;
    }
    else if (e.DisplayName == "Name") {
        e.Cancel = true;
    }
}

{% endhighlight %} 
{% endtabs %} 

![Designation and Age properties are not displayed in PropertyGrid](Filtering-Images\AutoGeneratingPropertyGridItem.png)

Here, the `Experience` and `Name` properties are not displayed in the `PropertyGrid`, since the properties was restricted to be added in `PropertyGrid` by the `AutoGeneratingPropertyGridItem` event.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property filtering support using `AutoGeneratingPropertyGridItem` event.

## Searching the Properties

If the `PropertyGrid.SelectedObject` contains more properties, it is difficult to find the specific property. Now, we can easily get the required properties by searching the property name in the SearchBox. SearchBox will be filter and display the properties which are contains the searched text. SearchBox is shown by default, we can hide it by setting [SearchBoxVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html#Syncfusion_Windows_PropertyGrid_PropertyGrid_SearchBoxVisibility) property as `Collapsed`.

{% tabs %}
{% highlight C# %}

public class Employee {
    public int Age { get; set; }
    public string Name { get; set; }
    public string EmailID { get; set; }
    public string ID { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        { 
            EmailID="johnson@gta.com",
            Age = 23, 
            ID = "1207", 
            Name = "John Son"
        };
    }
}

{% endhighlight %} 
{% endtabs %}

**SearchBoxVisibility = Visible**

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid Name="propertyGrid1" SelectedObject="{Binding SelectedEmployee }" SearchBoxVisibility="Visible" />

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;
propertyGrid1.SearchBoxVisibility = Visibility.Visible;

{% endhighlight %} 
{% endtabs %}

![SearchBox filter the Age property in PropertyGrid](Filtering-Images\Searching.png)

Here, The `Age` property is searched in the SearchBox.                                             

**SearchBoxVisibility = Collapsed**

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid Name="propertyGrid1" SelectedObject="{Binding SelectedEmployee }" SearchBoxVisibility="Collapsed" />

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SelectedObject = (propertyGrid1.DataContext as ViewModel).SelectedEmployee;
propertyGrid1.SearchBoxVisibility = Visibility.Collapsed;

{% endhighlight %} 
{% endtabs %}

![SearchBox not displayed in PropertyGrid](Filtering-Images\SearchBox-collapsed.png)

Here, The SearchBox is hidden in the `PropertyGrid`.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Grouping-Sorting-Ordering) to download the sample that showcases the property searching in the SearchBox support.

                                           







