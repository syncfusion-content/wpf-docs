---
layout: post
title: Visualize graphical object using Swimlanes | Syncfusion
description: How to visually represent the geometrical information and process flows as swimlanes and how to customize their appearance?
platform: wpf
control: SfDiagram
documentation: ug
---

# Swimlane in WPF Diagram(SfDiagram)

A [Swimlane](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Swimlane.html) is a type of diagram nodes, which is typically used to visualize the relationship between a business process and the department responsible for it by focusing on the logical relationships between activities.

![Swimlane Content](Swimlane-images/Swimlane_Default.PNG)

## Create a swimlane
A swimlane can be created and added to the diagram, either programmatically or interactively. 

### Add Swimlane through the Swimlanes collection 

To create a swimlane, you have to define the swimlane object and add that to the [Swimlanes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SfDiagram.html#Syncfusion_UI_Xaml_Diagram_SfDiagram_Swimlanes) collection of the diagram.

>Note: By default, if you create a swimlane, one lane and phase will be added.

{% tabs %}
{% highlight xaml %}
<!-- Initialize the Sfdiagram -->
 <syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Swimlanes>
        <!-- Initialize the SwimlaneCollection -->
         <syncfusion:SwimlaneCollection>
          <!--Initialize the Swimlane-->
            <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  
                UnitHeight="120" UnitWidth="450"/>           
         </syncfusion:SwimlaneCollection>
    </syncfusion:SfDiagram.Swimlanes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the SwimlaneCollection to SfDiagram
diagram.Swimlanes = new SwimlaneCollection();

//Creating the SwimlaneViewModel
SwimlaneViewModel swimlane = new SwimlaneViewModel()
{
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
};

//Add Swimlane to the Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

Now, the swimlane will be as follows.

![Add swimlane](Swimlane-images/Swimlane_Empty.PNG)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/SwimlaneCreation)


### Swimlane Header

The Swimlane Header was the primary element for swimlanes. The [`Header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneViewModel_Header) property of swimlane allows you to define its textual description and to customize its appearance.

>Note: By using this header,the swimlane interaction will be performed,like selection, dragging,and more.

The following code example explains how to define the swimlane header.

{% tabs %}
{% highlight xaml %}
 <!-- Initialize the Sfdiagram -->
<syncfusion:SfDiagram x:Name="diagram">
            <syncfusion:SfDiagram.Swimlanes>
                <!-- Initialize the SwimlaneCollection -->
                <syncfusion:SwimlaneCollection>
                    <!--Initialize the Swimlane-->
                    <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  
                UnitHeight="120" UnitWidth="450">
                  <!--Initialize the Swimlane Header-->
                        <syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneHeader UnitHeight="32" >
                                <syncfusion:SwimlaneHeader.Annotation>
                                    <syncfusion:AnnotationEditorViewModel Content="SALES PROCESS FLOW CHART"></syncfusion:AnnotationEditorViewModel>
                                </syncfusion:SwimlaneHeader.Annotation>
                            </syncfusion:SwimlaneHeader>
                        </syncfusion:SwimlaneViewModel.Header>
                    </syncfusion:SwimlaneViewModel>
                </syncfusion:SwimlaneCollection>
            </syncfusion:SfDiagram.Swimlanes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
  //Initialize the SfDiagram
  SfDiagram diagram = new SfDiagram();
 //Initialize the SwimlaneCollection to SfDiagram
 diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
 };
 //Creating header for SwimlaneViewModel
 swimlane.Header = new SwimlaneHeader()
 {
    UnitHeight = 32,
    Annotation = new AnnotationEditorViewModel()
    {
        Content = "SALES PROCESS FLOW CHART"
    }
 };

//Add Swimlane to the Swimlanes property of the diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

![Swimlane Header](Swimlane-images/Swimlane_Header.PNG)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Header)

### Customization of headers

The height and width of swimlane header can be customized with the [`UnitWidth`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildViewModel_UnitWidth) and [`UnitHeight`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildViewModel_UnitHeight) properties of swimlane header. Set fill color of header by using the [`ShapeStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneChildViewModel_ShapeStyle) property. 

The following code example explains how to customize the swimlane header.

{% tabs %}
{% highlight xaml %}

<Style x:Key="SwimlaneHeaderStyle" TargetType="Path">
   <Setter Property="Fill" Value="CadetBlue"/>
   <Setter Property="Stretch" Value="Fill"/>
   <Setter Property="Stroke" Value="#41719C"/>
   <Setter Property="StrokeThickness" Value="1"/>
</Style>
  <!--Template overriding for view template-->
 <DataTemplate x:Key="viewTemplate">
   <TextBlock Text="{Binding Path=Content, Mode=TwoWay}" 
               FontStyle="Italic" FontSize="12" 
               FontFamily="TimesNewRomen" 
               TextDecorations="Underline" 
               FontWeight="Bold" 
               Foreground="AliceBlue"/>
</DataTemplate>

 <!-- Initialize the Sfdiagram -->
 <syncfusion:SfDiagram x:Name="diagram">
            <syncfusion:SfDiagram.Swimlanes>
                <!-- Initialize the SwimlaneCollection -->
                <syncfusion:SwimlaneCollection>
                    <!--Initialize the Swimlane-->
                    <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150" Orientation="Horizontal" 
                UnitHeight="120" UnitWidth="450">
                        <syncfusion:SwimlaneViewModel.Header>
                         <!--Initialize the Swimlane Header-->
                            <syncfusion:SwimlaneHeader UnitHeight="32" ShapeStyle="{StaticResource SwimlaneHeaderStyle}">
                                <syncfusion:SwimlaneHeader.Annotation>
                                    <syncfusion:AnnotationEditorViewModel Content="SALES PROCESS FLOW CHART" ViewTemplate="{StaticResource viewTemplate">
                                    </syncfusion:AnnotationEditorViewModel>
                                </syncfusion:SwimlaneHeader.Annotation>
                            </syncfusion:SwimlaneHeader>
                        </syncfusion:SwimlaneViewModel.Header>
                    </syncfusion:SwimlaneViewModel>
                </syncfusion:SwimlaneCollection>
            </syncfusion:SfDiagram.Swimlanes>
        </syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
  //Initialize the SfDiagram
  SfDiagram diagram = new SfDiagram();
 //Initialize the SwimlaneCollection to SfDiagram
 diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
  Orientation=Orientation.Horizontal,
 };
 //Creating header for the SwimlaneViewModel
 swimlane.Header = new SwimlaneHeader()
 {
    UnitHeight = 32,
    Annotation = new AnnotationEditorViewModel()
    {
        Content = "SALES PROCESS FLOW CHART",
        ViewTemplate=this.Resources["viewTemplate"] as DataTemplate
    },
    ShapeStyle=this.Resources["SwimlaneHeaderStyle"] as Style,
 };

//Add Swimlane to the Swimlanes property of the diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

![Swimlane Header Customization](Swimlane-images/Swimlane_Header_Customization.PNG)

### Header editing

The diagram provides the support to edit swimlane headers at runtime. You can achieve the header editing by double clicking on it. Double clicking the header label will enables the editing mode.
The following image shows how to edit the swimlane header.

![Header Editing](Swimlane-images/Header_Edit.gif).

## Orientation

The orientation of swimlane can be customized with the [`Orientation`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel.html#Syncfusion_UI_Xaml_Diagram_SwimlaneViewModel_Orientation) property of the header.

>Note: By default the swimlane orientation has Horizontal.

The following code example explains how to set the orientation of the swimlane.

{% tabs %}
{% highlight xaml %}
<!-- Initialize the Sfdiagram -->
 <syncfusion:SfDiagram x:Name="diagram">
    <syncfusion:SfDiagram.Swimlanes>
        <!-- Initialize the SwimlaneCollection -->
         <syncfusion:SwimlaneCollection>
          <!--Initialize the Swimlane-->
            <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  Orientation="Horizontal"
                UnitHeight="120" UnitWidth="450"/>           
         </syncfusion:SwimlaneCollection>
    </syncfusion:SfDiagram.Swimlanes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}

//Initialize the SfDiagram
SfDiagram diagram = new SfDiagram();
//Initialize the SwimlaneCollection to SfDiagram
diagram.Swimlanes = new SwimlaneCollection();

//Creating the SwimlaneViewModel
SwimlaneViewModel swimlane = new SwimlaneViewModel()
{
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
  Orientation=Orientation.Horizontal,
};

//Add Swimlane to the Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

| Orientation | Output |
|---|---|
| Horizontal | ![Horizontal](Swimlane-images/Swimlane_Horizontal.PNG) |
| Vertical | ![Vertical](Swimlane-images/Swimlane_Vertical.PNG) |


## Interaction

### Select

Swimlane can be selected by clicking (tap) the header of the swimlane.

* The `IsSelected` Property is used to select or unselect the swimlane at runtime.

* The `ItemSelectingEvent` and `ItemSelectedEvent` for selecting an element, will notify you the item and its original source. To explore about arguments, refer to the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [ItemSelectedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.ItemSelectedEventArgs.html).

* The `ItemUnselectingEvent` and `ItemUnselectedEvent` for unselecting an element, will notify you the item and its original source. To explore about arguments, refer to the [DiagramPreviewEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramPreviewEventArgs.html) and [DiagramEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.DiagramEventArgs.html).

### Drag  

* Selected object can be dragged by clicking and dragging the header of the swimlane. 

* Instead of dragging original object, preview of the node alone can be dragged. For preview dragging, refer to the [PreviewSettings](https://help.syncfusion.com/wpf/sfdiagram/preview-settings). 

* The `NodeChangedEvent` will notify the `OffsetX` and `OffsetY` changes with their old and new values. Along with that, this event will give information about interaction state. To explore about arguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) .

![Drag Node](Swimlane-images/Swimlane_Select_Drag.gif)


Please find the swimlane sample as follows.

[View Swimlane sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane-Sample)