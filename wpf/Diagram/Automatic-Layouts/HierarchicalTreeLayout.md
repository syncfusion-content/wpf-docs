---
layout: post
title: Hierarchical tree layout in WPF Diagram control | Syncfusion
description: Learn here all about Hierarchical tree layout support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Hierarchical tree layout in WPF Diagram (SfDiagram)

The hierarchical tree Layout arranges nodes in a tree-like structure, where the nodes in the hierarchical layout may have multiple parents. There is no need to specify the layout root.

To arrange the nodes in hierarchical structure, specify the [LayoutType](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Layout.DirectedTreeLayout.html#Syncfusion_UI_Xaml_Diagram_Layout_DirectedTreeLayout_Type) as hierarchical tree.

{% tabs %}
{% highlight xaml %}

<!-- Initializes the employee collection-->
<local:Employees x:Key="employees">
    <local:Employee EmpId = "1" ParentId="" Name="Plant Manager" _Color = "#034d6d"/>
    <local:Employee EmpId = "2" ParentId = "1" Name = "Production Manager" _Color = "#1b80c6"/>
    <local:Employee EmpId = "3" ParentId = "1" Name = "Administrative Officer" _Color = "#1b80c6"/>
    <local:Employee EmpId = "4" ParentId = "1" Name = "Maintenance Manager" _Color = "#1b80c6"/>
    <local:Employee EmpId = "5" ParentId = "2" Name = "Control Room" _Color = "#3dbfc9"/>
    <local:Employee EmpId = "6" ParentId = "2" Name = "Plant Operator" _Color = "#3dbfc9"/>
    <local:Employee EmpId = "7" ParentId = "4" Name = "Electrical Supervisor" _Color = "#3dbfc9"/>
    <local:Employee EmpId = "8" ParentId = "4" Name = "Mechanical Supervisor" _Color = "#3dbfc9"/>
    <local:Employee EmpId = "9" ParentId = "5" Name = "Foreman" _Color = "#2bb28e"/>
    <local:Employee EmpId = "10" ParentId = "6" Name = "Foreman" _Color = "#2bb28e"/>
    <local:Employee EmpId = "11" ParentId = "7" Name = "Craft Personnel" _Color = "#2bb28e"/>
    <local:Employee EmpId = "12" ParentId = "7" Name = "Craft Personnel" _Color = "#2bb28e"/>
    <local:Employee EmpId = "13" ParentId = "8" Name = "Craft Personnel" _Color = "#2bb28e"/>
    <local:Employee EmpId = "14" ParentId = "8" Name = "Craft Personnel" _Color = "#2bb28e"/>
    <local:Employee EmpId = "15" ParentId = "9" Name = "Craft Personnel" _Color = "#76d13b"/>
    <local:Employee EmpId = "16" ParentId = "9" Name = "Craft Personnel" _Color = "#76d13b"/>
    <local:Employee EmpId = "17" ParentId = "10" Name = "Craft Personnel" _Color = "#76d13b"/>
</local:Employees>

<!--Initializes the DataSourceSettings -->
<syncfusion:DataSourceSettings x:Key="DataSourceSettings" Id="EmpId" 
                               ParentId="ParentId"
                               DataSource="{StaticResource employees}" />
<!--Initialize the Layout-->
<syncfusion:DirectedTreeLayout x:Name="DirectedTreeLayout" 
                               x:Key="treeLayout" 
                               HorizontalSpacing="30" 
                               VerticalSpacing="50" 
                               Orientation="TopToBottom" 
                               Type="Hierarchical" 
                               SpaceBetweenSubTrees="20" />
<!--Initialize the Layout Manager-->
<syncfusion:LayoutManager x:Key="layoutManager" 
                          Layout="{StaticResource treeLayout}"/>
{% endhighlight %}
{% highlight c# %}
//Initializes the employee collection
Employees employee = new Employees();
employee.Add(new Employee() { EmpId = "1", ParentId = "", Name = "Plant Manager", _Color = "#034d6d" });
employee.Add(new Employee() { EmpId = "2", ParentId = "1", Name = "Production Manager", _Color = "#1b80c6" });
employee.Add(new Employee() { EmpId = "3", ParentId = "1", Name = "Administrative Officer", _Color = "#1b80c6" });
employee.Add(new Employee() { EmpId = "4", ParentId = "1", Name = "Maintenance Manager", _Color = "#1b80c6" });
employee.Add(new Employee() { EmpId = "5", ParentId = "2", Name = "Control Room", _Color = "#3dbfc9" });
employee.Add(new Employee() { EmpId = "6", ParentId = "2", Name = "Plant Operator", _Color = "#3dbfc9" });
employee.Add(new Employee() { EmpId = "7", ParentId = "4", Name = "Electrical Supervisor", _Color = "#3dbfc9" });
employee.Add(new Employee() { EmpId = "8", ParentId = "4", Name = "Mechanical Supervisor", _Color = "#3dbfc9" });
employee.Add(new Employee() { EmpId = "9", ParentId = "5", Name = "Foreman", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "10", ParentId = "6", Name = "Foreman", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "11", ParentId = "7", Name = "Craft Personnel", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "12", ParentId = "7", Name = "Craft Personnel", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "13", ParentId = "8", Name = "Craft Personnel", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "14", ParentId = "8", Name = "Craft Personnel", _Color = "#2bb28e" });
employee.Add(new Employee() { EmpId = "15", ParentId = "9", Name = "Craft Personnel", _Color = "#76d13b" });
employee.Add(new Employee() { EmpId = "16", ParentId = "9", Name = "Craft Personnel", _Color = "#76d13b" });
employee.Add(new Employee() { EmpId = "17", ParentId = "10", Name = "Craft Personnel", _Color = "#76d13b" });

//Initializes the DataSourceSettings
diagram.DataSourceSettings = new DataSourceSettings()
{
    Id = "EmpId",
    ParentId = "ParentId",
    DataSource = employee,
};

//Initialize the Layout
diagram.LayoutManager = new LayoutManager()
{
    Layout = new DirectedTreeLayout()
    {
        Type = LayoutType.Hierarchical,
        Orientation = TreeOrientation.TopToBottom,
        HorizontalSpacing = 30,
        VerticalSpacing = 50,
    },
                
    RefreshFrequency = RefreshFrequency.ArrangeParsing,
};

{% endhighlight %}
{% endtabs %}

![WPF Diagram with HierarchicalLayout](Automatic-Layouts_images/wpf-diagram-hierarchical-layout.png)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Automatic%20Layout/Hierarchical%20Tree)
