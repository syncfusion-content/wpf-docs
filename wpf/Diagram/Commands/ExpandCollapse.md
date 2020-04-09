---
layout: post
title: Syncfusion | Explore the ExpandCollapse command.
description: Expand and Collapse command is used to show or hide children with IsExpanded property in ExpandCollapseParameter.
platform: wpf
control: SfDiagram
documentation: ug
---

# ExpandCollapse command

`ExpandCollapse` command is used to show or hide children and view only the relevant nodes in the diagram. The ExpandCollapse command will be executed with [ExpandCollapseParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.ExpandCollapseParameter.html) where the parameter contains the information about node which need to be expanded or collapsed. The IsExpanded property of Node is used to expand or collapse the children nodes. 

## ExpandCollapseParameter 

`ExpandCollapseParameter` is used to compress a view of a hierarchy so that only the roots of each Elements are visible. The opposite of collapse is expand, which makes the entire Elements visible.

### Node

`Node` is used to set the node that is to be act as root element.

### IsUpdateLayout

`IsUpdateLayout` is used to set whether the layout to be update or not after the command execution.

{% tabs %}
{% highlight C# %}

            if (args.Item is NodeViewModel && (args.Item as NodeViewModel).IsExpanded)
            {
                ExpandCollapseParameter param = new ExpandCollapseParameter()
                {
                    IsUpdateLayout = true,

                    // Set the node which is going to be show or hide its children
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

                    // Set the node which is going to be show or hide its children
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


Please find the [ExpandCollapse sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Expand%20and%20Collapse%20command) to depict this command.