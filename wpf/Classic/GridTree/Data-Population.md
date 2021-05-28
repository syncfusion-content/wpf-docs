---
layout: post
title: Data Population in WPF Wizard Control control | Syncfusion
description: Learn here all about Data Population support in Syncfusion WPF GridTreeControl (Classic) control and more.
platform: wpf
control: GridTree 
documentation: ug
---

# Data Population in WPF GridTreeControl (Classic)

The primary requirement of the data displayed in the GridTree control is that the parent node and the child node share the same schema (i.e. have the same columns to display). To populate the GridTree control, you need to handle the RequestTreeItems event (This event gets fired for every tree node that is being populated in order to retrieve its child nodes). In the event arguments, the ParentItem property indicates the item whose children are being requested. The list of children can be set using this property. If this property is empty, it implies that the event is requesting the root nodes. The following code example illustrates a minimal RequestTreeItems handler.

{% highlight c# %}





private void treeGrid_RequestTreeItems(object sender, GridTreeRequestTreeItemsEventArgs args)

{

    // When the ParentItem is null, you need to set args.ChildList to be the root items.

    if (args.ParentItem == null)

    {

        // Get the root list - get all employees who have no boss.

        args.ChildList = employees.GetReportees(-1); //get all whose boss's id is -1 (no boss)

    }

    // If ParentItem not null, set args.ChildList to the child items for the given Parent.

    else 

    {   

        // Get the children of the parent object.

        Employee emp = args.ParentItem as Employee;

        if (emp != null)

        {

            // Get all employees that report to the parent employee.

            args.ChildList = employees.GetReportees(emp.ID);

        }

    }

}

{% endhighlight %}

The only requirement on ChildList returned by the RequestTreeItems is that it should be an IEnumerable list of typed objects that share a single type.

## Order and Visibility of Columns in the GridTree Control

The default behavior of the GridTree control is to display all simple, public properties exposed in the items provided through the RequestTreeItems event (Here, properties indicate Data Source properties, which are represented as columns in the Grid control. For eg, in Customers table, CustomerID, CompanyName, etc. are termed as properties). To control the visibility and the order of the columns that appear in the Grid Tree, you can use the GridTreeControl.Columns collection of GridTreeColumn object. The order of the GridTreeColumn objects in the Columns collection determines the display order of the columns in the Grid Tree.  

* Each GridTreeColumn contains the following five properties: MappingName-The name of the property from the tree item that is bound with this column
* HeaderText-The HeaderText property sets the text for header cell of this column. If HeaderText is empty, then the MappingName will be used as the column header text.
* Width-Specifies width of this column in pixels.

The following code example illustrates how to set these properties for the GridTreeColumns by using XAML code.

{% highlight xaml %}



<sf:GridTreeControl Name="treeGrid" RequestTreeItems="treeGrid_RequestTreeItems" >

    <sf:GridTreeControl.Columns>

        <sf:GridTreeColumn MappingName="FirstName" HeaderText="First Name"/>

        <sf:GridTreeColumn MappingName="LastName" HeaderText="Last Name"/>

        <sf:GridTreeColumn MappingName="Salary" />

        <sf:GridTreeColumn MappingName="Rating" />

    </sf:GridTreeControl.Columns>

</sf:GridTreeControl>


{% endhighlight %}

* PercentWidth-This is another width property that plays a role in column sizing, if you had set GridTreeControl.PercentSizingBehavior(The PercentSizingBehavior determines how the grid columns should be sized when the grid is resized) to some value other than 'None'. If you set a value to the PercentWidth property, this column will be resized according to the sizing algorithms. For more details refer the PercentSizingBehavior section.
* StyleInfo-StyleInfo is a GridStyleInfo object that controls the appearance of the cells in this column. This object enables you to set various column properties, including the Font, and Background and Foreground color. All properties exposed in the GridStyleInfo objects are customizable by using this StyleInfo property.



