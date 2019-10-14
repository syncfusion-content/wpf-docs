---
layout: post
title: Grouping and Sorting | custom order | PropertyGrid  | wpf | Syncfusion
description: This section explains about how the property item can be grouped and sorted based on the SortDirection of property grid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Grouping and Sorting

This section explains about how the property items can be grouped or sorted in PropertyGrid. Property items will be sorted based on the [SortDirection](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~SortDirection.html) property of PropertyGrid.

## Grouping items based on attribute

[EnableGrouping](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~EnableGrouping.html) property decides whether the items of property grid can be grouped or sorted. If the SortButton is clicked, the property EnableGrouping will be false and it will be true when GroupButton is clicked. If the property is true, propertyGrid groups the property items based on Category Attribute and Display Attribute's GroupName field of the property. 

### Category Attribute

Property items will be grouped based on the name specified in the [CategoryAttribute](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.categoryattribute?view=netframework-4.8). If the property item doesn't have any category name, that property will be grouped under "Misc" category. In following example, Gender property is grouped under "Misc" category.

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

![Properties are grouped based on the value specified in the Category attribute](Grouping-and-sorting Images\Category-Attribute.png)

### Display attribute with GroupName

Property items will be grouped based on the name specified in the [GroupName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.groupname?view=netframework-4.8) field of DisplayAttribute. If the `Category` attribute is not specified in the property then the property items will be grouped with the name specified in the `GroupName` field. 

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

![Properties are grouped based on the value specified in the Display attribute](Grouping-and-sorting Images\Category-Attribute.png)   

Refer to this [`sample`](https://github.com/SyncfusionExamples/Filtering-the-property-items-of-PropertyGrid-through-attributes) to know how the property items are Categorized through attributes.

## Grouping and sorting through SortDirection

Values of `SortDirection` property is `Ascending`, `Descending` and `None`. Details about the property functionality is available here,

### Ascending and Descending 

Property items of property grid will be sorted in Ascending or Descending order based on `Name` of the property, not by `DisplayName` of the property item. If the property items are grouped, the grouped items will be sorted based on Category name of the items.

### Custom Order

If the `SortDirection` is null and the properties doesn't have any custom order then the properties will be arranged based on the order they were added in the property items collection of PropertyGrid. Otherwise, the properties will be arranged based on the order specified in each property of the DisplayAttribute.

#### Display attribute with Order

The property items of PropertyGrid will be ordered based on the value specified in the [Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8) field of Display attribute. If more than one property has same `Order` value, then the properties with distinct numbers will be added first then the duplicate order properties will be added. Also, if any of the property doesn't have order, that properties will be arranged based on the order they were added in the property items collection of PropertyGrid. 

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

![Properties are arranged based on custom order](Grouping-and-sorting Images\Custom-Order.png)  

Refer to this [`sample`](https://github.com/SyncfusionExamples/sorting-the-property-items-of-wpf-propertygrid) to know how the property items are ordered based on SortDirection property.

### Properties

Grouping and Sorting Table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
EnableGrouping</td><td>
Groups between the group mode and the sort mode.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
SortDirection</td><td>
Gets or sets the SortDirection for the PropertyGrid control.</td><td>
DependencyProperty</td><td>
Nullable ListSortDirection</td><td>
</td></tr>
</table>

#### Sample link

1. Select Start -> Programs -> Syncfusion -> Essential Studio xx.x.x.xx -> Dashboard.
2. Select   Run Locally Installed Samples in WPF Button.
3. Now expand the PropertyGrid treeview item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 

## Toggling Category group

Category can be collapsed or expanded by clicking the expander which is near to category name. Or using [CollapseCategory](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~CollapseCategory.html) and [ExpandCategory](https://help.syncfusion.com/cr/wpf/Syncfusion.PropertyGrid.Wpf~Syncfusion.Windows.PropertyGrid.PropertyGrid~ExpandCategory.html) methods, category groups can be collapsed or expanded programmatically. These methods will accept category name as argument.

{% tabs %}

{% highlight C# %}

      this.pgrid.CollapseCategory("Itentity");

{% endhighlight %}  

{% endtabs %}

![Itentity group has been collapsed](Grouping-and-sorting Images/Collapse-Category.png)

{% tabs %}

{% highlight C# %}

      this.pgrid.ExpandCategory("Itentity");

{% endhighlight %}  

{% endtabs %}

![Collapsed Itentity group has been expanded](Grouping-and-sorting Images/Expand-Category.png)