---
layout: post
title: Stencil in WPF Diagram control | Syncfusion®
description: Learn here all about Stencil support in Syncfusion® WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil in WPF Diagram (SfDiagram)

The [Stencil](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.html) is a gallery of reusable symbols and diagram elements that can be dragged and dropped on the diagram surface multiple times.

{% tabs %}
{% highlight xaml %}

<!--Namespace for stencil-->
xmlns:stencil="clr-namespace:Syncfusion.UI.Xaml.Diagram.Stencil;assembly=Syncfusion.SfDiagram.WPF"

<!--Define a Stencil-->
<stencil:Stencil x:Name="stencil" ExpandMode="All" BorderBrush="Black" BorderThickness="0,0,1,0" />

{% endhighlight %}

{% highlight c# %}

//Define a Stencil.
Stencil stencil = new Stencil()
{
    ExpandMode = ExpandMode.All,
    BorderThickness = new Thickness(0,0,1,0),
    BorderBrush = new SolidColorBrush(Colors.Black)
};

{% endhighlight %}
{% endtabs %}

![StencilDiagram](Stencil_images/Stencil_img1.PNG)

## Add symbols in a Stencil 

The [Symbol](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Symbol.html) is used to visualize the elements in a stencil that can be created using the following ways:
 
 * Using the diagram elements. 
 * Using the SymbolViewModel.
 
 The Stencil's [`SymbolSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolSource) property is used to define the data source as a collection of objects (symbol, node, connector, and more) that needs to be populated as symbols.
 
## Using the Diagram Elements

The diagram elements such as [NodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html), [ConnectorViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html), [GroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GroupViewModel.html), and [ContainerViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ContainerViewModel.html) can be used to visualize the symbol.
 
{% tabs %} 
{% highlight xaml %}
<!--Initialize the stencil-->
<stencil:Stencil x:Name="stencil"
                 Grid.Column="0"
                 Grid.Row="1"
                 ExpandMode="ZeroOrMore"
                 BorderBrush="#dfdfdf"
                 BorderThickness="1"
                 GroupMappingName="Key">
    <stencil:Stencil.SymbolSource>
        <syncfusion:SymbolCollection>
            <!--Define the DiagramElement- Node-->
            <syncfusion:NodeViewModel x:Name="node"
                                      Key="Nodes"
                                      UnitHeight="70"
                                      UnitWidth="100"
                                      OffsetX="100"
                                      OffsetY="100"
                                      Shape="{StaticResource Rectangle}">
            </syncfusion:NodeViewModel>
            <!--Define the DiagramElement- Connector-->
            <syncfusion:ConnectorViewModel Key="Connectors" 
                                           SourcePoint="100,100"
                                           TargetPoint="200,200" />
            <!--Define the DiagramElement- Group-->
            <syncfusion:GroupViewModel Key="Groups">
                <!--Creates the Groupable Nodes-->
                <syncfusion:GroupViewModel.Nodes>
                    <syncfusion:NodeCollection>
                        <syncfusion:NodeViewModel UnitHeight="70"
                                                  ID="srcnode"
                                                  OffsetX="0"
                                                  OffsetY="300"
                                                  UnitWidth="100"
                                                  Shape="{StaticResource Rectangle}">
                        </syncfusion:NodeViewModel>
                        <syncfusion:NodeViewModel UnitHeight="70"
                                                  ID="tarnode"
                                                  OffsetX="100"
                                                  OffsetY="500"
                                                  UnitWidth="100"
                                                  Shape="{StaticResource Rectangle}">
                        </syncfusion:NodeViewModel>
                    </syncfusion:NodeCollection>
                </syncfusion:GroupViewModel.Nodes>
                <!--Creates the Groupable Connectors-->
                <syncfusion:GroupViewModel.Connectors>
                    <syncfusion:ConnectorCollection>
                        <syncfusion:ConnectorViewModel SourceNodeID="srcnode"
                                                       TargetNodeID="tarnode" />
                    </syncfusion:ConnectorCollection>
                </syncfusion:GroupViewModel.Connectors>
            </syncfusion:GroupViewModel>
            <!--Creates the container-->
            <syncfusion:ContainerViewModel Key="Container" 
                                           OffsetX="300" 
                                           OffsetY="300" 
                                           UnitHeight="200" 
                                           UnitWidth="250">
                <!--Creates the container Nodes-->
                <syncfusion:GroupViewModel.Nodes>
                    <syncfusion:NodeCollection>
                        <syncfusion:NodeViewModel UnitHeight="70"
                                                  UnitWidth="100"
                                                  OffsetX="250"
                                                  OffsetY="250"
                                                  Shape="{StaticResource Rectangle}">
                        </syncfusion:NodeViewModel>
                        <syncfusion:NodeViewModel UnitHeight="70"
                                                  UnitWidth="100"
                                                  OffsetX="300"
                                                  OffsetY="350"
                                                  Shape="{StaticResource Rectangle}">
                        </syncfusion:NodeViewModel>
                    </syncfusion:NodeCollection>
                </syncfusion:GroupViewModel.Nodes>
            </syncfusion:ContainerViewModel>
        </syncfusion:SymbolCollection>
    </stencil:Stencil.SymbolSource>
</stencil:Stencil>
{% endhighlight %}

{% highlight c# %}
//Define the SymbolSource with SymbolCollection.
stencil.SymbolSource = new SymbolCollection();

//Initialize the node diagram element.
NodeViewModel node = new NodeViewModel()
{
    Key = "Nodes",
    UnitHeight = 70,
    UnitWidth = 100,
    OffsetX = 100,
    OffsetY = 100,
    Shape = this.Resources["Rectangle"],
};

//Initialize the connector diagram element.
ConnectorViewModel connector = new ConnectorViewModel()
{
    Key = "Connectors",
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};

//Initialize the group element.
GroupViewModel group = new GroupViewModel()
{
    Key = "Groups",
    //Adding group nodes
    Nodes = new NodeCollection()
    {
        new NodeViewModel()
        {
            ID="srcnode",
            UnitHeight=70,
            UnitWidth=100,
            OffsetX=0,
            OffsetY=300,
            Shape=this.Resources["Rectangle"]
        },
        new NodeViewModel()
        {
            ID="tarnode",
            UnitHeight=70,
            UnitWidth=100,
            OffsetX=100,
            OffsetY=500,
            Shape=this.Resources["Rectangle"]
        }
    },
    //Adding group connector.
    Connectors = new ConnectorCollection()
    {
        new ConnectorViewModel()
        {
            SourceNodeID="srcnode",
            TargetNodeID="tarnode"
        }
    }
};
GroupViewModel group = new GroupViewModel()
{
    Key = "Groups",
    //Adding group nodes
    Nodes = new NodeCollection()
    {
        new NodeViewModel()
        {
            ID="srcnode",
            UnitHeight=70,
            UnitWidth=100,
            OffsetX=0,
            OffsetY=300,
            Shape=this.Resources["Rectangle"]
        },
        new NodeViewModel()
        {
            ID="tarnode",
            UnitHeight=70,
            UnitWidth=100,
            OffsetX=100,
            OffsetY=500,
            Shape=this.Resources["Rectangle"]
        }
    },
    //Adding group connector.
    Connectors = new ConnectorCollection()
    {
        new ConnectorViewModel()
        {
            SourceNodeID="srcnode",
            TargetNodeID="tarnode"
        }
    }
};

//Creating container element.
ContainerViewModel container = new ContainerViewModel()
{
    Key = "Container",
    UnitHeight = 200,
    UnitWidth = 250,
    OffsetX = 300,
    OffsetY = 300,
    //Creating container nodes
    Nodes = new NodeCollection()
    {
        new NodeViewModel()
        {
            UnitHeight = 70,
            UnitWidth = 100,
            OffsetX = 250,
            OffsetY = 250,
            Shape = this.Resources["Rectangle"],
        },
        new NodeViewModel()
        {
            UnitHeight = 70,
            UnitWidth = 100,
            OffsetX = 300,
            OffsetY = 350,
            Shape = this.Resources["Rectangle"],
        },
    },
};

//Adding diagram elements to the stencil SymbolSource collection.
(stencil.SymbolSource as SymbolCollection).Add(node);
(stencil.SymbolSource as SymbolCollection).Add(connector);
(stencil.SymbolSource as SymbolCollection).Add(group);
(stencil.SymbolSource as SymbolCollection).Add(container); 
{% endhighlight %}

{% endtabs %}

![DiagramElements](Stencil_images/stencil1.PNG) 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-node-connector-group)

## Using the SymbolViewModel

The [SymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html) has [`Symbol`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_Symbol) and [`SymbolTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_SymbolTemplate) properties to visualize the `Symbol` in the stencil.

{% tabs %}

{% highlight xaml %}

<DataTemplate x:Key="Diamond">
    <StackPanel>
        <Path Stretch="Fill"
              Data="M 397.784,287.875L 369.5,316.159L 341.216,287.875L 369.5,259.591L 397.784,287.875 Z"
              Fill="White"
              Stroke="Black"
              StrokeThickness="1" />
        <TextBlock HorizontalAlignment="Center" VerticalAlignment="Center" Text="Diamond" />
    </StackPanel>
</DataTemplate>
<DataTemplate x:Key="symboltemplate">
    <StackPanel>
       <Image Source="/Image/user_image.png" Width="100" Height="80" />
       <TextBlock HorizontalAlignment="Center" VerticalAlignment="Center" Text="User" />
    </StackPanel>
</DataTemplate>

<stencil:Stencil x:Name="stencil"
                 Grid.Column="0"
                 Grid.Row="1"
                 ExpandMode="ZeroOrMore"
                 BorderBrush="#dfdfdf"
                 BorderThickness="1"
                 GroupMappingName="Key">
    <stencil:Stencil.SymbolSource>
        <syncfusion:SymbolCollection>
            <syncfusion:SymbolViewModel Symbol="User" Key="Image"
                                        SymbolTemplate="{StaticResource symboltemplate}" />
            <syncfusion:SymbolViewModel Symbol="Diamond" Key="Template"
                                        SymbolTemplate="{StaticResource Diamond}" />

        </syncfusion:SymbolCollection>
    </stencil:Stencil.SymbolSource>
</stencil:Stencil>
 
{% endhighlight %}
 
{% highlight c# %}

//Define the SymbolSource with the SymbolCollection.
stencil.SymbolSource = new SymbolCollection();
 
//Initialize the SymbolItem.
SymbolViewModel imagenode = new SymbolViewModel()
{    
    Symbol = "User",
    SymbolTemplate = this.Resources["symboltemplate"] as DataTemplate
};

SymbolViewModel symbol = new SymbolViewModel()
{    
    Symbol = "Diamond",
    SymbolTemplate = this.Resources["Diamond"] as DataTemplate
};

//Adding the element to the collection.
(stencil.SymbolSource as SymbolCollection).Add(imagenode);
(stencil.SymbolSource as SymbolCollection).Add(symbol);

{% endhighlight %}
{% endtabs %}

![Symbol](Stencil_images/symbolimage.PNG) 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-symbols)

## Constraints

The [`Constraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_Constraints) property of stencil allows you to enable or disable certain features. For more information about stencil constraints, refer to the [StencilConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html).

## See also

[How to drag and drop elements from a treeview ?](https://www.syncfusion.com/kb/10574/how-to-drag-and-drop-elements-from-treeview-in-wpf-diagramsfdiagram)

[How to refresh the stencil when adding a new symbol in the symbol source ?](https://www.syncfusion.com/kb/9928/how-to-refresh-the-stencil-when-adding-new-symbol-in-symbol-source)

[How to host different UI elements as a node content ?](https://www.syncfusion.com/kb/9456/how-to-host-different-ui-elements-as-node-content)

[How to notify stencil has been loaded ?](https://www.syncfusion.com/kb/6256/how-to-notify-stencil-has-been-loaded)

[How to get the base node interface while dropping a Symbol from Stencil to SfDiagram ?](https://www.syncfusion.com/kb/5880/how-to-get-the-base-node-interface-while-dropping-a-symbol-from-the-stencil-to-the)

[How to use different User Controls into Stencil?](https://www.syncfusion.com/kb/11459/how-to-use-different-user-controls-into-stencil-in-the-wpf-diagramsfdiagram)

[How to refresh the stencil with new collection or new symbol?](https://support.syncfusion.com/kb/article/8714/how-to-refresh-stencil-with-new-collection-or-symbol-in-wpf-diagram)

[How to create the SfDiagram with stencil control?](https://support.syncfusion.com/kb/article/8908/how-to-create-the-wpf-diagram-sfdiagram-with-stencil)

[How to modify stencil's symbol template dynamically at run time?](https://support.syncfusion.com/kb/article/11582/how-to-modify-stencils-symbol-template-dynamically-at-run-time-in-wpf-diagramsfdiagram)

[How to drag and drop elements from treeview?](https://support.syncfusion.com/kb/article/9277/how-to-drag-and-drop-elements-from-treeview-in-wpf-diagram-sfdiagram)

[How to drag and drop different shapes from SfTreeView to WPF Diagram?](https://support.syncfusion.com/kb/article/10960/how-to-drag-and-drop-different-shapes-from-sftreeview-to-wpf-diagram-sfdiagram)

[How to restrict the symbol dropping from the SymbolPalette?](https://support.syncfusion.com/kb/article/9919/how-to-restrict-the-symbol-dropping-from-the-symbolpalette-in-the-wpf-diagram-sfdiagram)

[How to create parent and child relationship by drag and drop nodes?](https://support.syncfusion.com/kb/article/10008/how-to-create-parent-and-child-relationship-by-drag-and-drop-nodes-in-wpf-diagram-sfdiagram)

[How to get the notification when symbol is added to the stencil?](https://support.syncfusion.com/kb/article/5863/how-to-notify-stencil-in-wpf-diagram-sfdiagram)

[How to get base node interface while dropping a symbol from stencil?](https://support.syncfusion.com/kb/article/5494/how-to-get-base-node-interface-while-dropping-a-symbol-from-stencil-to-wpf-diagram)

[How to expand all symbol groups in stencil?](https://support.syncfusion.com/kb/article/5492/how-to-expand-all-symbol-groups-in-wpf-diagram-sfdiagram)

[How to change the color of a node in the stencil and diagram while loading a saved file in WPF Diagram(SfDiagram)?](https://support.syncfusion.com/kb/article/18669/how-to-change-the-color-of-a-node-in-the-stencil-and-diagram-while-loading-a-saved-file-in-wpf-diagramsfdiagram)

[How to group all the SymbolViewModels into the same group in the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18672/how-to-group-all-the-symbolviewmodels-into-the-same-group-in-the-wpf-diagram-sfdiagram)

[How to Create Customized Stencil Using SVG Images in WPF SfDiagram?](https://support.syncfusion.com/kb/article/18251/how-to-create-customized-stencil-using-svg-images-in-wpf-sfdiagram)

[How to Change Cursor to Block Cursor When Hovering in WPF SfDiagram?](https://support.syncfusion.com/kb/article/18242/how-to-change-cursor-to-block-cursor-when-hovering-in-wpf-sfdiagram)

[How to Change the Background Color of a Symbol in WPF SfDiagram?](https://support.syncfusion.com/kb/article/18241/how-to-change-the-background-color-of-a-symbol-in-wpf-sfdiagram)

[How to drag and drop both default and custom node from the stencil into the WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18459/how-to-drag-and-drop-both-default-and-custom-node-from-the-stencil-into-the-wpf-diagram-sfdiagram)

[How to enable/disable the Stencil symbol in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/17888/how-to-enabledisable-the-stencil-symbol-in-wpf-diagram-sfdiagram)

[How to Achieve the Stencil Preview Effect Without Dragging a Symbol in the WPF Diagram (SfDiagram)](https://support.syncfusion.com/kb/article/15537/how-to-achieve-the-stencil-preview-effect-without-dragging-a-symbol-in-the-wpf-diagram-sfdiagram)

[How to refresh stencil with new collection or symbol in WPF Diagram?](https://support.syncfusion.com/kb/article/8714/how-to-refresh-stencil-with-new-collection-or-symbol-in-wpf-diagram)

[How to create the WPF Diagram (SfDiagram) with stencil?](https://support.syncfusion.com/kb/article/8908/how-to-create-the-wpf-diagram-sfdiagram-with-stencil)

[How to achieve the AutoConnect functionality in WPF Diagram (SfDiagram)?](https://support.syncfusion.com/kb/article/18252/how-to-achieve-the-autoconnect-functionality-in-wpf-diagram-sfdiagram)