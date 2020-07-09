---
title: "Swimlane"
component: "Diagram"
description: "Nodes visually represents the geometrical information and process flows."
---

# Swimlane in WPF Diagram(SfDiagram)

[Swimlane](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.Swimlane.html) is a type of diagram nodes,which is typically used to visualize the relationship between a business process and the department responsible for it by focusing on the logical relationships between activities.

![Swimlane Content](Swimlane-images/Swimlane_Default.PNG)

## Create a swimlane
A swimlane can be created and added to the Diagram, either programmatically or interactively. Swimlanes are stacked on the Diagram area from bottom to top in the order they are added.

### Add Swimlane through Swimlanes collection 

To create a swimlane, you have to define the swimlane object and add that to Swimlanes collection of the Diagram.

>Note: by default, if we create a swimlane, one lane and phase will be added.

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
//Initialize SwimlaneCollection to SfDiagram
diagram.Swimlanes = new SwimlaneCollection();

//Creating the SwimlaneViewModel
SwimlaneViewModel swimlane = new SwimlaneViewModel()
{
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
};

//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

Now, swimlane will be as follows.

![Add swimlane](Swimlane-images/Swimlane_Empty.PNG)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/SwimlaneCreation)


### SwimlaneHeaders

SwimlaneHeader was the primary element for swimlanes. The [`Header`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Header.html) property of swimlane allows you to define its textual description and to customize its appearance.

>Note: By using this header,the swimlane interaction will be performed,like selection, dragging,etc.

The following code example illustrates how to define a swimlane header.

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
                        <syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneHeader UnitHeight="32" >
                                <syncfusion:SwimlaneHeader.Annotation>
                                    <syncfusion:AnnotationEditorViewModel Content="Swimlane"></syncfusion:AnnotationEditorViewModel>
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
 //Initialize SwimlaneCollection to SfDiagram
 diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
  UnitWidth = 450,
  UnitHeight = 120,
  OffsetX = 300,
  OffsetY = 150,
 };
 //Creating Header for SwimlaneViewModel
 swimlane.Header = new SwimlaneHeader()
 {
    UnitHeight = 32,
    Annotation = new AnnotationEditorViewModel()
    {
        Content = "Swimlane"
    }
 };

//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

![Swimlane Header](Swimlane-images/Swimlane_Header.PNG)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Header)

### Customization of headers

The height and width of swimlane header can be customized with [`UnitWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitWidth.html) and [`UnitHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitHeight.html) properties of swimlane header. Set fill color of header by using the [`ShapeStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~ShapeStyle.html) property. The orientation of swimlane can be customized with the [`Orientation`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Orientation.html) property of the header.

>Note: By default the swimlane orientation has Horizontal.

The following code example illustrates how to customise the swimlane header.

{% tabs %}
{% highlight xaml %}

<Style x:Key="SwimlaneHeaderStyle" TargetType="Path">
   <Setter Property="Fill" Value="#FF5B9BD5"/>
   <Setter Property="Stretch" Value="Fill"/>
   <Setter Property="Stroke" Value="#41719C"/>
   <Setter Property="StrokeThickness" Value="1"/>
</Style>

 <!-- Initialize the Sfdiagram -->
 <syncfusion:SfDiagram x:Name="diagram">
            <syncfusion:SfDiagram.Swimlanes>
                <!-- Initialize the SwimlaneCollection -->
                <syncfusion:SwimlaneCollection>
                    <!--Initialize the Swimlane-->
                    <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150" Orientation="Horizontal" 
                UnitHeight="120" UnitWidth="450">
                        <syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneHeader UnitHeight="32" ShapeStyle="{StaticResource SwimlaneHeaderStyle}">
                                <syncfusion:SwimlaneHeader.Annotation>
                                    <syncfusion:AnnotationEditorViewModel Content="Swimlane"></syncfusion:AnnotationEditorViewModel>
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
 //Initialize SwimlaneCollection to SfDiagram
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
 //Creating Header for SwimlaneViewModel
 swimlane.Header = new SwimlaneHeader()
 {
    UnitHeight = 32,
    Annotation = new AnnotationEditorViewModel()
    {
        Content = "Swimlane"
    },
    ShapeStyle=this.Resources["SwimlaneHeaderStyle"] as Style,
 };

//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %} 

![Swimlane Header Customization](Swimlane-images/Swimlane_Header_Customization.PNG)

### Header editing

Diagram provides the support to edit swimlane headers at runtime. We achieve the header editing by double click on it. Double clicking the header label will enables the editing mode.
The following image illustrates how to edit the swimlane header.

![Header Editing](Swimlane-images/Header_Edit.gif).

### Header Selection and Resize

 * We can select the individual lane and phase header by click on Header twice. For first click, the respective lane or phase can select. 

 * We can support to resize the individual lane and phase header. While resizing lane or phase, it has maintain 20px distances from Lane children.
 * The `NodeChangedEvent` will notify the `UnitHeight` and `UnitWidth` changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) 

 The following image illustrates how to select and resize the lane and phase header.

![Header Select and Resize](Swimlane-images/Header_Selection_Resize.gif).

## Lanes

Lane is a functional unit or a responsible department of a business process that helps to map a  process within the functional unit or in between other functional units.

The number of [`Lanes`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Lanes.html) can be added to swimlane. The lanes are automatically stacked inside  swimlane based on the order they are added.

### Create an empty lane

* We can create the lanes and add into Lanes collection of the Swimlane.

>Note: For Horizontal Swimlane, we must set the UnitHeight of the Lane. For Vertical Swimlane, we must set UnitWidth of the Lane.

The following code example illustrates how to define a swimlane with lane.

{% tabs %}
{% highlight xaml %}

   <syncfusion:SfDiagram x:Name="diagram" >
                <syncfusion:SfDiagram.Swimlanes>
                     <!--Initialize the SwimlaneCollection--> 
                    <syncfusion:SwimlaneCollection>
                        <!--Initialize the Swimlane-->
                        <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  
                UnitHeight="120" UnitWidth="450">
                            <!--Create a header for Swimlane-->
                            <syncfusion:SwimlaneViewModel.Header>
                                <syncfusion:SwimlaneHeader UnitHeight="32" >
                                    <syncfusion:SwimlaneHeader.Annotation>
                                        <syncfusion:AnnotationEditorViewModel Content="Swimlane"></syncfusion:AnnotationEditorViewModel>
                                    </syncfusion:SwimlaneHeader.Annotation>
                                </syncfusion:SwimlaneHeader>
                            </syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneViewModel.Lanes>
                                <syncfusion:LaneCollection>
                                    <!--Initialize the Lane-->
                                    <syncfusion:LaneViewModel UnitHeight="100">
                                    </syncfusion:LaneViewModel>
                                </syncfusion:LaneCollection>
                            </syncfusion:SwimlaneViewModel.Lanes>
                        </syncfusion:SwimlaneViewModel>
                    </syncfusion:SwimlaneCollection>
                </syncfusion:SfDiagram.Swimlanes>
            </syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
  //Initialize the SfDiagram
  SfDiagram diagram = new SfDiagram();
 //Initialize SwimlaneCollection to SfDiagram
  diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };

   swimlane.Lanes = new LaneCollection()
   {
   new LaneViewModel()
   {
    UnitHeight=100,
   }
};

//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Lane](Swimlane-images/Swimlane_Lane.PNG).

### Create Lane Header and Header customization

* The [`Header`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.LaneViewModel~Header.html) property of lane allows you to textually describe the lane and to customize the appearance of the description.
* The size of lane header can be controlled by using [`UnitWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitWidth.html) and [`UnitHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitHeight.html) properties of header.
* The appearance of lane header can be set by using the [`ShapeStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~ShapeStyle.html) properties.

The following code example illustrates how to define a lane header and its customization.

{% tabs %}
{% highlight xaml %}

<Style x:Key="LaneHeaderStyle" TargetType="Path">
   <Setter Property="Fill" Value="#FF5B9BD5"/>
   <Setter Property="Stretch" Value="Fill"/>
   <Setter Property="Stroke" Value="#41719C"/>
   <Setter Property="StrokeThickness" Value="1"/>
</Style>
 <syncfusion:SfDiagram x:Name="diagram" >
                <syncfusion:SfDiagram.Swimlanes>
                     <!--Initialize the SwimlaneCollection--> 
                    <syncfusion:SwimlaneCollection>
                        <!--Initialize the Swimlane-->
                        <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  
                UnitHeight="120" UnitWidth="450">
                            <!--Create a header for Swimlane-->
                            <syncfusion:SwimlaneViewModel.Header>
                                <syncfusion:SwimlaneHeader UnitHeight="32" >
                                    <syncfusion:SwimlaneHeader.Annotation>
                                        <syncfusion:AnnotationEditorViewModel Content="Swimlane"></syncfusion:AnnotationEditorViewModel>
                                    </syncfusion:SwimlaneHeader.Annotation>
                                </syncfusion:SwimlaneHeader>
                            </syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneViewModel.Lanes>
                                <syncfusion:LaneCollection>
                                    <!--Initialize the Lane-->
                                    <syncfusion:LaneViewModel UnitHeight="100">
                                        <syncfusion:LaneViewModel.Header>
                                            <!--Create a header for Lane-->
                                            <syncfusion:SwimlaneHeader UnitWidth="30" ShapeStyle="{StaticResource LaneHeaderStyle}" >
                                                <syncfusion:SwimlaneHeader.Annotation>
                                                    <syncfusion:AnnotationEditorViewModel Content="Lane"></syncfusion:AnnotationEditorViewModel>
                                                </syncfusion:SwimlaneHeader.Annotation>
                                            </syncfusion:SwimlaneHeader>
                                        </syncfusion:LaneViewModel.Header>
                                    </syncfusion:LaneViewModel>
                                </syncfusion:LaneCollection>
                            </syncfusion:SwimlaneViewModel.Lanes>
                        </syncfusion:SwimlaneViewModel>
                    </syncfusion:SwimlaneCollection>
                </syncfusion:SfDiagram.Swimlanes>
            </syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
  //Initialize the SfDiagram
  SfDiagram diagram = new SfDiagram();
 //Initialize SwimlaneCollection to SfDiagram
  diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };

   swimlane.Lanes = new LaneCollection()
   {
   new LaneViewModel()
   {
    UnitHeight=100,
    Header=new SwimlaneHeader()
    {
        UnitHeight=30,
        Annotation=new AnnotationEditorViewModel(){Content="Lane"},
        ShapeStyle=this.Resources["LaneHeaderStyle"] as Style,
    }
   }
};

//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Lane Header](Swimlane-images/Swimlane_Lane_Header.PNG).


### Add and Remove lane at runtime

 You can add and remove the lane at runtime by using the `Add` and `Remove` method of the [`SfDiagram.Lanes`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Lanes.html) Collection. The following code illustrates how to dynamically add and remove lane to swimlane.

{% tabs %}
{% highlight xaml %}
 <Button Name="AddButton" Width="100"  Height="30" IsEnabled="True" Content="Add Lane" ToolTip="Add Lane" Command="{Binding AddCommand}" Cursor="Hand"></Button>
<Button Name="RemoveButton" Width="100"  Height="30" IsEnabled="True" Content="Remove Lane" ToolTip="Remove Lane" Command="{Binding RemoveCommand}" Cursor="Hand">
</Button>
 <syncfusion:SfDiagram x:Name="diagram" Nodes="{Binding Nodes}" 
    Swimlanes="{Binding Swimlanes}"                            Connectors="{Binding Connectors}"                         SelectedItems="{Binding SelectedItems}"                              SnapSettings="{Binding SnapSettings}"                              HorizontalRuler="{Binding HorizontalRuler}"                              VerticalRuler="{Binding VerticalRuler}"/>

{% endhighlight %}
{% highlight c# %}

SnapSettings = new SnapSettings()
{
 SnapConstraints = SnapConstraints.None,
};

SelectedItems = new SelectorViewModel();

HorizontalRuler = new Ruler() { Orientation = Orientation.Horizontal };
VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };

//Add Command
 AddCommand = new Command(OnAdd);
//Remove Command
 RemoveCommand = new Command(OnRemove);

 //Initialize SwimlaneCollection to SfDiagram
  this.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };

   swimlane.Lanes = new LaneCollection()
   {
   new LaneViewModel()
   {
    UnitHeight=100,
    Header=new SwimlaneHeader()
    {
        UnitHeight=30,
        Annotation=new AnnotationEditorViewModel(){Content="Lane"},
        ShapeStyle=this.Resources["LaneHeaderStyle"] as Style,
    }
   }
};

//Add Swimlane to Swimlanes property of the Diagram
(this.Swimlanes as SwimlaneCollection).Add(swimlane);

//Add Lane into Lanes collection
 private void OnAdd(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
   if (swimlane != null)
    {
     (swimlane.Lanes as LaneCollection).Add(new LaneViewModel() { UnitHeight = 100 });
    }
 }
 //Remove Lane from Lanes collection
 private void OnRemove(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
  if (swimlane != null && (swimlane.Lanes as LaneCollection).Count>1)
  {
  (swimlane.Lanes as LaneCollection).Remove((swimlane.Lanes as LaneCollection).LastOrDefault());
  }
 }

{% endhighlight %}
{% endtabs %}

![Lane Add Remove](Swimlane-images/Lane_Add_Remove.gif).

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Add_Remove_Lane)

### Add children to lane

 To add nodes to lane,you should add [`Children`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.LaneViewModel~Children.html) collection of the lane.

The following code example illustrates how to add nodes to lane.

{% tabs %}
{% highlight xaml %}
 <!--Style for Node-->
<Style TargetType="syncfusion:Node">
 <Setter Property="Shape">
  <Setter.Value>
   <RectangleGeometry Rect="0,0,100,100"></RectangleGeometry>
  </Setter.Value>
  </Setter>
 <Setter Property="ShapeStyle">
  <Setter.Value>
    <Style TargetType="Path">
      <Setter Property="Fill" Value="#5b9bd5"/>
      <Setter Property="Stretch" Value="Fill"/>
    </Style>
</Setter.Value>
</Setter>
</Style>

 <syncfusion:SfDiagram x:Name="diagram" Nodes="{Binding Nodes}" 
    Swimlanes="{Binding Swimlanes}"                            Connectors="{Binding Connectors}"                         SelectedItems="{Binding SelectedItems}"                              SnapSettings="{Binding SnapSettings}"                              HorizontalRuler="{Binding HorizontalRuler}"                              VerticalRuler="{Binding VerticalRuler}"/>

{% endhighlight %}
{% highlight c# %}

SnapSettings = new SnapSettings()
{
 SnapConstraints = SnapConstraints.None,
};

SelectedItems = new SelectorViewModel();

HorizontalRuler = new Ruler() { Orientation = Orientation.Horizontal };
VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };

//Add Command
 AddCommand = new Command(OnAdd);
//Remove Command
 RemoveCommand = new Command(OnRemove);

 //Initialize SwimlaneCollection to SfDiagram
  this.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };
LaneViewModel lane1 = new LaneViewModel()
{
  UnitHeight = 100,
  Header = new SwimlaneHeader()
  {
    UnitHeight = 30,
    Annotation = new AnnotationEditorViewModel() { Content = "Lane" }
  }
 };
 swimlane.Lanes = new LaneCollection()
 {
   lane1
 };
NodeViewModel node = new NodeViewModel() { UnitHeight = 50, UnitWidth = 50, LaneOffsetX = 100, LaneOffsetY = 30 };
 NodeViewModel node1 = new NodeViewModel() { UnitHeight = 50, UnitWidth = 50, LaneOffsetX = 250, LaneOffsetY = 30 };
(this.Nodes as NodeCollection).Add(node);
(this.Nodes as NodeCollection).Add(node1);
(lane1.Children as LaneChildren).Add(node);
(lane1.Children as LaneChildren).Add(node1);

//Add Swimlane to Swimlanes property of the Diagram
(this.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Lane Children](Swimlane-images/Lane_Children.PNG).

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Lane_Children)

### Lane interaction

### Resizing lane

* Lane can be resized in the bottom and right direction.
* Lane can be resized by using resize selector of the lane.
* Lane can be resized by resizing the bottom and right border of the lane without make a selection.
* Once you can resize the lane,the swimlane will be resized automatically.
* The lane can be resized either resizing the selector or the tight bounds of the child object. If the child node move to edge of the lane it can be automatically resized.
* The `SwimlaneChildChangedEvent` will notify the `UnitHeight` and `UnitWidth` changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [SwimlaneChildChangedEvent](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IGraphInfo~SwimlaneChildChangedEvent_EV.html) 
The following image illustrates how resize the lane.

![Lane Resizing](Swimlane-images/Lane_Resize.gif)

### Lane swapping

* Lanes can be swapped using drag the lanes over another lane.
* Helper should intimate the insertion point while lane swapping.
The following image illustrates how swapping the lane.
* The `SwimlaneChildChangedEvent` will notify the `RowIndex` and `ColumnIndex` changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [SwimlaneChildChangedEvent](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.IGraphInfo~SwimlaneChildChangedEvent_EV.html) 

![Lane Swapping](Swimlane-images/Lane_Swapping.gif)

### Resize helper

* The special resize helper will be used to resize the lanes.
* The resize cursor will be available on the right and bottom direction alone.
* Once resize the lane the swimlane will be resized automatically

### Children interaction in lanes

* You can resize the child node within swimlanes.
* You can drag the child nodes within lane.
* Interchange the child nodes from one lane to another lane.
* Drag and drop the child nodes from lane to diagram.
* Drag and drop the child nodes from diagram to lane.
* Based on the child node interactions,the lane size should be updated.
The following image illustrates children interaction in lane.

![Lane Children Interaction](Swimlane-images/Child_Interaction.gif)
  
### Lane header editing

Diagram provides the support to edit Lane headers at runtime. We achieve the header editing by double click event. Double clicking the header label will enables the editing of that.
The following image illustrates how to edit the lane header.

![Lane Header Editing](Swimlane-images/Lane_Header_Edit.gif)

## Phase

 Phase are the subprocess which will split each lanes as horizontally or vertically based on the swimlane orientation. The multiple number of [`Phase`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.Phase.html) can be added to swimlane.
The following code example illustrates how to add phase at swimlane.

{% tabs %}
{% highlight xaml %}

   <syncfusion:SfDiagram x:Name="diagram" >
                <syncfusion:SfDiagram.Swimlanes>
                     <!--Initialize the SwimlaneCollection--> 
                    <syncfusion:SwimlaneCollection>
                        <!--Initialize the Swimlane-->
                        <syncfusion:SwimlaneViewModel OffsetX="300" OffsetY="150"  
                UnitHeight="120" UnitWidth="450">
                            <!--Create a header for Swimlane-->
                            <syncfusion:SwimlaneViewModel.Header>
                                <syncfusion:SwimlaneHeader UnitHeight="32" >
                                    <syncfusion:SwimlaneHeader.Annotation>
                                        <syncfusion:AnnotationEditorViewModel Content="Swimlane"></syncfusion:AnnotationEditorViewModel>
                                    </syncfusion:SwimlaneHeader.Annotation>
                                </syncfusion:SwimlaneHeader>
                            </syncfusion:SwimlaneViewModel.Header>
                           <syncfusion:SwimlaneViewModel.Phases>
                                <syncfusion:PhaseCollection>
                             <!--Initialize the Phase-->
                             <syncfusion:PhaseViewModel UnitWidth="450">
                                <syncfusion:PhaseViewModel.Header>
                                <!--Create a header for Phase-->
                            <syncfusion:SwimlaneHeader UnitHeight="30" >
                                 <syncfusion:SwimlaneHeader.Annotation>
                                  <syncfusion:AnnotationEditorViewModel Content="Phase"></syncfusion:AnnotationEditorViewModel>
                                </syncfusion:SwimlaneHeader.Annotation>
                                 </syncfusion:SwimlaneHeader>
                                  </syncfusion:PhaseViewModel.Header>
                                  </syncfusion:PhaseViewModel>
                                </syncfusion:PhaseCollection>
                            </syncfusion:SwimlaneViewModel.Phases>
                        </syncfusion:SwimlaneViewModel>
                    </syncfusion:SwimlaneCollection>
                </syncfusion:SfDiagram.Swimlanes>
            </syncfusion:SfDiagram>
{% endhighlight %}
{% highlight c# %}
  //Initialize the SfDiagram
  SfDiagram diagram = new SfDiagram();
 //Initialize SwimlaneCollection to SfDiagram
  diagram.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };

  swimlane.Phases = new PhaseCollection()
  {
       new PhaseViewModel()
       {
        UnitWidth=450,
        Header=new SwimlaneHeader()
        {
         UnitHeight=30,
         Annotation=new AnnotationEditorViewModel(){Content="Phase"},
        }
       }
  };


//Add Swimlane to Swimlanes property of the Diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Phse](Swimlane-images/Swimlane_Phase.PNG).


### Dynamically add phase to Lane

 You can add the a phase at runtime by using the `Add` and `Remove` method of the [`SfDiagram.Phases`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Phases.html) Collection. The following code example illustrates how to add and remove phase at run time.

{% tabs %}
{% highlight xaml %}
 <Button Name="AddButton" Width="100"  Height="30" IsEnabled="True" Content="Add Phase" ToolTip="Add Phase" Command="{Binding AddCommand}" Cursor="Hand"></Button>
<Button Name="RemoveButton" Width="100"  Height="30" IsEnabled="True" Content="Remove Phase" ToolTip="Remove Phase" Command="{Binding RemoveCommand}" Cursor="Hand">
</Button>
 <syncfusion:SfDiagram x:Name="diagram" Nodes="{Binding Nodes}" 
    Swimlanes="{Binding Swimlanes}"                            Connectors="{Binding Connectors}"                         SelectedItems="{Binding SelectedItems}"                              SnapSettings="{Binding SnapSettings}"                              HorizontalRuler="{Binding HorizontalRuler}"                              VerticalRuler="{Binding VerticalRuler}"/>

{% endhighlight %}
{% highlight c# %}

SnapSettings = new SnapSettings()
{
 SnapConstraints = SnapConstraints.None,
};

SelectedItems = new SelectorViewModel();

HorizontalRuler = new Ruler() { Orientation = Orientation.Horizontal };
VerticalRuler = new Ruler() { Orientation = Orientation.Vertical };

//Add Command
 AddCommand = new Command(OnAdd);
//Remove Command
 RemoveCommand = new Command(OnRemove);

 //Initialize SwimlaneCollection to SfDiagram
  this.Swimlanes = new SwimlaneCollection();

 //Creating the SwimlaneViewModel
 SwimlaneViewModel swimlane = new SwimlaneViewModel()
 {
   UnitWidth = 450,
   UnitHeight = 120,
   OffsetX = 300,
   OffsetY = 150,
   Orientation = Orientation.Horizontal,
 };
   //Creating Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "Swimlane"
     },
   };

 swimlane.Phases = new PhaseCollection()
 {
   new PhaseViewModel()
    {
     UnitWidth=450,
     Header=new SwimlaneHeader()
     {
      UnitHeight=24,
      Annotation=new AnnotationEditorViewModel(){Content="Phase"},
     }
    }
  };

//Add Swimlane to Swimlanes property of the Diagram
(this.Swimlanes as SwimlaneCollection).Add(swimlane);

//Add Lane into Lanes collection
 private void OnAdd(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
   if (swimlane != null)
    {
     (swimlane.Phases as PhaseCollection).Add(new PhaseViewModel() { UnitWidth = 100 });
    }
 }
 //Remove Lane from Lanes collection
 private void OnRemove(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
  if (swimlane != null && (swimlane.Phases as PhaseCollection).Count>1)
  {
   (swimlane.Phases as PhaseCollection).Remove((swimlane.Phases as PhaseCollection).LastOrDefault());
  }
 }

{% endhighlight %}
{% endtabs %}

![Phase Add Remove](Swimlane-images/Phase_Add_Remove.gif).

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Add_Remove_Phase)

### Phase interaction

### Resizing

* The phase can be resized by using its selector.
* You must select the phase header to enable the phase selection.
* Once the phase can be resized, the lane size will be updated automatically.

### Resizing helper

* The special resize selector will be used to resize the phase.
* The resize cursor will be available on the left and bottom direction for horizontal, and the top and bottom direction for vertical swimlane.

### Phase header editing

Diagram provides the support to edit phase headers at runtime. We achieve the header editing by double click event. Double clicking the header label will enables the editing of that.

The following image illustrates how to edit the phase header.

![Phase Header Editing](Swimlane-images/Phase_Header_Edit.gif)

## Add swimlane to palette
 
 Diagram provides the support to add swimlane and phases to symbol palette. The following code sample illustrate how to add swimlane and phases to palette.

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

## Add Swimlane shapes to palette via category

we can add the swimlane shapes via category. For more information, refer to the [Symbol categories](/wpf/sfdiagram/stencil#symbol-categories "Symbol categories"). 

### Drag and drop swimlane to palette

* The drag and drop support for swimlane shapes has been provided.
* When you drag and drop the lane shape,if the diagram already contains swimlane with the same orientation, the lane will be added and stacked inside a swimlane based on the order. Otherwise, it will be added a new swimlane.
* The phase will only drop on swimlane shape with same orientation.
The following image illustrates how to drag symbol from palette.

![Drag Symbol from Palette](Swimlane-images/Symbol_palette.gif)

[View Swimlane sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane-Sample)