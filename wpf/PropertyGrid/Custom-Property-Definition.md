---
layout: post
title: Custom Property Definition in WPF PropertyGrid control | Syncfusion
description: This section explains how to customize the property definition of the property item in PropertyGrid control.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Custom definition of the properties in WPF PropertyGrid

By default, property items of `PropertyGrid.SelectedObject` are automatically generated in the [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control by using the [AutoGeneratingPropertyGridItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PropertyGrid.PropertyGrid.html#Syncfusion_Windows_PropertyGrid_PropertyGrid_AutoGeneratingPropertyGridItem) event. Now, you can restrict the auto generated items and manually define a property items through the `XAML` by using the `PropertyGridItem`.

N> Manual definition of property item by using `PropertyGridItem` have higher priority than property definition from attributes and `AutoGeneratingPropertyGridItem` event.

## Define PropertyItem manually 

You can manually define the property item by set the value to its properties and add that item into the `Items` collection property. You can enable it only by setting the `AutoGenerateItems` property value as `false`. The default value of `AutoGenerateItems` property is `true`.

N> If `AutoGenerateItems` property is `false`, then only the items which are added in the `Items` collection will generated in the `PropertyGrid`.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public enum Gender {
    Male,
    Female
}

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public Gender Gender { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Gender = Gender.Male
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGenerateItems="False"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
    <syncfusion:PropertyGrid.Items>
        <syncfusion:PropertyGridItem PropertyName="Name"/>
        <syncfusion:PropertyGridItem PropertyName="DOB"/>
    </syncfusion:PropertyGrid.Items>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

propertyGrid1.AutoGenerateItems = false;

propertyGrid1.Items.Add(new PropertyGridItem() { PropertyName = "Name" });
propertyGrid1.Items.Add(new PropertyGridItem() { PropertyName = "DOB" });

{% endhighlight %} 
{% endtabs %}

![PropertyGridItem added manually](Property_definition_images\AddingItems.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Custom-PropertyDefinition)

## Add or remove PropertyItem at runtime

You can manually add or remove the property item at runtime by adding or removing that item from the `Items` collection property. You can also clear all the property items from the `PropertyGrid`.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public enum Gender {
    Male,
    Female
}

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public Gender Gender { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Gender = Gender.Male
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGenerateItems="False"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
    <syncfusion:PropertyGrid.Items>
        <syncfusion:PropertyGridItem PropertyName="Name"/>
        <syncfusion:PropertyGridItem PropertyName="DOB"/>
    </syncfusion:PropertyGrid.Items>
</syncfusion:PropertyGrid>

<StackPanel>
    <Button Name="addItems"
            Click="AddItems_Click"
            Content="Add Items"></Button>
    <Button x:Name="removeItems"
            Click="RemoveItems_Click"
            Content="Remove Items"></Button>
    <Button Name="clearItems"
            Click="ClearItems_Click"
            Content="Clear Items"></Button>
</StackPanel>

{% endhighlight %} 
{% highlight C# %}

propertyGrid1.AutoGenerateItems = false;

propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "Name"
});
propertyGrid1.Items.Add(new PropertyGridItem() 
{
    PropertyName = "DOB"
});

addItems.Click += AddItems_Click;
removeItems.Click += RemoveItems_Click;
clearItems.Click += ClearItems_Click;

{% endhighlight %} 
{% endtabs %}

You can dynamically add the property item as follows,

{% tabs %}
{% highlight C# %}

private void AddItem_Click(object sender, RoutedEventArgs e) {
    propertyGrid1.Items.Add(new PropertyGridItem()
    {
        PropertyName = "Gender"
    });
}

private void RemoveItems_Click(object sender, RoutedEventArgs e) {
    propertyGrid1.Items.RemoveAt(1);
}

private void ClearItems_Click(object sender, RoutedEventArgs e) {
    propertyGrid1.Items.Clear();
}

{% endhighlight %} 
{% endtabs %}

![PropertyGridItem adding and removing at runtime](Property_definition_images\Dynamic.gif)

## Manually define the PropertyItem

You can manually define the display name, description, category, nested mode, readonly state and value editor for any property items.

* `PropertyGridItem.DisplayName` - To manually define the display name for the property items.

* `PropertyGridItem.Description`- To manually define the description for the property items.

* `PropertyGridItem.CategoryName` - To manually define the category for the property items.

* `PropertyGridItem.IsReadOnly` - To manually define the readonly state for the property items.

* `PropertyGridItem.Editor` - To manually define the own value editor for the property items.

* `PropertyGridItem.NestedPropertyDisplayMode` - To manually define the nested mode of the property items.

* `PropertyGridItem.Visibility` - To manually define the visibility for the property items.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Custom-PropertyDefinition)

## Manually add own value editor and categorize the properties

If you want to add own value editor and categorize the property items manually, use the `PropertyGridItem.Editor` and `PropertyGridItem.CategoryName` properties to the required property items.

N> You can refer [Create Custom Value Editor](https://help.syncfusion.com/wpf/propertygrid/customeditor-support#creating-the-custom-editor) page to know more about how to create a own value editors.

{% tabs %}
{% highlight C# %}

using System;
using System.ComponentModel;
using System.ComponentModel.DataAnnotations;

public class EmailEditor : MaskEditor {
    public EmailEditor() {
        Mask = @"[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}";
    }
}

public enum Gender {
    Male,
    Female
}

public class Employee {
    public string Name { get; set; }
    public string ID { get; set; }
    public DateTime DOB { get; set; }
    public Gender Gender { get; set; }
    public string EmailID { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            Name = "John",
            ID = "381",
            DOB = new DateTime(1995, 12, 24),
            Gender = Gender.Male,
            EmailID = "john@123.c"
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGenerateItems="False" 
                         EnableGrouping="True"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
    <syncfusion:PropertyGrid.Items>
        <syncfusion:PropertyGridItem PropertyName="Name" 
                                     CategoryName="Basic Info"/>
        <syncfusion:PropertyGridItem PropertyName="ID" 
                                     CategoryName="Basic Info"/>
        <syncfusion:PropertyGridItem PropertyName="DOB"
                                     CategoryName="Basic Info"/>
        <syncfusion:PropertyGridItem PropertyName="Gender" 
                                     CategoryName="Additional Info"/>
        <syncfusion:PropertyGridItem PropertyName="EmailID" 
                                     CategoryName="Additional Info">
            <!--Adding own value editor for the EmailID property-->
            <syncfusion:PropertyGridItem.Editor>
                <local:EmailEditor/>
            </syncfusion:PropertyGridItem.Editor>
        </syncfusion:PropertyGridItem>
    </syncfusion:PropertyGrid.Items>

</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

propertyGrid1.AutoGenerateItems = false;
propertyGrid1.EnableGrouping = true;

propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "Name",
    CategoryName = "Basic Info" 
});
propertyGrid1.Items.Add(new PropertyGridItem() 
{
    PropertyName = "ID", 
    CategoryName = "Birth date of the employee" 
});
propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "DOB",
    CategoryName = "Basic Info" 
});
propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "Gender",
    CategoryName = "Additional Info" 
});
propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "EmailID",
    CategoryName = "Additional Info" 
});
{% endhighlight %} 
{% endtabs %}

![PropertyGridItem category and value editor changed](Property_definition_images\Ediotor_Category.png)

Here, the masked textbox with email-id mask is assigned as a value editor for the `EmailID` property and properties are categorized under `Basic Info` and `Additional Info`.

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Custom-PropertyDefinition)

## Manually define nested properties for PropertyItem

If you want to manually explore only particular nested properties of any property item, add that particular nested properties into the respective property item's `PropertyGridItem.Items` collection. You must enable nested property mode by using `PropertyGridItem.PropertyExpandMode` property value as `NestedMode` to explore the nested properties. The default value of `PropertyGridItem.PropertyExpandMode` property is `null`.

{% tabs %}
{% highlight C# %}

public class Bank {
    public string BankName { get; set; }
    public int CustomerID { get; set; }
    public long AccountNumber { get; set; }
    public override string ToString() {
        return BankName;
    }
}

public class Employee {
    public string ID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public Bank Bank { get; set; }        
    public DateTime DOB { get; set; }
}

public class ViewModel {
    public Object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee()
        {
            DOB = new DateTime(1995, 01, 31),
            Name = "Johnson",
            ID = "895",
            Age = 25,
            Bank = new Bank()
            {
                AccountNumber = 123456789,
                CustomerID = 356,
                BankName = "ABC Bank"
            },
        };
    }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid AutoGenerateItems="False" 
                         PropertyExpandMode="NestedMode"
                         SelectedObject="{Binding SelectedEmployee}"
                         x:Name="propertyGrid1">
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
    <syncfusion:PropertyGrid.Items>
        <syncfusion:PropertyGridItem PropertyName="Name"/>
        <syncfusion:PropertyGridItem PropertyName="ID"/>
        <syncfusion:PropertyGridItem PropertyName="DOB"
                                     NestedPropertyDisplayMode="Show">
            <syncfusion:PropertyGridItem.Items>
                <syncfusion:PropertyGridItem PropertyName="Day"/>
                <syncfusion:PropertyGridItem PropertyName="Month"/>
                <syncfusion:PropertyGridItem PropertyName="Year"/>
            </syncfusion:PropertyGridItem.Items>
        </syncfusion:PropertyGridItem>
    </syncfusion:PropertyGrid.Items>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% highlight C# %}

propertyGrid1.AutoGenerateItems = false;
propertyGrid1.PropertyExpandMode = PropertyExpandModes.NestedMode;

propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "Name"
});
propertyGrid1.Items.Add(new PropertyGridItem() 
{
    PropertyName = "ID"
});

ObservableCollection<PropertyGridItem> DOB_Items = new 
    ObservableCollection<PropertyGridItem>();
DOB_Items.Add(new PropertyGridItem() { PropertyName = "Day" });
DOB_Items.Add(new PropertyGridItem() { PropertyName = "Month" });
DOB_Items.Add(new PropertyGridItem() { PropertyName = "Year" });

propertyGrid1.Items.Add(new PropertyGridItem()
{
    PropertyName = "DOB",
    Items = DOB_Items
});

{% endhighlight %} 
{% endtabs %}

![PropertyGrid displays particular nested properties](Property_definition_images\Dynamic_NestedProperty.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Custom-PropertyDefinition)

