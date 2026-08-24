---
layout: post
title: Expand Collapse Command in WPF SfDiagram | Syncfusion®
description: Expand or collapse hierarchical nodes in Syncfusion® WPF SfDiagram and control layout updates with ExpandCollapse parameters.
platform: wpf
control: SfDiagram
documentation: ug
---

# Expand Collapse Command in WPF SfDiagram

The [ExpandCollapse](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ExpandCollapse) command is used to show or hide children and view only the relevant nodes in the diagram. The `ExpandCollapse` command will be executed with the [ExpandCollapseParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html), where the parameter contains information about the node that needs to be expanded or collapsed. The `IsExpanded` property of the node is used to expand or collapse the children nodes. 

N> The `ExpandCollapse` command is intended for hierarchical nodes that contain child nodes, such as those used in organizational charts, tree layouts, and other hierarchical diagram structures. If the specified node does not contain any child nodes, the command will not perform any operation because there are no child elements to expand or collapse.

## ExpandCollapseParameter 

The `ExpandCollapseParameter` is used to compress a view of a hierarchy so that only the roots of the elements are visible. The opposite of collapse is expand that makes the entire elements visible.

### Node

The [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html#Syncfusion_UI_Xaml_Diagram_ExpandCollapseParameter_Node) property is used to set the node that is to be acts as the root element.

N> The `Node` property must be assigned with a valid node instance that supports expand and collapse operations. If the `Node` property is set to `null`, the `ExpandCollapse` command will not perform any operation because there is no target node to expand or collapse.

### IsUpdateLayout

The [IsUpdateLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html#Syncfusion_UI_Xaml_Diagram_ExpandCollapseParameter_IsUpdateLayout) property is used to set whether the layout to be updated or not after the command execution. The default value of the `IsUpdateLayout` property is `false`.

N> In the following example, `args.Item` represents the node associated with the current diagram interaction event (such as a node click or command invocation event). Ensure that the item is a valid `NodeViewModel` with child nodes before executing the `ExpandCollapse` command.

{% tabs %}
{% highlight c# %}

//Initialize the SfDiagram 
SfDiagram diagramcontrol = new SfDiagram();

if (args.Item is NodeViewModel && (args.Item as NodeViewModel).IsExpanded)
{
    ExpandCollapseParameter param = new ExpandCollapseParameter()
    {
        IsUpdateLayout = true,

        // Set the node that is going to be show or hide its children
        node = args.Item as NodeViewModel,
    };

    IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

    //Show or hide the children of node.
    graphinfo.Commands.ExpandCollapse.Execute(param);
    (args.Item as NodeViewModel).IsExpanded = false;
}
else
{
    ExpandCollapseParameter param = new ExpandCollapseParameter()
    {
        IsUpdateLayout = true,

        // Set the node that is going to be show or hide its children
        node = args.Item as NodeViewModel,
    };
    IGraphInfo graphinfo = diagramcontrol.Info as IGraphInfo;

    //Show or hide the children of node.
    graphinfo.Commands.ExpandCollapse.Execute(param);
    (args.Item as NodeViewModel).IsExpanded = true;
}

{% endhighlight %}
{% endtabs %}


![ExpandCollapse](Commands_Images/Commands_img21.gif)


[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Expand%20and%20Collapse%20command)