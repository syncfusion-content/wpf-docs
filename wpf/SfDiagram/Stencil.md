---
layout: post
title: Define and add the frequently used Nodes/Connectors to the Stencil.
description: How to add Symbol to the Stencil and drag and drop them over the drawing area?
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil

Stencil has a collection of Symbols and it is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram.

Namespace for Stencil

{% highlight xaml %}

xmlns:stencil="using:Syncfusion.UI.Xaml.Diagram.Stencil"

{% endhighlight %}

![](Stencil_images/Stencil_img1.jpeg)

## Symbol

Symbol is used to visualize the elements in Stencil, by following ways:
 
 * ISymbol
 * Using DiagramElements

### Using ISymbol

ISymbol have `Symbol` and `SymbolTemplate` to visualize the Symbol.

{% highlight C# %}
public class SymbolItem : ISymbol
{
 //Symbol-Any Object
 public object Symbol { get; set; }

 //Custom property for Mapping.
 public object GroupName { get; set; }

 //Data template to visualize the object.
 public DataTemplate SymbolTemplate { get; set; }

 //For cloning the symbol from the given object and data template.
 public ISymbol Clone()
 {
  return new SymbolItem()
  {
   Symbol = this.Symbol,
   SymbolTemplate = this.SymbolTemplate
  };
 }
 public object Key { get; set; }
}

{% endhighlight %}

{% tabs %}

{% highlight xaml %}
 <local:SymbolItem GroupName="Flow Chart" Symbol="Diamond" SymbolTemplate="{StaticResource Diamond}"/>
 
 {% endhighlight %}
 {% endtabs %}
 
 {% tabs %}
 {% highlight c# %}
 
//Initialize the SymbolItem
SymbolItem symbol = new SymbolItem();

 {% endhighlight %}
 {% endtabs %}
 
#### Define SymbolSource

`SymbolSource` is the property of Stencil which is Collection of objects (i.e,Symbol,Node,Connector etc..). Based on the SymbolSource, the Stencil will populate the Symbols.

{% tabs %}
{% highlight c# %}
//Adding ISymbol to SymbolCollection
public class SymbolCollection : ObservableCollection<ISymbol>
{
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<Window.Resources>
    <DataTemplate x:Key="Diamond">
        <Path Stretch="Fill" Data="M 397.784,287.875L 369.5,316.159L 341.216,287.875L 369.5,259.591L 397.784,287.875 Z" Fill="White"
Stroke="Black" StrokeThickness="1" />
    </DataTemplate>
</Window.Resources>
<Grid >
    <!--Define the Stencil Element-->
    <stencil:Stencil x:Name="stencil" BorderBrush="#dfdfdf" BorderThickness="1" >
        <!--Initialize the SymbolSource-->
        <stencil:Stencil.SymbolSource>
            <!--Define the SymbolCollection-->
            <local:SymbolCollection>
                <!--Symbol with SymbolTemplate-->
                <local:SymbolItem GroupName="Flow Chart" Symbol="Diamond"  SymbolTemplate="{StaticResource Diamond}"/>
            </local:SymbolCollection>
        </stencil:Stencil.SymbolSource>
        <!--Define the SymbolGroups-->
        <stencil:Stencil.SymbolGroups>
            <stencil:SymbolGroups>
                <stencil:SymbolGroupProvider MappingName="GroupName">
                </stencil:SymbolGroupProvider>
            </stencil:SymbolGroups>
        </stencil:Stencil.SymbolGroups>
    </stencil:Stencil>
</Grid>

{% endhighlight %}
{% endtabs %}


![](Stencil_images/Stencil_img2.jpeg)

### Using DiagramElements

DiagramElements such as Node, Connector and Group can be used to visualize the Symbol.
 
 {% tabs %} 
{% highlight xaml %}
<Grid>
    <!--Define the Stencil-->
    <stencil:Stencil Grid.Column="0" BorderThickness="1" BorderBrush="#dfdfdf" x:Name="stencil">
        <!--Initialize the SymbolSource-->
        <stencil:Stencil.SymbolSource>
            <!--Initialize the SymbolCollection-->
     <local:SymbolCollection>
                <!--Define the DiagramElement-Node-->
                <syncfusion:NodeViewModel x:Name="node" UnitHeight="100" UnitWidth="100" OffsetX="100" OffsetY="100" Shape="{StaticResource Rectangle}" Key="Nodes">
                </syncfusion:NodeViewModel>
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
</Grid>

{% endhighlight %}
{% endtabs %}

![](Stencil_images/Stencil_img17.jpeg)

## Symbol Groups

The `SymbolGroupProvider` groups the symbols into SymbolGroup based on the MappingName property.

{% tabs %}
{% highlight xaml %}

<stencil:Stencil x:Name="stencil" ExpandMode="All" 
		         SymbolSource="{StaticResource Collection}">
    <!--Initialize the SymbolGroup-->
    <stencil:Stencil.SymbolGroups>
        <stencil:SymbolGroups>
            <!--Map Symbols Using MappingName-->
            <stencil:SymbolGroupProvider MappingName="Key"></stencil:SymbolGroupProvider>
        </stencil:SymbolGroups>
    </stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}
{% endtabs %}

![](Stencil_images/Stencil_img3.jpeg)

## Symbol Filters

`SymbolFilterProvider` is used to filter or hide the symbols by using delegates. SymbolFilters are the collection of SymbolFilterProvider.

{% tabs %}
{% highlight C# %}
// Define filtering of Symbols
private bool Filter(SymbolFilterProvider sender, object symbol)
     {
          if (symbol is NodeViewModel)
              {
                  if (sender.Content.ToString() == (symbol as NodeViewModel).Key.ToString())
                  return true;
              }
     }

{% endhighlight %}
{% endtabs %}

for Sample, refer to [SymbolFilter](http://www.syncfusion.com/downloads/support/directtrac/198906/ze/SymbolFilter-1471608955 "SymbolFilter")

![](Stencil_images/Stencil_img12.jpeg)

### SelectedFilter

There can be multiple SymbolFilters, but only one filter can be selected at a time. These SymbolFilters are visually represented in a combo box. When the selected item is changed in the combo box, SelectedFilter is updated accordingly.

![](Stencil_images/Stencil_img13.jpeg)

## Preview for Drag and Drop

When you drag an item from Stencil to Diagram, a preview of the dragged item will be displayed.

{% highlight C# %}

//Enables the drag and drop preview.
stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;

//Disables the drag and drop preview.
stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;

{% endhighlight %}

Here, Stencil is an instance of Stencil.

#### Preview of the dragging Symbol

![](Stencil_images/Stencil_img14.jpeg)

#### Dragged Symbol

![](Stencil_images/Stencil_img15.jpeg)

#### Customization of Preview for Drag and Drop

You can customize the preview content by overriding the PrepareDragDropPreview method of the Stencil feature. The following code example illustrates how to customize preview content.

{% tabs %}
{% highlight C# %}
public class CustomStencil : Stencil
    {
        //Virtual method to customize the preview of dragging the symbol from Stencil.
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

![](Stencil_images/Stencil_img16.jpeg)

## Events

Expand Event and Collapse Event are notified to provide interaction in SymbolGroup.

Following table describes stencil related events.

| Event | Description | Arguments |
|---|---|---|
| ExpandEvent | Occurs when expand the symbol group in the Stencil. | On which the `ExpandEvent` is raised. | 
| CollpaseEvent | Occurs when collapse the symbol group in the Stencil. | On which the `CollapseEvent` is raised. |

#### ExpandMode
 please refer to, [ExpandMode](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.Stencil.Stencil_members.html "ExpandMode")