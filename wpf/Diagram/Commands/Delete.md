---
layout: post
title: Delete Command in WPF SfDiagram | Syncfusion®
description: Delete selected or specified diagram elements in Syncfusion® WPF SfDiagram using the Delete command and DeleteParameter settings.
platform: wpf
control: SfDiagram
documentation: ug
---

# Delete Command in WPF SfDiagram

The [`Delete`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Delete) command is used to perform delete operations on the Diagram view for the currently selected item. This command is also used to delete any unselected diagram objects with its parameter. 

To execute delete commands, the [DeleteParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DeleteParameter.html) type must be passed.

N> When `null` is passed to the Delete command, the currently selected diagram elements are deleted. If no diagram elements are selected, the command will not perform any operation.

## Delete command parameter

The `DeleteParameter` is used to represent the item's parameters for executing the delete command. The DeleteParameter contains a [`Items`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DeleteParameter.html#Syncfusion_UI_Xaml_Diagram_DeleteParameter_Items) property and it is used to specify a list of diagram objects that need to be deleted using the delete command.

N> When `null` is passed to the Delete command, the currently selected diagram objects are deleted. If no diagram objects are selected, the command will not perform any operation.

The following example locates nodes and connectors by using their `ID` property. Ensure that unique IDs are assigned to the diagram objects when they are created or loaded so that the required objects can be identified before executing the delete command.

{% tabs %}

{% highlight c# %}

List<IGroupable> deleteableObjects = new List<IGroupable>();

//Finding selected nodes based on IDs.
if (selectedNode != null)
{
    foreach (NodeViewModel node in diagram.Nodes as IEnumerable<object>)
    {
        if (node.ID.ToString().Equals(selectedNode.ToString()))
            deleteableObjects.Add(node);
    }
}

//Finding selected connectors based on IDs.
if (selectedConnector != null)
{
    foreach (ConnectorViewModel connector in diagram.Connectors as IEnumerable<object>)
    {
        if (connector.ID.ToString().Equals(selectedConnector.ToString()))
            deleteableObjects.Add(connector);
    }
}

if (deleteableObjects.Count > 0)
{
    //Adding deletable objects to the DeleteParameter class using Items property.
    var parameter = new DeleteParameter() { Items = deleteableObjects };
    //Executing delete command with DeleteParameter items.
    (diagram.Info as IGraphInfo).Commands.Delete.Execute(parameter);
}
else
    //Executing delete command with null value and currently selected items will be deleted.
    (diagram.Info as IGraphInfo).Commands.Delete.Execute(null);

{% endhighlight %}
{% endtabs %}

![Delete and DeleteParameter](Commands_Images/DeleteCommandParameter.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Commands/Delete%20Command)