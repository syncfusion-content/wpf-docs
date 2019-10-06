---
layout: post
title: Attributes support in Syncfusion WPF PropertyGrid
description: This section explains how to control PropertyGrid features using different attributes supported by it.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Supported Attributes

This sections explains about the attributes which are supported in the PropertyGrid. 

## Description Attribute

Description about the property can be specified using `Description` attribute and the description will be displayed in the Description panel only if the `DescriptionPanelVisibility` property is true. The following code and screenshot illustrates the same,

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

![Description specified in the Description attribute is displayed in Description panel](Attribute-Support-Images\Description-Attribute.png)

## Category Attribute

When the property `EnableGrouping` is true, properties will be grouped based on the name specified in the CategoryAttribute. If the property item doesn't have any category name, that property will be grouped under "Misc" category. In following example, Gender property is grouped under "Misc" category.

{% tabs %}

{% highlight C# %}

        [Category("Identity")]
        public string ID
        {
            get;

            set;
        }


        [Category("Identity")]
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


The following illustrates how the properties are grouped based on Category value,

![Properties are grouped based on the value specified in the Category attribute](Attribute-Support-Images\Category-Attribute.png)

## DisplayName Attribute

You can provide a meaningful name in PropertyGrid instead of property name using DisplayName attribute. Here, the property `ID` and `DOB` will be displayed as `Employee ID` and `Date of Birth` respectively. 

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

![Name specified in the DisplayName attribute is displayed as Name of the property](Attribute-Support-Images\DisplayName-Attribute.png)

## Browsable and Bindable Attribute

If the property has Browsable as false or Bindable as false, that properties will not be shown in PropertyGrid. Functionalities of Browsable and Bindable attributes are same. 

{% tabs %}

{% highlight C# %}

        [Browsable(false)]
        public string ID
        {
            get;

            set;
        }


        [Bindable(false)]
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
       
        public Country Country
        {
            get;

            set;
        }
        
{% endhighlight %} 

{% endtabs %} 


The following screenshot illustrates that the ID and DOB properties are not displayed in the property grid.

![ID and DOB is not displayed in propertygrid](Attribute-Support-Images\Bindable-Browsable-Attribute.png)

## ReadOnly and Editable Attribute

When the property marked as ReadOnly or Editable as false, property grid does not allow user to edit the property values. In the following code `Password` property is marked as Editable false and `DOB` is marked as ReadOnly.

{% tabs %}

{% highlight C# %}

        public string ID
        {
            get;

            set;
        }

        [Editable(false)]
        public object Password
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

{% endhighlight %}  

{% endtabs %} 


Here, the  DOB and Password properties are disabled,

![Password and DOB is not editabled in propertygrid](Attribute-Support-Images\ReadOnly-Editable-Attribute.png)        

## Display Attribute

[Display attribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute?view=netframework-4.8) contains several fields for general purpose. System.ComponentModel.DataAnnotations assembly should be added to the project to access this support. This support is available from 4.0 framework. The following fields of DisplayAttribute is supported in PropertyGrid,

## Display attribute with AutoGeneratedField

If a property has the value of ReadOnly attribute is false or Editable attribute as true and the AutoGeneratedField of DisplayAttribute is false then the property item will not be added to the property collection of PropertyGrid and not visible in the UI. Value of AutoGeneratedField has no effect when the property is marked as ReadOnly.

{% tabs %}

{% highlight C# %}

        [Display(Description = "ID of the employee")]
        public string ID
        {
            get;

            set;
        }


        [Display(AutoGenerateField = false)]
        public DateTime DOB
        {
            get;

            set;
        }

        [Browsable(false)]
        [Display(AutoGenerateField = true)]
        public Gender Gender
        {
            get;

            set;
        }
        
        public Country Country
        {
            get;

            set;
        }

{% endhighlight %}  

{% endtabs %} 


The following screenshot illustrates that DOB and Gender properties are not displayed in property grid.

![Gender and DOB is not added in propertygrid](Attribute-Support-Images\AutoGeneratedField.png)  

## Display attribute with GroupName

Property items will be grouped based on the name specified in the `GroupName` field of DisplayAttribute. If the `Category` Attribute is not specified in the property then the property items will be grouped with the name specified in the `GroupName` field. 

{% tabs %}

{% highlight C# %}

        [Display(GroupName = "Identity")]
        public string ID
        {
            get;

            set;
        }


        [Display(GroupName = "Identity")]
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


Here, the `ID` and `DOB` is grouped based on the value specified in GroupName field.

![Properties are grouped based on the value specified in the Display attribute](Attribute-Support-Images\Category-Attribute.png)        

## Display attribute with Order

When the `SortDirection` property has null value, the property items of PropertyGrid will be ordered based on the value specified in the `Order` field of Display attribute. If more than one property has same `Order` value, then the properties with distinct numbers will be added first then the duplicate order properties will be added. Also, if any of the property doesn't have order, that properties will be arranged based on the order they were added in the property items collection of PropertyGrid. 

{% tabs %}

{% highlight C# %}

[Display(Order = 4)]
        public Gender Gender
        {
            get;

            set;
        }

        [Display(Order = 7)]
        public Country Country
        {
            get;

            set;
        }

        [Display(Order = 6)]
        public string Email
        {
            get;

            set;
        }

        [Display(Order = 0)]
        public string FirstName
        {
            get;

            set;
        }

        public string Designation
        {
            get;

            set;
        }
        
        [Display(Order = 1)]
        public string LastName
        {
            get;

            set;
        }

        public string ID
        {
            get;

            set;
        }


        [Display(Order = 4)]
        public DateTime DOB
        {
            get;

            set;
        }


        [Display(Order = 5)]
        public long Mobile
        {
            get;

            set;
        }

        [Display(Order = 2)]
        public int Age
        {
            get;

            set;
        }

        public ImageSource Image
        {
            get;

            set;
        }
        
{% endhighlight %}  

{% endtabs %} 


Here the property `DOB` and `Gender` has same order but the property `Gender` property is added prior than `DOB`. So the Gender property will be arranged in 4th place, and the `DOB` is arranged after `Country` property. And the other non-specified order properties are arranged based on the order they were added to the collection.

![Properties are arranged based on custom order](Attribute-Support-Images\Custom-Order.png)  

## Display attribute with Name

Based on the name specified in the `Name` field of Display attribute, properties will be displayed in the PropertyGrid. Here, the property `ID` and `DOB` will be displayed as `Employee ID` and `Date of Birth` respectively. If the `DisplayName` attribute is not specified then the value specified in the `Name` field will be displayed as property name.

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

![Name specified in the Display attribute is displayed as Name of the property](Attribute-Support-Images\DisplayName-Attribute.png)

## Display attribute with Description

Description about the property has been specified in the `Description` field of Display attribute and the description will be displayed in the Description panel only if the `DescriptionPanelVisibility` property is true. If the Description attribute is not specified then the value specified in the `Description` field of Display attribute will be displayed as Description of the property. The following code and screenshot illustrates the same,

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


![Description specified in the Description attribute is displayed in Description panel](Attribute-Support-Images\Description-Attribute.png)