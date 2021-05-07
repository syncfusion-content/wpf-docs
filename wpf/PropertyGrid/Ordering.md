---
layout: post
title: Ordering in WPF PropertyGrid control | Syncfusion
description: Learn about Ordering support in Syncfusion Essential Studio WPF PropertyGrid control, its elements and more details.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Ordering in WPF PropertyGrid

We can order the properties according to our needs. We can change the order of the properties by attributes and event.

## Ordering using Attribute

The properties in [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) will be ordered based on the value specified in the [Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8) field of [Display](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) attribute. If we need to change the order of the properties, we should set the `SortDirection` property to `null`.

{% tabs %}
{% highlight C# %}

public class Employee {
    [Display(Order = 4)]
    public String Gender { get; set; }

    [Display(Order = 7)]
    [Category("Address")]
    public String Country { get; set; }

    [Display(Order = 6)]
    [Category("Contact Details")]
    public string Email { get; set; }

    [Display(Order = 0)]
    [Category("Identity")]
    public string FirstName { get; set; }

    public string Designation { get; set; }

    [Display(Order = 1)]
    [Category("Identity")]
    public string LastName { get; set; }

    public string ID { get; set; }

    [Display(Order = 4)]
    public DateTime DOB { get; set; }

    [Display(Order = 5)]
    [Category("Contact Details")]
    public string Mobile { get; set; }

    [Display(Order = 2)]
    public int Age { get; set; }
}

public class ViewModel {
    public Object SelectedEmplyee { get; set; }
    public ViewModel() {
        SelectedEmplyee = new Employee() { 
            FirstName = "Carl", 
            LastName = "johnson", 
            Age = 30, 
            Country = "United States",
            Designation = "Team Lead",
            DOB = new DateTime(2000, 12, 01),
            Email = "carljanson@gta.com", 
            Gender = "Male",
            ID = "SF001", 
            Mobile = "1234567890" 
        };
    }
}
        
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}" EnableGrouping="True" 
                         SortDirection="{x:Null}" x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid1.EnableGrouping = true;
propertyGrid1.SortDirection = null;

{% endhighlight %}
{% endtabs %}

### Ordering in Group view

Based on the value specified in the `Order` field of `Display` attribute, the property items will be ordered and grouped. Groups are ordered according to group which contains the lower ordered property.

![Properties are in ordered based on the value specified in the Order field of the Display attribute](Sorting-Images\Categories-Ordering.png)

Here, the `FirstName` property contains the lower order as `0` and categorized under the `Identity` category. Then the `Identity` category ordered as first. After that, `Age` property contains the lower order as `2` from another category, So `Misc` category ordered as `second`  and vice versa.

### Ordering with Sort view

If more than one property has same `Order` value, then the properties with distinct numbers will be added first, then the duplicate order properties will be added. Also, if any of the properties doesn’t have order, that properties will be arranged at last based on the order in which they were added in the class.

![Properties are in ordered based on the value specified in the Order field of the Display attribute](Sorting-Images\Properties-Ordering.png)

Here, the property `DOB` and `Gender` has same order but the `Gender` property is added prior than `DOB`. So the `Gender` property will be arranged in `4th` place, and the `DOB` is arranged after Country property. And the other non-specified order properties are arranged based on the order in which they were added to the Class.

## Ordering based on properties defined in class

The Ordering can be performed without using any Attributes. If the `SortDirection` property is `null` and the properties have no custom order, then the properties will be ordered according to the order in which they were added to the class.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;

public class Employee {
    [Category("Identity")]
    public String Gender { get; set; }

    [Category("Address")]
    public String Country { get; set; }

    [Category("Contact Details")]
    public string Email { get; set; }

    [Category("Identity")]
    public string FirstName { get; set; }

    public string Designation { get; set; }

    [Category("Identity")]
    public string LastName { get; set; }

    public string ID { get; set; }

    public DateTime DOB { get; set; }

    [Category("Contact Details")]
    public string Mobile { get; set; }

    public int Age { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee() 
        { 
            FirstName = "Carl",
            LastName = "johnson", 
            Age = 30,
            Country = "United States", 
            Designation = "Team Lead",
            DOB = new DateTime(2000, 12, 01),
            Email = "carljanson@gta.com", 
            Gender = "Male", 
            ID = "SF001", 
            Mobile = "1234567890"
        };
    }
}

{% endhighlight %} 
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
                         SortDirection="{x:Null}" x:Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));
propertyGrid1.SortDirection = null;

{% endhighlight %}
{% endtabs %} 

![Properties are in ordered based on they added into the Class](Sorting-Images\Property-Default-Ordering.png)

Here, the properties are arranged from the `Gender` property and end with `Age` property by the order in which they were added to the class. 


![Categories are in ordered based on they added into the Class](Sorting-Images\Category-Default-Ordering.png)

Here, the `Gender` property added in the class at `first` and categorized under the `Identity` category. Then the `Identity` category ordered as `first`. After that, `Country` property added in the class from another category, So `Address` category ordered as `second` and vice versa.

N> If you use both `Ordering` and `Sorting`, `Sorting` have higher priority. So the properties are arranged either `Ascending` or `Descending` order according to the sorting value.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Grouping-Sorting-Ordering) to download the sample that showcases the property ordering support using the attributes.

## Change Property order at runtime

We can set the property order without using the attributes and can change the property order at runtime by handling the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html)  event with [AutoGeneratingPropertyGridItemEventArgs.Order](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.AutoGeneratingPropertyGridItemEventArgs.html#Syncfusion_Windows_PropertyGrid_AutoGeneratingPropertyGridItemEventArgs_Order) property.

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
                         SortDirection="{x:Null}"
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
propertyGrid1.SortDirection = null;
propertyGrid1.AutoGeneratingPropertyGridItem += PropertyGrid1_AutoGeneratingPropertyGridItem;

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight C# %}

private void PropertyGrid1_AutoGeneratingPropertyGridItem(object sender, AutoGeneratingPropertyGridItemEventArgs e) {
    //Experience, DOB, Name and ID  properties ordered by the Order property.
    if (e.DisplayName == "Experience") {
        e.Order = 3;
    }
    else if (e.DisplayName == "DOB") {
        e.Order = 2;
    }
    else if (e.DisplayName == "Name") {
        e.Order = 0;
    }
    else if (e.DisplayName == "ID") {
        e.Order = 1;
    }
}

{% endhighlight %} 
{% endtabs %}

![Properties are ordered based on the value specified in the Order property of the AutoGeneratingPropertyGridItem event](Sorting-Images\Ordering-Event.png)

Here, the `Name` property is arranged at `first` and `Experience` property arranged at `fourth` position based on the value specified in the `AutoGeneratingPropertyGridItemArgs.Order` property.

Click [here](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/AutoGeneratingPropertyGridItem%20event) to download the sample that showcases the property `Description` support using `AutoGeneratingPropertyGridItem` event.
