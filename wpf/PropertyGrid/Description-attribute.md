---
layout: post
title: Attributes support in Syncfusion WPF PropertyGrid
description: This section explains how to control PropertyGrid features using different attributes supported by it.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Description of PropertyItem

Description about the property will be displayed in the Description panel. Visibility of panel can be handled by the `DescriptionPanelVisibility` property of PropertyGrid. By default it is false. User should enable this property to display the description of the property. Height of the description panel can be handled by `DescriptionPanelHeight` property.

## Description Attribute

Description about the property can be specified using [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.descriptionattribute?view=netframework-4.8) attribute. The following code and screenshot illustrates the same,

{% tabs %}

{% highlight C# %}

        [Description("ID of the employee")]
        public string ID
        {
            get;

            set;
        }


        [Description("Birth date of the employee")]
        public DateTime DOB
        {
            get;

            set;
        }
{% endhighlight %}  

{% endtabs %} 

![Description specified in the Description attribute is displayed in Description panel](Attribute-Images\Description-Attribute.png)

## Display attribute with Description

Description about the property has been specified in the [Description](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.description?view=netframework-4.8) field of Display attribute. If the Description attribute is not specified then the value specified in the `Description` field of Display attribute will be displayed as Description of the property. The following code and screenshot illustrates the same,

{% tabs %}

{% highlight C# %}

        [Display(Description = "ID of the employee")]
        public string ID
        {
            get;

            set;
        }


        [Display(Description = "Birth date of the employee")]
        public DateTime DOB
        {
            get;

            set;
        }
        
{% endhighlight %}  

{% endtabs %} 


![Description specified in the Description attribute is displayed in Description panel](Attribute-Images\Description-Attribute.png)