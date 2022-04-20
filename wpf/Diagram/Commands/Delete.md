---
layout: post
title: Delete Command in WPF Diagram control | Syncfusion
description: Learn here all about Delte Command support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Delete Command in WPF Diagram (SfDiagram)

The [Delete](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Delete) commands are used to do delete operation on the Diagram view for currently selected item. This command is also used to delete any un-selected diagram objects with its parameter. 

To execute delete commands, the DeleteCommandParameter type has to be passed.

## Delete command parameter

The DeleteParameter is used to represent the item's parameters for executing the delete command. Please find its properties and their description as follows. The DeleteParameter contains a Items property and it is used to specify a list of diagram objects that need to be deleted using the delete command.

{% tabs %}

{% highlight C# %}

List<IGroupable> deleteableNodes = new List<IGroupable>();
if (selectedNode != null)
{
    foreach (NodeViewModel node in diagram.Nodes as IEnumerable<object>)
    {
        if (node.ID.ToString().Equals(selectedNode.ToString()))
        {
            deleteableNodes.Add(node);
        }
    }
}
if (deleteableNodes.Count > 0)
{
    var parameter = new DeleteParameter() { Items = deleteableNodes };
    //Executing DeleteCommand by passing DeleteParameter
    (diagram.Info as IGraphInfo).Commands.Delete.Execute(parameter);
}
else
    //Executing DeleteCommand for selected nodes.
    (diagram.Info as IGraphInfo).Commands.Delete.Execute(null);

{% endhighlight %}
{% endtabs %}


![Delete and DeleteParameter](Commands_Images/DeleteCommandParameter.gif)


[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Delete%20Command)
