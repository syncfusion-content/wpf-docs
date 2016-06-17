---
layout: post
title: Populate Diagram from external data sources.
description: How to populate the Diagram from the local data?
platform: wpf
control: SfDiagram
documentation: ug
---

#DataSource

SfDiagram is populated with the Node taken from an external hierarchical data source. SfDiagram exposes its specific, data-related properties and allows you to specify the data source fields where the node information is retrieved from.

##DataSource Settings

Two mapping fields are necessary to map a hierarchical datasource with the diagram. Id property is used for unique identification of a record. ParentId property is used to identify the parent object to which a particular object is connected.

| Properties | Description | Value |
|---|---|---|
| DataSource | Data source based on the diagram that is to be generated. | Object |
| ParentId | Specifies the mapping parent id property of the data source items. | String |
| Id | Specified the mapping unique id property of data source items. | String |
| Root | Specifies the root element of the data source items. | String |

###DataSource

The following code example illustrates how to bind data to SfDiagram.

{% highlight xaml %}

<!-- Initializes the employee colletion-->
<local:Employees x:Key="employees">
    <local:Employee Name="Steve" EmpId="1" ParentId="" Designation="CEO"/>
    <local:Employee Name="Kevin" EmpId="2" ParentId="1" Designation="Manager"/>
    <local:Employee Name="John" EmpId="3" ParentId="1" Designation="Manager"/>
    <local:Employee Name="Raj" EmpId="4" ParentId="2" Designation="Team Lead"/>
    <local:Employee Name="Will" EmpId="5" ParentId="2" Designation="S/w Developer"/>
    <local:Employee Name="Sarah" EmpId="6" ParentId="3" Designation="TeamLead"/>
    <local:Employee Name="Mike" EmpId="7" ParentId="3" Designation="Testing Engineer"/>
</local:Employees>

<!--Initializes the DataSourceSettings -->
<syncfusion:DataSourceSettings x:Key="DataSourceSettings" DataSource="{StaticResource employees}"
                               ParentId="ParentId" Id="EmpId" Root="1"/>
               
<!--Initializes the Layout-->                
<syncfusion:DirectedTreeLayout x:Key="treeLayout" HorizontalSpacing="80" VerticalSpacing="50" 
                               SpaceBetweenSubTrees="20" Orientation="TopToBottom"/>
<syncfusion:LayoutManager x:Key="layoutManager" Layout="{StaticResource treeLayout}"/>                               
         
<!--Initializes the SfDiagram-->          
<syncfusion:SfDiagram x:Name="diagram" LayoutManager="{StaticResource layoutManager}"                           
                      DataSourceSettings="{StaticResource DataSourceSettings}">
    <!--Initializes the NodeCollection-->                  
    <syncfusion:SfDiagram.Nodes>
        <syncfusion:NodeCollection/>
    </syncfusion:SfDiagram.Nodes>
    <!--Initializes the ConnectorCollection-->
    <syncfusion:SfDiagram.Connectors>
        <syncfusion:ConnectorCollection/>
    </syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

![](DataSource_images/DataSource_img1.png)

##DataSource Root

During Automatic Layout, Node without parent is treated as Root of the layout. But, now we have provided the option to specify this Root by using the DataSource settings.

The following code illustrates how to specify the root object for the Diagram**.**

{% highlight C# %}

//Object with id “CEO”, is considered as root of tree layout.
diagram.DataSourceSettings.Root = “CEO”;

{% endhighlight %}

![](DataSource_images/DataSource_img2.jpeg)
