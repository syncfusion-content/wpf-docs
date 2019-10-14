---
layout: post
title: ReadyOnly, Editable attributes support in Syncfusion WPF PropertyGrid
description: This section explains how to make the property item readonly using attributes supported by PropertyGrid.
platform: wpf
control: PropertyGrid 
documentation: ug
---

# ReadOnly and Editable Attribute

When the property marked as [ReadOnly](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.readonlyattribute?view=netframework-4.8) or [Editable](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.editableattribute?view=netframework-4.8) as false, property grid does not allow user to edit the property values. In the following code `Password` property is marked as Editable false and `DOB` is marked as ReadOnly.

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

![Password and DOB is not editabled in propertygrid](Attribute-Images\ReadOnly-Editable-Attribute.png)