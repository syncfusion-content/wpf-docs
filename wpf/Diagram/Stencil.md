---
layout: post
title: Define and add the Nodes or Connectors to the Stencil | Syncfusion.
description: How to add the Symbol and Nodes or Connectors to the Stencil and drag and drop them over the drawing area?
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil in the WPF Diagram (SfDiagram)

The [Stencil](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.html) is a gallery of reusable symbols and diagram elements that can be dragged and dropped on the diagram surface many times.

{% tabs %}
{% highlight xaml %}

<!--Namespace for stencil-->
xmlns:stencil="clr-namespace:Syncfusion.UI.Xaml.Diagram.Stencil;assembly=Syncfusion.SfDiagram.WPF"

<!--Define a Stencil-->
<stencil:Stencil x:Name="stencil" ExpandMode="All" BorderBrush="Black" BorderThickness="0,0,2,0" />

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

The [Symbol](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Symbol.html) is used to visualize the elements in a Stencil that can be created using the following ways:
 
 * Using the diagram elements. 
 * Using the SymbolViewModel.
 
 The Stencil's [SymbolSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolSource) property is used to define the data source as a collection of objects (symbol, node, connector, and more) that needs to be populated as symbols.
 
### Using the Diagram Elements

The diagram elements such as [NodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html), [ConnectorViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html), and [GroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GroupViewModel.html) can be used to visualize the symbol.
 
{% tabs %} 
{% highlight xaml %}

<!--Initialize the SymbolSource-->
<stencil:Stencil.SymbolSource>
    <!--Define the SymbolCollection-->
    <local:SymbolCollection>
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
    </local:SymbolCollection>
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
//Adding an element to the collection.
(stencil.SymbolSource as SymbolCollection).Add(node);
(stencil.SymbolSource as SymbolCollection).Add(cvm);
(stencil.SymbolSource as SymbolCollection).Add(grp);

//Adding the ISymbol to the SymbolCollection.
public class SymbolCollection : ObservableCollection<Object>
{
}

{% endhighlight %}

{% endtabs %}

![DiagramElements](Stencil_images/stencil1.PNG) 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-node-connector-group)

### Using the SymbolViewModel

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
        <TextBlock HorizontalAlignment="Center"
                   VerticalAlignment="Center"
                   Text="Diamond" />
    </StackPanel>
</DataTemplate>
 <DataTemplate x:Key="symboltemplate">
            <StackPanel>
                <Image Source="/Image/user_image.png"
                       Width="100"
                       Height="80" />
                <TextBlock HorizontalAlignment="Center"
                           VerticalAlignment="Center"
                           Text="User" />
            </StackPanel>
</DataTemplate>

<stencil:Stencil.SymbolSource>
    <!--Define the SymbolCollection-->
    <local:SymbolCollection>
        <Syncfusion:SymbolViewModel Symbol="User" SymbolTemplate="{StaticResource symboltemplate}"/>
         <Syncfusion:SymbolViewModel Symbol="Diamond" SymbolTemplate="{StaticResource Diamond}"/>
    </local:SymbolCollection>
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

//Adding the ISymbol to the SymbolCollection.
public class SymbolCollection : ObservableCollection<Object>
{
}

{% endhighlight %}

{% endtabs %}

![Symbol](Stencil_images/symbolimage.PNG) 

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil-with-symbols)

### Customize the Symbol appearance

You can customize the appearance of a `Symbol` by changing its style (Background, BorderThickness, BorderBrush, and Padding). The following code explains how to customize the appearance of the symbol.

The width and height properties of the symbol enable you to define the size of the symbols.


{% tabs %}

{% highlight xaml %}

 <!--Style for Symbol-->
        <Style TargetType="stencil:Symbol">
            <Setter Property="Width" Value="100" />
            <Setter Property="Height" Value="100" />
            <Setter Property="BorderThickness" Value="1" />
            <Setter Property="Background" Value="Transparent" />
            <Setter Property="BorderBrush" Value="Blue" />            
            <Setter Property="Padding" Value="5"></Setter>
        </Style>

{% endhighlight %}
 
{% endtabs %}

![Symbol](Stencil_images/imagenode1.PNG) 

### Add the name and tooltip to the symbol
You can use the `Name` property of the [NodeViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeViewModel.html), [ConnectorViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ConnectorViewModel.html), [GroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.GroupViewModel.html), and [SymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolViewModel.html) to specify the identifying name to that element. Please find the following code example.

{% tabs %}

{% highlight xaml %}
<Stencil:Stencil x:Name="stencil" ExpandMode="ZeroOrMore">
    <Stencil:Stencil.SymbolSource>
       <Syncfusion:SymbolCollection>
        <Syncfusion:NodeViewModel Key="Basic Shapes" UnitHeight="100" UnitWidth="100" Name="Triangle" Shape="{StaticResource Triangle}"></Syncfusion:NodeViewModel>
        <Syncfusion:SymbolViewModel Symbol="User" Key="Image" Name="User"
          SymbolTemplate="{StaticResource symboltemplate}" />
      </Syncfusion:SymbolCollection>
    </Stencil:Stencil.SymbolSource>
    <Stencil:Stencil.SymbolGroups>
      <Stencil:SymbolGroups>
      <!--Separate groups based on the key-->
         <Stencil:SymbolGroupProvider MappingName="Key" />
       </Stencil:SymbolGroups>
    </Stencil:Stencil.SymbolGroups>
</Stencil:Stencil>

{% endhighlight %}
 
{% endtabs %}

By default, the `Name` property of the diagramming elements(NodeViewModel, ConnectorViewModel, GroupViewModel, and more) is displayed as a tooltip of that symbol while moving the mouse over that symbol but you can give your custom tooltip to that symbol also. Please find the following code example.

{% tabs %}

{% highlight xaml %}

 <!--Style for Symbol-->
<Style TargetType="stencil:Symbol">
 <Setter Property="ToolTip" Value="{Binding Symbol}"></Setter>
 <Setter Property="Width" Value="100" />
 <Setter Property="Height" Value="100" />
 <Setter Property="BorderThickness" Value="1" />
 <Setter Property="Background" Value="Transparent" />
 <Setter Property="BorderBrush" Value="Blue" />            
 <Setter Property="Padding" Value="5"></Setter>
</Style>
<Stencil:Stencil x:Name="stencil" ExpandMode="ZeroOrMore">
    <Stencil:Stencil.SymbolSource>
       <Syncfusion:SymbolCollection>
        <Syncfusion:SymbolViewModel Symbol="User" Key="Image" Name="User"
          SymbolTemplate="{StaticResource symboltemplate}" />
        <Syncfusion:SymbolViewModel  Key="Template" Name="Diamond"
             SymbolTemplate="{StaticResource Diamond}" >
         <Syncfusion:SymbolViewModel.Symbol>
            <StackPanel Orientation="Vertical">
                <TextBlock   FontSize="14" FontWeight="Bold" Foreground="Black" Text="Diamond" Margin="0,0,0,10">
                </TextBlock>
                <TextBlock FontStyle="Italic" FontSize="12" Foreground="Black" Text="Drag onto the Page">
                </TextBlock>
            </StackPanel>
        </Syncfusion:SymbolViewModel.Symbol>
        </Syncfusion:SymbolViewModel>
      </Syncfusion:SymbolCollection>
    </Stencil:Stencil.SymbolSource>
    <Stencil:Stencil.SymbolGroups>
      <Stencil:SymbolGroups>
      <!--Separate groups based on the key-->
         <Stencil:SymbolGroupProvider MappingName="Key" />
       </Stencil:SymbolGroups>
    </Stencil:Stencil.SymbolGroups>
</Stencil:Stencil>
{% endhighlight %}
 
{% endtabs %}

![Symbol](Stencil_images/imagenode.PNG) 

N> The `DataContext` of the `Symbol` will be any diagramming elements such as `NodeViewModel,` `ConnectorViewModel,` `GroupViewModel,` and `SymbolViewModel.`

## Group symbols into a category

The symbols of the same category can be grouped using the [SymbolGroupProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupProvider.html).  The `SymbolGroupProvider` groups based on the [MappingName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolGroupProvider_MappingName) property, which has the name of the property whose value will be in the group category. In the following code example, the `MappingName` has a value of "Key" and the `SymbolGroupProvider` will create the group based on the value of the `Key` property. The symbols with the same category name could be grouped under that category.

{% tabs %}
{% highlight xaml %}

<Style TargetType="sync:Node">
 <Setter Property="ShapeStyle">
 <Setter.Value>
    <Style TargetType="Path">
      <Setter Property="Fill" Value="#FF5B9BD5"></Setter>
      <Setter Property="Stretch" Value="Fill"></Setter>
    </Style>
 </Setter.Value>
 </Setter>
</Style>
<Style TargetType="sync:Connector">
   <Setter Property="ConnectorGeometryStyle">
   <Setter.Value>
     <Style TargetType="Path">
       <Setter Property="Stroke" Value="#FF5B9BD5"></Setter>
     </Style>
   </Setter.Value>
  </Setter>
</Style>

<DataTemplate x:Key="TitleTemplate">
   <TextBlock x:Name="HeaderText" Text="{Binding}" FontSize="15" FontWeight="SemiBold"  Foreground="#2b579a" />
</DataTemplate>

<stencil:Stencil Grid.Column="0" BorderThickness="1" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}" BorderBrush="#dfdfdf" x:Name="stencil">
    <!--Initialize the SymbolSource-->
    <stencil:Stencil.SymbolSource>
    <!--Define the SymbolCollection-->
    <local:SymbolCollection>
        <syncfusion:NodeViewModel x:Name="node" UnitHeight="70" UnitWidth="100" OffsetX="100" OffsetY="100" Shape="{StaticResource Rectangle}" Key="Node">
        </syncfusion:NodeViewModel>
        <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200" Key="Connector"/>
        <!--Define the DiagramElement- Group-->
        <syncfusion:GroupViewModel Key="Group">
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
    </local:SymbolCollection>
</stencil:Stencil.SymbolSource>
    <!--Initialize the SymbolGroup-->
    <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
            <!--Map Symbols Using MappingName-->
            <stencil:SymbolGroupProvider MappingName="Key">
            </stencil:SymbolGroupProvider>
        </stencil:SymbolGroups>
    </stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}
{% highlight c# %}

//Define a Stencil.
Stencil stencil = new Stencil()
{
    ExpandMode =ExpandMode.All,
    BorderThickness =new Thickness(0,0,1,0),
    BorderBrush =new SolidColorBrush(Colors.Black)
};
//Define the SymbolSource with the SymbolCollection.
stencil.SymbolSource = new SymbolCollection();
NodeViewModel node = new NodeViewModel()
{
    UnitHeight = 100,
    UnitWidth = 100,
    OffsetX = 100, OffsetY = 100,
    Shape = App.Current.MainWindow.Resources["Rectangle"],
    Key = "Node"
};

ConnectorViewModel cvm = new ConnectorViewModel()
{
    SourcePoint = new Point(100, 100),
    TargetPoint = new Point(200, 200),
    Key="Connector"
};

GroupViewModel grp = new GroupViewModel()
            {
                Key="Group",
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

//Add the element to the symbol collection.
(stencil.SymbolSource as SymbolCollection).Add(node);
(stencil.SymbolSource as SymbolCollection).Add(cvm);
(stencil.SymbolSource as SymbolCollection).Add(grp);

//Define the SymbolGroups.
stencil.SymbolGroups = new SymbolGroups()
{
    new SymbolGroupProvider()
    {
        MappingName = "Key"
    }
};

{% endhighlight %}
{% endtabs %} 

![Symbol](Stencil_images/stencil2.PNG) 

### Customize the appearance of the symbol group header

You can customize the appearance of a `SymbolGroup` header by changing its style. The following code explains how to customize the appearance of the symbol group header.

{% tabs %}

{% highlight xaml %}

 <!--Style for Symbol Group-->
        <Style TargetType="stencil:SymbolGroup">
            <Setter Property="FontFamily" Value="Regular"/>
            <Setter Property="Background" Value="#ffffff"/>
            <Setter Property="Foreground" Value="#222222"/>
            <Setter Property="FontSize" Value="14"/>
            <Setter Property="HeaderTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <stencil:Header>
                            <stencil:Header.Template>
                                <ControlTemplate TargetType="stencil:Header">
                                    <Grid>
                                        <Border x:Name="header" Background="#f5f5f5" BorderBrush="#dfdfdf" 
                                                BorderThickness="1">
                                            <ContentPresenter Margin="10" Content="{Binding}"/>
                                        </Border>
                                    </Grid>
                                </ControlTemplate>
                            </stencil:Header.Template>
                        </stencil:Header>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>

{% endhighlight %}
 
{% endtabs %}

### Expand and collapse the symbol group

When there is more number of symbol groups in the stencil then you can expand and collapse the symbol groups using the [ExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ExpandMode) property of `Stencil.` The `ExpandMode` property allows you to decide the number of symbol groups that can be expanded in a stencil.

|ExpandMode|Description|
|----------|-----------|
|All       |    Enables or disables all the symbol group that can be expanded |
|One       |    Enables or disables only one symbol group that can be expanded |
|OneOrMore |    Enables or disables one or more symbol group that can be expanded |
|ZeroOrMore|    Enables or disables none or more symbol group that can be expanded |
|ZeroOrOne |    Enables or disables none or one symbol group that can be expanded |

## Symbol categories

There are plenty of shapes available in the diagram resource dictionary. It takes more time and allows repeated code samples to add all symbols to the stencil. To avoid this, the shapes are split and categorized as a list of symbols in the [StencilCategory](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.StencilCategory.html ) class. You can add more than one category using the [Categories](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_Categories) property of the stencil class.

The `Categories` can be mentioned by using the following properties of the `StencilCategory` class,

* Keys: Specifies the static resource key name value of the category collection.
* Title: Specifies the title that should be displayed as a header of the category collection.

### Built-in symbol categories 

The built-in shape paths available in the diagram resource dictionary are grouped by categories. The following are the built-in categories being available in the diagram resource dictionary:

* BasicShapes
* FlowShapes
* ArrowShapes
* DataFlowShapes
* UMLActivity
* UMLUseCase
* UMLRelationship
* ElectricalShapes
* SwimlaneShapes
* BPMNEditorShapes

{% tabs %}
{% highlight xaml %}
<!--Initialize the stencil-->
<Stencil:Stencil x:Name="stencil" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}"
ExpandMode="ZeroOrMore"                         BorderBrush="#dfdfdf"
BorderThickness="1">
   <!--Initialize the stencil categories-->
    <Stencil:Stencil.Categories>
     <Stencil:StencilCategoryCollection>
       <!--Specify the basic shapes category with title and resource key-->
       <Stencil:StencilCategory Title="Basic Shapes" Keys="{StaticResource BasicShapes}"/>
        </Stencil:StencilCategoryCollection>
        </Stencil:Stencil.Categories>
        <Stencil:Stencil.SymbolGroups>
        <Stencil:SymbolGroups>
          <!--Separate groups based on the key-->
          <Stencil:SymbolGroupProvider MappingName="Key" />
        </Stencil:SymbolGroups>
    </Stencil:Stencil.SymbolGroups>
</Stencil:Stencil>
{% endhighlight %}
{% endtabs %}

![Basic Shapes](Stencil_images/CategoryBasicShapes.png)

### Add the custom shapes categories

The custom symbol collections can be added to the stencil by defining the custom symbol's resource collection.

{% tabs %}
{% highlight xaml %}

<!--custom path data-->
<sys:String x:Key="CustomPath">
    F1M1.66,0.25C0.882,0.25,0.25,0.881,0.25,1.66L0.25,24.622C0.25,25.401,0.882,26.032,1.66,26.032L4.48,26.032C5.259,26.032,5.89,25.401,5.89,24.622L5.89,1.66C5.89,0.881,5.259,0.25,4.48,0.25z
</sys:String>

<!--custom shapes collection-->
<x:Array Type="sys:String" x:Key="customShapeCollection">
    <sys:String>Rectangle</sys:String>
    <sys:String>Cube</sys:String>
    <sys:String>Triangle</sys:String>
    <sys:String>Ellipse</sys:String>
    <sys:String>CustomPath</sys:String>
</x:Array>
<DataTemplate x:Key="TitleTemplate">
   <TextBlock x:Name="HeaderText" Text="{Binding}" FontSize="15" FontWeight="SemiBold"  Foreground="#2b579a" >
   </TextBlock>
</DataTemplate>
<!--Initialize the stencil-->
<Stencil:Stencil x:Name="stencil" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}" ExpandMode="ZeroOrMore"
BorderBrush="#dfdfdf"
BorderThickness="1">
    <!--Initialize the stencil categories-->
    <Stencil:Stencil.Categories>
        <Stencil:StencilCategoryCollection>
            <!--Specify the custom shapes category with title and resource key-->
            <Stencil:StencilCategory Title="Custom shapes" Keys="{StaticResource customShapeCollection}"/>
        </Stencil:StencilCategoryCollection>
    </Stencil:Stencil.Categories>
    <Stencil:Stencil.SymbolGroups>
        <Stencil:SymbolGroups>
        <!--Separate groups based on the key-->
        <Stencil:SymbolGroupProvider MappingName="Key" />
        </Stencil:SymbolGroups>
    </Stencil:Stencil.SymbolGroups>
</Stencil:Stencil>
{% endhighlight %}
{% endtabs %}

![Custom Shapes collection](Stencil_images/CustomShapes.png)

N> The custom symbol collections should be added in the App.xaml file.

### Customize the appearance of the symbols in the built-in categories 

The built-in symbol categories symbol sizes are equivalent to the Visio symbol size. Each symbol available in the category collection can be customized by the [PrepareSymbolViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_PrepareSymbolViewModel_System_Object_System_String_System_String_) virtual method of the stencil class. Symbols can be modified by using the following properties of the `PrepareSymbolViewModel` method,

* `Item`: To modify the symbol and its properties.
* `SymbolName`: To know the name of the symbol.
* `CategoryName`: To know the name of the category.

Also, you can decide whether a symbol can be added to the stencil symbol collection or not. It can be achieved by using the `Cancel` property of [CanAddSymbol](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_CanAddSymbol_System_String_System_String_) the virtual method of stencil class. 

{% tabs %}
{% highlight C# %}
/// <summary>
/// The custom class for the stencil view model.
/// </summary>
public class StencilViewModel : Stencil
{
    /// <summary>
    /// Overridden method to change the symbol.
    /// </summary>
    /// <param name="Item">Item value of the shape</param>
    /// <param name="SymbolName">Name of the symbol</param>
    /// <param name="CategoryName">Name of the category</param>
    /// <returns>Return the item of the shape</returns>
    protected override object PrepareSymbolViewModel(object Item, string SymbolName, string CategoryName)
    {
        if (SymbolName == "Rectangle")
        {
            (Item as INode).UnitWidth = 80;
            (Item as INode).UnitHeight = 40;
            return Item;
        }
        else
            return base.PrepareSymbolViewModel(Item, SymbolName, CategoryName);
    }

    /// <summary>
    /// Overidden method to decide whether a symbol can be added or not
    /// </summary>
    /// <param name="symbolName">Name of the symbol</param>
    /// <param name="categoryName">Name of the category</param>
    /// <returns>Return the boolean</returns>
    protected override bool CanAddSymbol(string symbolName, string categoryName)
    {
        if (symbolName == "Triangle")
        {
            return false;            
        }

        return base.CanAddSymbol(symbolName, categoryName);
    }
}

{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/StencilCategory)

## Filter the symbols based on groups/category 

The grouped symbols can be filtered or hide using the [SymbolFilters](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolFilters). The `SymbolFilters` are a collection of [SymbolFilterProvider](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html) which contains the [SymbolFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_SymbolFilter) delegate property to filter the specific symbol group.

The [Content](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_Content) and [ContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_ContentTemplate) property of the `SymbolFilterProvider` is used to update the content of the symbol filter.

The following code explains how to create a symbol filter in the stencil.

{% tabs %}
{% highlight xaml %}
<Window.DataContext>
   <viewmodel:StencilVM></viewmodel:StencilVM>
</Window.DataContext>
<Window.Resources>
        <DataTemplate x:Key="TitleTemplate">
            <TextBlock x:Name="HeaderText" Text="{Binding}" FontSize="15" FontWeight="SemiBold"  Foreground="#2b579a" >
            </TextBlock>
        </DataTemplate>
        <!--Style for Node-->
        <Style TargetType="{x:Type syncfusion:Node}">
            <Setter Property="ShapeStyle">
                <Setter.Value>
                    <Style  TargetType="Path">
                        <Setter Property="Fill" Value="#FF5B9BD5"/>
                        <Setter Property="Stroke" Value="#FFEDF1F6"/>
                        <Setter Property="StrokeThickness" Value="1"/>
                        <Setter Property="Stretch" Value="Fill"/>
                    </Style>
                </Setter.Value>
            </Setter>
        </Style>
        <!--Style for Connector-->
            <Style TargetType="{x:Type syncfusion:Connector}">
            <Setter Property="ConnectorGeometryStyle">
                <Setter.Value>
                    <Style TargetType="Path">
                        <Setter Property="Stroke" Value="#FF5B9BD5"></Setter>
                        <Setter Property="StrokeThickness" Value="1"></Setter>
                    </Style>
                </Setter.Value>
            </Setter>
            <Setter Property="TargetDecoratorStyle">
                <Setter.Value>
                    <Style TargetType="Path">
                        <Setter Property="Fill" Value="#FF5B9BD5"></Setter>
                        <Setter Property="StrokeThickness" Value="1"></Setter>
                    </Style>
                </Setter.Value>
            </Setter>
        </Style>
        <!--Style for Symbol-->
        <Style TargetType="stencil:Symbol">
            <Setter Property="Width" Value="100" />
            <Setter Property="Height" Value="100" />
            <Setter Property="BorderThickness" Value="1" />
            <Setter Property="Background" Value="Transparent" />
            <Setter Property="BorderBrush" Value="Transparent" />
            <Setter Property="Margin" Value="4"></Setter>
        </Style>
        <!--Style for Symbol Group-->
        <Style TargetType="stencil:SymbolGroup">
            <Setter Property="FontFamily" Value="Regular"/>
            <Setter Property="Background" Value="#ffffff"/>
            <Setter Property="Foreground" Value="#222222"/>
            <Setter Property="FontSize" Value="14"/>
            <Setter Property="HeaderTemplate">
                <Setter.Value>
                    <DataTemplate>
                        <stencil:Header>
                            <stencil:Header.Template>
                                <ControlTemplate TargetType="stencil:Header">
                                    <Grid>
                                        <Border x:Name="header" Background="#f5f5f5" BorderBrush="#dfdfdf" 
                                                BorderThickness="1">
                                            <ContentPresenter Margin="10" Content="{Binding}"/>
                                        </Border>
                                    </Grid>
                                </ControlTemplate>
                            </stencil:Header.Template>
                        </stencil:Header>
                    </DataTemplate>
                </Setter.Value>
            </Setter>
        </Style>
</Window.Resources>
<Grid>
  <Grid.ColumnDefinitions>
    <ColumnDefinition Width="2*"/>
    <ColumnDefinition Width="8*"/>
  </Grid.ColumnDefinitions>
  <!--Define the Stencil-->
   <stencil:Stencil Grid.Column="0" BorderThickness="1" BorderBrush="#dfdfdf" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}"  x:Name="stencil" ExpandMode="All" SymbolFilters="{Binding Symbolfilters}" SelectedFilter="{Binding Selectedfilter}">
     <!--Initialize the SymbolSource-->
     <stencil:Stencil.SymbolSource>
      <!--Initialize the SymbolCollection-->
      <local:SymbolCollection>
       <!--Define the DiagramElement-Node-->
        <syncfusion:NodeViewModel x:Name="node" UnitHeight="100" UnitWidth="100" OffsetX="100" OffsetY="100" Shape="{StaticResource Rectangle}" Key="Nodes">
          </syncfusion:NodeViewModel>
       <!--Define the DiagramElement- Connector-->
         <syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200" Key="Connector">
          </syncfusion:ConnectorViewModel>
      </local:SymbolCollection>
      </stencil:Stencil.SymbolSource>
       <!--Initialize the SymbolGroup-->
       <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
         <!--Map Symbols Using MappingName-->
         <stencil:SymbolGroupProvider MappingName="Key"></stencil:SymbolGroupProvider>
        </stencil:SymbolGroups>
       </stencil:Stencil.SymbolGroups>
     </stencil:Stencil>
</Grid>
{% endhighlight %}
{% highlight C# %}

public class StencilVM : INotifyPropertyChanged
{
   public StencilVM()
   {
     Symbolfilters = new SymbolFilters();
     SymbolFilterProvider all = new SymbolFilterProvider { Content = "All",  SymbolFilter = Filter };
     SymbolFilterProvider Node = new SymbolFilterProvider { Content = "Nodes", SymbolFilter = Filter };
     SymbolFilterProvider Con = new SymbolFilterProvider { Content = "Connector", SymbolFilter = Filter };

      this.Symbolfilters.Add(all);
      this.Symbolfilters.Add(Node);
      this.Symbolfilters.Add(Con);
      this.Selectedfilter = Symbolfilters[0];
   }

   // Define the filtering of symbols.
   private bool Filter(SymbolFilterProvider sender, object symbol)
   {
      if (symbol is NodeViewModel)
       {
         if (sender.Content.ToString() == (symbol as NodeViewModel).Key.ToString())
             return true;
       }

       if (symbol is ConnectorViewModel)
       {
        if (sender.Content.ToString() == (symbol as ConnectorViewModel).Key.ToString())
               return true;
        }
        if (sender.Content.ToString() == "All")
        {
          return true;
        }
        return false;
    }
   public ObservableCollection<SymbolFilterProvider> Symbolfilters { get; set; } 

   public SymbolFilterProvider Selectedfilter { get; set; }

   public event PropertyChangedEventHandler PropertyChanged;
}
{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/SymbolFilters-sample)

![SymbolFilter](Stencil_images/Stencil_img12.PNG)

### Appearance of symbol filters

The visual appearance of the symbol filters can be customized to either a combo box or list view. The [SymbolFilterDisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolFilterDisplayMode) property of the `Stencil` is used to customize the appearance of the symbol filter.

|SymbolFilterDisplayMode|Description|
|----------|-----------|
| ComboBox | The symbol filter is visually represented in a combo box.  |
| List | The symbol filter are visually represented in a listview |

In `List` display mode,  the filters will be added in the list view only when you set the [IsChecked](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolFilterProvider.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolFilterProvider_IsChecked) property of the `SymbolFilterProvider` to `true.` You can dynamically add or remove the filter from the list view, by clicking the **more shapes** option and checked or unchecked the filter to add or remove that filter from the list view.  Check marks indicate the filters added to the List.

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil_ListView)

 ![Symbol](Stencil_images/StencilImprovement.GIF) 

### SelectedFilter

There can be multiple SymbolFilters but only one filter can be selected at a time. You can select the filter from the collection of filters using the [SelectedFilter](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SelectedFilter) of the stencil. In the combo box, a particular item will be selected and updated that item to the SelectedFilter. In List view, the selected item will be updated as a SelectedFilter.

## Add a title to the Stencil

The [Title](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_Title) property of the `Stencil` is used to add the title to the stencil. Please find the following code example that explains how to provide the content to the stencil.

{% tabs %}

{% highlight xaml %}
<!--Initialize the stencil-->
<Stencil:Stencil x:Name="stencil" Title="Shapes">
    <!--Initialize the stencil categories-->
    <Stencil:Stencil.Categories>
        <Stencil:StencilCategoryCollection>
            <!--Specify the basic shapes category with a title and resource key-->
            <Stencil:StencilCategory Title="Basic Shapes" Keys="{StaticResource BasicShapes}"/>
        </Stencil:StencilCategoryCollection>
    </Stencil:Stencil.Categories>
</Stencil:Stencil>

{% endhighlight %}
 
{% endtabs %}

![Symbol](Stencil_images/Stencil_Title.PNG) 

### Customize Stencil title

The appearance of the title can be customized by using the  [TitleTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_TitleTemplate) property of the `Stencil.`

Please find the code example that explains how to add a title and its customization.

 {% tabs %}
{% highlight xaml %}
<DataTemplate x:Key="TitleTemplate">
  <StackPanel Orientation="Horizontal">
   <Image Source="/Image/Shapes.png"
      Width="15" Height="15" />
   <TextBlock Margin="5,0,0,0" HorizontalAlignment="Center"
    VerticalAlignment="Center"                        Text="Shapes" />
  </StackPanel>
</DataTemplate>

<!--Initialize the stencil-->
<Stencil:Stencil x:Name="stencil" Title="Shapes" TitleTemplate="{StaticResource TitleTemplate}>
    <!--Initialize the stencil categories-->
    <Stencil:Stencil.Categories>
        <Stencil:StencilCategoryCollection>
            <!--Specify the basic shapes category with a title and resource key-->
            <Stencil:StencilCategory Title="Basic Shapes" Keys="{StaticResource BasicShapes}"/>
        </Stencil:StencilCategoryCollection>
    </Stencil:Stencil.Categories>
</Stencil:Stencil>
{% endhighlight %}
{% endtabs %}

![Symbol](Stencil_images/Stencil_TitleTemplate.PNG) 

## Browse the symbols from the stencil 

You can search for symbols in the stencil by entering the symbol name (e.g: "rectangle") in the search text box and start searching. The symbols are resulted by matching the value of the `Name` property with the string entered in the search textbox. The [ShowSearchTextBox](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ShowSearchTextBox) property of the `Stencil` is used to show or hide the search textbox in a stencil. 

The following image shows the search result of the symbol.

 ![Symbol](Stencil_images/Stencil_Search_Textbox.GIF) 

## Stencil display mode

The Stencil view can be toggled between the expanded and compact modes by clicking the expander at the top right corner of the Stencil during run-time. You can do the same using the [DisplayMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_DisplayMode) property of the `Stencil.`

|DisplayMode|Description|
|----------|-----------|
| Compact | The stencil always shows as a narrow sliver which can be opened to full width |
| Expanded | Specifies to update the Expanded state of the stencil |

You can show or hide the expander icon by using the [ShowDisplayModeToggleButton](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_ShowDisplayModeToggleButton) property of the `Stencil.` 

![Symbol](Stencil_images/Stencil_Compact.PNG) 

## Preview for Drag and Drop

When you drag an item from the Stencil to the diagram, a preview of the dragged item will be displayed. Preview of the item can be enabled or disabled by using the [StencilConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html) `ShowPreview.`

{% highlight C# %}

//Enables the drag and drop preview.
stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;

//Disables the drag and drop preview.
stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;

{% endhighlight %}

Here, the stencil is an instance of Stencil.

![Preview](Stencil_images/Stencil_img14.PNG)

#### Customization of Preview for drag and drop

You can customize the preview content by overriding the [PrepareDragDropPreview](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_PrepareDragDropPreview) method of the Stencil. You can define your customized preview to the [SymbolPreview](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolPreview) property of the stencil.

{% tabs %}
{% highlight C# %}
public class CustomStencil : Stencil
{
    //Virtual method to customize the preview of dragging the symbol from a stencil.
    protected override void PrepareDragDropPreview()
    {
        this.SymbolPreview = new ContentPresenter()
        {
            Content = new Rectangle()
            {
                Width = 50,
                Height = 50,
                Fill = new SolidColorBrush(Colors.SteelBlue)
            }
        };
    }
}

{% endhighlight %}
{% endtabs %}

![CustomPreview](Stencil_images/Stencil_img16.jpeg)

## Events

* The `Expanded Event` and `Collapsed Event` are notified to provide interactions in the SymbolGroup. To explore about arguments, refer to the [SymbolGroupExpandCollapseEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupExpandCollapseEventArgs.html)

* The `DragEnter Event` notifies when an element enters into the diagram from a stencil.
* The `DragLeave Event` notifies when an element leaves from the diagram.
* The `DragOver Event` notifies when an element drag over another diagram element.
* The `ItemDropEvent Event` notifies when an element is dropped on the diagram. 

To explore about arguments, refer to the [ItemDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html)


## Restrict the node dropped on Diagram

The diagram provides support to cancel the drag and drop operation from the stencil to the diagram in two ways.
* Using the `Cancel` argument of `ItemDropEventArgs`. For example, if you need to restrict drop for a particular node or based on some condition, then this argument will allow you to achieve the same. To explore about arguments, refer to the [ItemDropEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemDropEventArgs.html).
 
* When the ESC key is pressed.

## Symbol dragging outside diagram bounds

By default, the cursor appears as a block cursor when dragging the symbol (from stencil) outside the diagram bounds. The SfDiagram provides supports to drag the elements within the given limitations. For details, please refer to the [Dragging based on DragLimit](https://help.syncfusion.com/wpf/diagram/interaction/drag#dragging-based-on-draglimit)

## Preserving the node template when drag and drop

The SfDiagram using the serialization and deserialization approach for drag and drop the element from a stencil and it did not serialize the framework properties like the Content and ContentTemplate properties. So, you need to retain templates as a resource and reassign them once it loaded back in the diagram. This can be achieved by using the ItemAdded event to restore the Content and ContentTemplate property values.

{% tabs %}
{% highlight C# %}

private void MainWindow_ItemAdded(object sender, ItemAddedEventArgs args) 
{ 
    if(args.Item is CustomNode) 
    { 
        CustomNode node = args.Item as CustomNode; 
        node.Content = node.CustomContent; 
        node.ContentTemplate = App.Current.MainWindow.Resources[node.CustomContentTemplate] asDataTemplate; 
    } 
} 

{% endhighlight %}
{% endtabs %}

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/Stencil%20Drag%20Drop%20Template)

## Constraints

The `Constraints` property of stencil allows you to enable or disable certain features. For more information about stencil constraints, refer to the [StencilConstraints](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html).

## See Also

* [How to drag and drop elements from a treeview ?](https://www.syncfusion.com/kb/10574/how-to-drag-and-drop-elements-from-treeview-in-wpf-diagramsfdiagram)
* [How to refresh the stencil when adding a new symbol in the symbol source ?](https://www.syncfusion.com/kb/9928/how-to-refresh-the-stencil-when-adding-new-symbol-in-symbol-source)
* [How to host different UI elements as a node content ?](https://www.syncfusion.com/kb/9456/how-to-host-different-ui-elements-as-node-content)
* [How to notify stencil has been loaded ?](https://www.syncfusion.com/kb/6256/how-to-notify-stencil-has-been-loaded)
* [How to expand all SymbolGroups ?](https://www.syncfusion.com/kb/5878/how-to-expand-all-symbolgroups)
* [How to get the base node interface while dropping a Symbol from Stencil to SfDiagram ?](https://www.syncfusion.com/kb/5880/how-to-get-the-base-node-interface-while-dropping-a-symbol-from-the-stencil-to-the)
* [How to use different User Controls into Stencil?](https://www.syncfusion.com/kb/11459/how-to-use-different-user-controls-into-stencil-in-the-wpf-diagramsfdiagram)
