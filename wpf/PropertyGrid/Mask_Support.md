---
layout: post
title: Restrict user input in WPF PropertyGrid control | Syncfusion
description: This section explains how the Restrict user input of the property item has been customized through attributes and editors.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Restrict user input in WPF PropertyGrid

You can now restrict the user input for the property items by using the attributes and mask editor in the [PropertyGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid.html).

N> Add the following assembly references to use the mask attribute and mask editor

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

## Restrict user input using attributes

You can restrict the user to enter particular character or value for the one or more specific property item by setting the `Regex` based mask to the `MaskAttribute` property.

N> You must create the property as either `Object` or `string` type to use mask attribute.

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

