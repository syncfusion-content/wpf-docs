---
layout: post
title: Delete Command in WPF Diagram control | Syncfusion®
description: Learn here all about Delte Command support in Syncfusion® WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Delete Command in WPF Diagram (SfDiagram)

The [`Delete`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.IDiagramCommands.html#Syncfusion_UI_Xaml_Diagram_IDiagramCommands_Delete) commands are used to do delete operation on the Diagram view for currently selected item. This command is also used to delete any un-selected diagram objects with its parameter. 

To execute delete commands, the [DeleteParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DeleteParameter.html) type has to be passed.

## Delete command parameter

The `DeleteParameter` is used to represent the item's parameters for executing the delete command. The DeleteParameter contains a [`Items`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DeleteParameter.html#Syncfusion_UI_Xaml_Diagram_DeleteParameter_Items) property and it is used to specify a list of diagram objects that need to be deleted using the delete command.

{% tabs %}

{% highlight C# %}

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
    //Adding deleteable objects to the DeleteParameter class using Items property.
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
