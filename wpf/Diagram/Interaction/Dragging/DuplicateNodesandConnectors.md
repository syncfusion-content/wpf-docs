---
layout: post
title: Duplicate Nodes and Connectors in WPF Diagram | Syncfusion®
description: Duplicate nodes, connectors, and groups in Syncfusion® WPF Diagram by dragging selected elements while holding the Ctrl key.
platform: wpf
control: SfDiagram
documentation: ug
---
# Duplicate Nodes and Connectors in WPF Diagram

The [WPF Diagram](https://www.syncfusion.com/diagram-sdk/wpf-diagram) simplifies the process of duplicating nodes and connectors. You can create duplicates by dragging. of selected nodes or connectors by simply holding down the Ctrl key, providing an improved experience for editing your diagrams.

![DuplicateNodesandConnectors](Drag_images/DuplicateNodeandConnectors.gif)

N> To duplicate connectors using Ctrl + Drag, the connector must first be enabled for dragging by setting the [`ConnectorConstraints.Draggable`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorConstraints.html#Syncfusion_UI_Xaml_Diagram_ConnectorConstraints_Draggable) constraint.

{% tabs %}
{% highlight xaml %}

 <!--Initialize the Sfdiagram-->
 <syncfusion:SfDiagram x:Name="diagram" >
     <!--Initialize the connectors-->
     <syncfusion:SfDiagram.Connectors>
         <!--Initialize the Connector Collection-->
         <syncfusion:ConnectorCollection>
             <!--create the simple connector with Draggable constraints-->
             <syncfusion:ConnectorViewModel x:Name="simpleConnector" Constraints="Default,Draggable"
                                            SourcePoint="100,100" TargetPoint="200,200" />
         </syncfusion:ConnectorCollection>
     </syncfusion:SfDiagram.Connectors>
 </syncfusion:SfDiagram>

{% endhighlight %}

{% highlight c# %}


SfDiagram diagram = new SfDiagram();

diagram.Connectors = new ConnectorCollection();

ConnectorViewModel simpleConnector = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};

simpleConnector.Constraints |= ConnectorConstraints.Draggable;

//Adding the connector into Collection
(diagram.Connectors as ConnectorCollection).Add(simpleConnector);

{% endhighlight %}
{% endtabs %}

## See Also

[How to show the copied diagram elements as preview image along with the mouse pointer?](https://support.syncfusion.com/kb/article/12037/how-to-show-the-copied-diagram-elements-as-preview-image-along-with-the-mouse-pointer-in)

[How to disable Ctrl + Drag duplicate behavior in WPF Diagram?](https://support.syncfusion.com/kb/article/18502/how-to-disable-ctrl--drag-duplicate-behavior-in-wpf-diagramsfdiagram)