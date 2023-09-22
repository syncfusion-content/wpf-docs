---
layout: post
title: Stencil in WPF Diagram control | Syncfusion
description: Learn here all about Stencil support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
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
 
 The Stencil's [SymbolSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolSource) property is used to define the data source as a collection of objects (symbol, node, connector, and more) that needs to be populated as symbols.
 
## Using the Diagram Elements

The diagram elements such as [NodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html), [ConnectorViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html), [GroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GroupViewModel.html), and [ContainerViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ContainerViewModel.html) can be used to visualize the symbol.
 
{% tabs %} 
{% highlight xaml %}

<!--Initialize the SymbolSource-->
<stencil:Stencil.SymbolSource>
    <!--Define the SymbolCollection-->
    <Syncfusion:SymbolCollection>
        <syncfusion:NodeViewModel x:Name="node" UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Shape="{StaticResource Rectangle}">
        </syncfusion:NodeViewModel>
        <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200"/>
        <!--Define the DiagramElement- Group-->
        <syncfusion:GroupViewModel>
            <!--Creates the Groupable Nodes-->
            <syncfusion:GroupViewModel.Nodes>
                <syncfusion:NodeCollection>
                    <syncfusion:NodeViewModel UnitHeight="70" ID="srcnode" OffsetX="0" OffsetY="300" 
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
                    <syncfusion:ConnectorViewModel SourceNodeID="srcnode" TargetNodeID="tarnode"/>
                </syncfusion:ConnectorCollection>
            </syncfusion:GroupViewModel.Connectors>
        </syncfusion:GroupViewModel>
        <Syncfusion:ContainerViewModel Key="Container" UnitHeight="300" UnitWidth="300">
            <!--Creates the Groupable Nodes-->
            <Syncfusion:GroupViewModel.Nodes>
                <Syncfusion:NodeCollection>
                    <Syncfusion:NodeViewModel UnitHeight="70"
                                              OffsetX="0"
                                              OffsetY="100"
                                              UnitWidth="100"
                                              Shape="{StaticResource Rectangle}">
                    </Syncfusion:NodeViewModel>
                    <Syncfusion:NodeViewModel UnitHeight="70"
                                              OffsetX="100"
                                              OffsetY="200"
                                              UnitWidth="100"
                                              Shape="{StaticResource Rectangle}">
                    </Syncfusion:NodeViewModel>
                </Syncfusion:NodeCollection>
            </Syncfusion:GroupViewModel.Nodes>
        </Syncfusion:ContainerViewModel>
    </Syncfusion:SymbolCollection>
</stencil:Stencil.SymbolSource>

{% endhighlight %}

{% highlight c# %}

//Define the SymbolSource with SymbolCollection.
stencil.SymbolSource = new SymbolCollection();

//Initialize the diagram element.
NodeViewModel node = new NodeViewModel()
{
    UnitHeight = 70,
    UnitWidth = 100,
    OffsetX = 100, OffsetY = 100,
    Shape = App.Current.MainWindow.Resources["Rectangle"],
}; 

ConnectorViewModel cvm = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
};

GroupViewModel grp = new GroupViewModel()
{
    Nodes = new NodeCollection()
    {
       new NodeViewModel()
       {
         ID="srcnode",
         UnitHeight=70,
         UnitWidth=100,
         OffsetX=0,
         OffsetY=300,
         Shape=App.Current.Resources["Rectangle"]
        },
       new NodeViewModel()
       {
        ID="tarnode",
        UnitHeight=70,
        UnitWidth=100,
        OffsetX=100,
        OffsetY=500,
        Shape=App.Current.Resources["Rectangle"]
        }
    },
    Connectors = new ConnectorCollection()
    {
      new ConnectorViewModel()
      {
        SourceNodeID="srcnode", 
        TargetNodeID="tarnode"
      }
    }
};

ContainerViewModel container = new ContainerViewModel()
{
    UnitHeight = 300,
    UnitWidth = 300,
    Key = "Container",
    Nodes = new NodeCollection()
    {
        new NodeViewModel()
        {
            UnitHeight = 70,
            OffsetX = 0,
            OffsetY = 100,
            UnitWidth = 100,
            Shape = this.Resources["Rectangle"],
        },
        new NodeViewModel()
        {
            UnitHeight = 70,
            OffsetX = 100,
            OffsetY = 200,
            UnitWidth = 100,
            Shape = this.Resources["Rectangle"],
        },
    },
};

//Adding an element to the collection.
(stencil.SymbolSource as SymbolCollection).Add(node);
(stencil.SymbolSource as SymbolCollection).Add(cvm);
(stencil.SymbolSource as SymbolCollection).Add(grp);
(stencil.SymbolSource as SymbolCollection).Add(container);

{% endhighlight %}

{% endtabs %}

![DiagramElements](Stencil_images/stencil1.PNG) 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-node-connector-group)

## Using the SymbolViewModel

The [SymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html) has [Symbol](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_Symbol) and [SymbolTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolViewModel_SymbolTemplate) properties to visualize the `Symbol` in the stencil.

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

<stencil:Stencil.SymbolSource>
    <!--Define the SymbolCollection-->
    <Syncfusion:SymbolCollection>
        <Syncfusion:SymbolViewModel Symbol="User" SymbolTemplate="{StaticResource symboltemplate}"/>
         <Syncfusion:SymbolViewModel Symbol="Diamond" SymbolTemplate="{StaticResource Diamond}"/>
    </Syncfusion:SymbolCollection>
</stencil:Stencil.SymbolSource>
 
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

## Constraints

The `Constraints` property of stencil allows you to enable or disable certain features. For more information about stencil constraints, refer to the [StencilConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html).

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-symbols)

## See also

* [How to drag and drop elements from a treeview?](https://support.syncfusion.com/kb/article/9277/how-to-drag-and-drop-elements-from-treeview-in-wpf-diagram-sfdiagram)
* [How to refresh the stencil when adding a new symbol in the symbol source?](https://support.syncfusion.com/kb/article/8714/how-to-refresh-stencil-with-new-collection-or-symbol-in-wpf-diagram)
* [How to host different UI elements as a node content ?](https://support.syncfusion.com/kb/article/8182/how-to-host-different-ui-elements-as-node-content-in-the-wpf-diagram-sfdiagram)
* [How to notify stencil has been loaded?](https://support.syncfusion.com/kb/article/5863/how-to-notify-stencil-in-wpf-diagram-sfdiagram)
* [How to get the base node interface while dropping a Symbol from Stencil to SfDiagram?](https://support.syncfusion.com/kb/article/5494/how-to-get-base-node-interface-while-dropping-a-symbol-from-stencil-to-wpf-diagram)
* [How to use different User Controls into Stencil?](https://support.syncfusion.com/kb/article/9924/how-to-use-different-user-controls-into-stencil-in-the-wpf-diagram-sfdiagram)
