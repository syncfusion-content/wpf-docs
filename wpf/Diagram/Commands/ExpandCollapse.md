---
layout: post
title: Expand Collapse Command in WPF Diagram control | Syncfusion
description: Learn here all about Expand Collapse Command support in Syncfusion WPF Diagram (SfDiagram) control and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Expand Collapse Command in WPF Diagram (SfDiagram)

The [ExpandCollapse](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_ExpandCollapse) command is used to show or hide children and view only the relevant nodes in the diagram. The ExpandCollapse command will be executed with the [ExpandCollapseParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html) where the parameter contains the information about node that need to be expanded or collapsed. The IsExpanded property of node is used to expand or collapse the children nodes. 

## ExpandCollapseParameter 

The [ExpandCollapseParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html) is used to compress a view of a hierarchy so that only the roots of each elements are visible. The opposite of collapse is expand that makes the entire elements visible.

### Node

The [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html#Syncfusion_UI_Xaml_Diagram_ExpandCollapseParameter_node) is used to set the node that is to be act as root element.

### IsUpdateLayout

The [IsUpdateLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html#Syncfusion_UI_Xaml_Diagram_ExpandCollapseParameter_IsUpdateLayout) is used to set whether the layout to be updated or not after the command execution.

{% tabs %}
{% highlight C# %}

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
