---
layout: post
title: Property DisplayName in WPF PropertyGrid | Syncfusion
description: This section explains how the display name of the property item has been customized through attributes.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Display name of the PropertyItem

This sections explains about how the name of the property item works based on Name and DisplayName attributes. 

## DisplayName Attribute

User can provide a meaningful name in PropertyGrid instead of property name using [DisplayName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.displaynameattribute?view=netframework-4.8) attribute. Here, the property `ID` and `DOB` will be displayed as `Employee ID` and `Date of Birth` respectively. 

{% tabs %}

{% highlight C# %}

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
       
        public Gender Gender
        {
            get;

            set;
        }
        
{% endhighlight %} 

{% endtabs %} 

![Name specified in the DisplayName attribute is displayed as Name of the property](Attribute-Images\DisplayName-Attribute.png)

## Display attribute with Name

Based on the name specified in the [Name](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.name?view=netframework-4.8) field of Display attribute, properties will be displayed in the PropertyGrid. Here, the property `ID` and `DOB` will be displayed as `Employee ID` and `Date of Birth` respectively. If the `DisplayName` attribute is not specified then the value specified in the `Name` field will be displayed as property name.

{% tabs %}

{% highlight C# %}

        [Display(Name = "Employee ID")]
        public string ID
        {
            get;

            set;
        }

        [Display(Name = "Date of Birth")]
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

{% endhighlight %} 

{% endtabs %} 

![Name specified in the Display attribute is displayed as Name of the property](Attribute-Images\DisplayName-Attribute.png)

Refer to this [`sample`](https://github.com/SyncfusionExamples/How-to-set-desired-name-to-the-property-items-of-WPF-PropertyGrid-through-attributes) to know how the display name of the property item has been customized through attributes.