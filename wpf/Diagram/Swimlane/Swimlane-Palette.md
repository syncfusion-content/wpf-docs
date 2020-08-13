---
layout: post
title: Visualize graphical object using Swimlanes | Syncfusion
description: How to add the lanes and phases to the stencil and drag and drop them over the drawing area and its interaction?
platform: wpf
control: SfDiagram
documentation: ug
---

# Swimlane items in Stencil
  Diagram provides support to add lanes and phases to Stencil. 

## Add lanes and phases into stencil

Diagram elements such as [Lane](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.LaneViewModel.html), and [Phase](https://help.syncfusion.com/cr/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PhaseViewModel.html) can be used to visualize the Symbol.

 The following code sample shows how to add the lanes and phases to palette.

{% tabs %}
{% highlight xaml %}
 <syncfusion:Stencil x:Name="stencil"                             BorderThickness="0,0,1,0" ExpandMode="All">
     <syncfusion:Stencil.SymbolSource>
         <syncfusion:SymbolCollection>
        <!--Rendered HorizontalSwimlane-->
         <syncfusion:LaneViewModel ID="HorizontalSwimlane" Key="Swimlane Shapes" Orientation="Horizontal" ></syncfusion:LaneViewModel>
         <!--Rendered VerticalSwimlane-->
        <syncfusion:LaneViewModel ID="VerticalSwimlane" Key="Swimlane Shapes" Orientation="Vertical" ></syncfusion:LaneViewModel>
         <!--Rendered HorizontalPhase-->
        <syncfusion:PhaseViewModel ID="HorizontalPhase" Key="Swimlane Shapes" Orientation="Horizontal" ></syncfusion:PhaseViewModel>
        <!--Rendered VerticalPhase-->
        <syncfusion:PhaseViewModel ID="VerticalPhase" Key="Swimlane Shapes" Orientation="Vertical"></syncfusion:PhaseViewModel>
                        </syncfusion:SymbolCollection>
                    </syncfusion:Stencil.SymbolSource>
         <syncfusion:Stencil.SymbolGroups>
             <syncfusion:SymbolGroups>
               <!--Separate groups based on the key-->
             <syncfusion:SymbolGroupProvider MappingName="Key"/>
         </syncfusion:SymbolGroups>
    </syncfusion:Stencil.SymbolGroups>
 </syncfusion:Stencil>

{% endhighlight %}
{% endtabs %}

![Swimlane SymbolPalette Shapes](Swimlane-images/Swimlane_SymbolPalette.PNG)

## Add Swimlane shapes to palette using the category

You can add the swimlane shapes using the category. For more information, refer to the [Symbol categories](/wpf/sfdiagram/stencil#symbol-categories "Symbol categories"). 

## Interactions

* The drag and drop support for swimlane shapes have been provided.
* When you drag and drop the lane shape, if the diagram already contains swimlane with the same orientation, the lane will be added and stacked inside a swimlane based on the order. Otherwise, it will be added a new swimlane.
* The phase will only drop on the swimlane shape with the same orientation.
The following image shows how to drag symbol from palette.

![Drag Symbol from Palette](Swimlane-images/Symbol_palette.gif)
