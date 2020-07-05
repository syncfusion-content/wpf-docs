---
layout: post
title: Restrict user input in WPF PropertyGrid control | Syncfusion
description: This section explains how the Restrict user input of the property item has been customized through attributes and editors.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Restrict user input in WPF PropertyGrid

 You can restrict the user from providing invalid input using MaskAttribute, for example emails, phone numbers, zip codes, currency, etc.

# Restrict user input using built-in editor

 The [PropertyGrid](https://www.syncfusion.com/wpf-ui-controls/propertygrid) control supports several built-in editors. Based on the property type, the built-in editors automatically assigned as value editor for the properties and its allow the valid inputs based on property type.

<table>
<th> S.No </th>
<th> Property Type </th>
<th> Default Editor </th>
<tr>
<td>1</td>
<td>int</td>
<td>IntegerTextBox</td>
</tr>
<tr>
<td>2</td>
<td>double</td>
<td>DoubleTextBox</td>
</tr>
<tr>
<td>3</td>
<td>string</td>
<td>TextBox</td>
</tr>
<tr>
<td>4</td>
<td>enum</td>
<td>ComboBox</td>
</tr>
<tr>
<td>5</td>
<td>DateTime</td>
<td>DateTimeEdit</td>
</tr>
<tr>
<td>6</td>
<td>bool</td>
<td>CheckBox</td>
</tr>
<tr>
<td>7</td>
<td>Brush</td>
<td>ColorPicker</td>
</tr>
</table>

{% tabs %}
{% highlight C# %}

// Employee class to be explored in property grid.
public class Employee {
    public string EmployeeName { get; set; }
    public string ID { get; set; }
    public int Age { get; set; }
    public int Experiance { get; set; }
}

public class ViewModel {
    public object SelectedEmployee { get; set; }
    public ViewModel() {
        SelectedEmployee = new Employee() 
        {
            EmployeeName = "Johnson",
            Age = 25,
            ID = "1234",
            Experiance =3
        };
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid SelectedObject="{Binding SelectedEmployee}"
                         Name="propertyGrid1" >
    <syncfusion:PropertyGrid.DataContext>
        <local:ViewModel></local:ViewModel>
    </syncfusion:PropertyGrid.DataContext>
</syncfusion:PropertyGrid>

{% endhighlight %}
{% highlight c# %}

PropertyGrid propertyGrid1 = new PropertyGrid();
propertyGrid1.DataContext = new ViewModel();
propertyGrid1.SetBinding(PropertyGrid.SelectedObjectProperty, new Binding("SelectedEmployee"));

{% endhighlight %}
{% endtabs %}

![Restrict user input using built-in editor in the PropertyGrid control](Getting-Started_images/Binding-with-any-object_img1.png)

 Here, `Age`, `Experiance` and `ID` properties is a `int` type properties, they allow only the whole number inputs. `EmployeeName` is a string type property, so `TextBox` is assigned as a value editor and all the text will be allowed.

## Restrict user input using attributes

You can restrict the user to enter particular character or value for the one or more specific property item by setting the `Regex` based mask to the `MaskAttribute` property.

N> You can apply mask attribute to property of type Object or string only.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.PropertyGrid;

//Setting mask option for two specific properties
[MaskAttribute("[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}", "Email_1,Email_2")]
public class Person {
    public Person() {
        Name = "Carl Johnson";
        Age = 3;
        Mobile = "2054449786";
        Email_1 = "carljohnson@gta.com";
        Email_2 = "johnson@gta.c";
    }

    public string Name { get; set; }
    public string Email_1 { get; set; }
    public object Email_2 { get; set; }

    //Setting mask option for Mobile property
    [MaskAttribute(@"\(\d{3}\) \d{3} - \d{4}")]
    public string Mobile { get; set; }

    //Setting mask option for Age properties
    [MaskAttribute(@"\d{2}")]
    public object Age { get; set; }
}
      
{% endhighlight %}
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid  x:Name="propertyGrid">
    <syncfusion:PropertyGrid.SelectedObject>
        <local:Person/>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% endtabs %}

![Restrict user input using attributes](Attribute-Images\MaskAttributes.png)

Here, the partial and wrong inputs are highlighted by the red color border.

N> View [Sample](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Mask_Attributes) in GitHub

## Restrict user input using custom mask editor

You can restrict the user to enter particular character or value for the one or more specific property item by using the `Regex` based mask to the custom editor's `Mask` property which is derived from the `MaskEditor`.

N> You must create the property as either `Object` or `string` type to use mask editor.

N> Please refer the [Custom Editor](https://help.syncfusion.com/wpf/propertygrid/customeditor-support) page to know more about how to set the custom editor for the property items.
   
{% tabs %}
{% highlight C# %}

using System.ComponentModel;
using Syncfusion.Windows.PropertyGrid;

//Custom mask editor
public class EmailEditor : MaskEditor {
    public EmailEditor() {
        Mask = "[A-Za-z0-9._%-]+@[A-Za-z0-9]+.[A-Za-z]{2,3}"
    }
}

//Custom mask editor
public class MobileNoEditor : MaskEditor {
    public MobileNoEditor() {
        Mask = @"\(\d{3}\) \d{3} - \d{4}";
    }
}

//Setting custom mask editors for the properties
[Editor("Email_1, Email_2", typeof(EmailEditor))]
[Editor("Mobile", typeof(MobileNoEditor))]
public class Person {
    public Person() {
        Name = "Carl Johnson";
        Age = 3;
        Mobile = "2054449";
        Email_1 = "carljohnson@gta.c";
        Email_2 = "johnson@gta.com";
    } 

    public string Name { get; set; }
    public string Email_1 { get; set; }
    public object Email_2 { get; set; }
    public string Mobile { get; set; }
    public object Age { get; set; }
}

{% endhighlight %} 
{% endtabs %} 

{% tabs %}
{% highlight xaml %}

<syncfusion:PropertyGrid  x:Name="propertyGrid">
    <syncfusion:PropertyGrid.SelectedObject>
        <local:Person/>
    </syncfusion:PropertyGrid.SelectedObject>
</syncfusion:PropertyGrid>

{% endhighlight %} 
{% endtabs %} 

![Restrict user input using custom mask editor](Attribute-Images\MaskEditor.png)

Here, the partial and wrong inputs are highlighted by the red color border.

N> View [Sample](https://github.com/SyncfusionExamples/wpf-property-grid-examples/tree/master/Samples/Mask_Editors) in GitHub

