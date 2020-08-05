---
layout: post
title: Visualize graphical object using Swimlanes | Syncfusion
description: How to visually represent the subprocess which will split each lanes as horizontally or vertically for Phase and how to customize their appearance?
platform: wpf
control: SfDiagram
documentation: ug
---

# Phase in WPF Diagram(SfDiagram)

 The [Phase](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PhaseViewModel.html) is the subprocess which will split each lanes as horizontally or vertically based on the swimlane orientation. The multiple number of phase can be added to swimlane.

## Create an empty Phase

You can create the [Phase](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PhaseViewModel.html) and add into the[Phases](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Phases.html) collection of the Swimlane.

>Note: For Horizontal Swimlane, you must set the UnitWidth of the Phase. For Vertical Swimlane, you must set UnitHeight of the Phase.

The following code example explains how to add phase at swimlane.

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
                                        <syncfusion:AnnotationEditorViewModel Content="SALES PROCESS FLOW CHART"> </syncfusion:AnnotationEditorViewModel>
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
                                  <syncfusion:AnnotationEditorViewModel Content="Phase1"></syncfusion:AnnotationEditorViewModel>
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
      Content = "SALES PROCESS FLOW CHART"
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
         Annotation=new AnnotationEditorViewModel(){Content="Phase1"},
        }
       }
  };


//Add Swimlane to the Swimlanes property of the diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Phse](Swimlane-images/Swimlane_Phase.PNG).


## Dynamically add phase to Swimlane

 You can add the a phase at runtime by using the `Add` and `Remove` method of the [`SfDiagram.Phases`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneViewModel~Phases.html) collection. The following code example explains how to add and remove phase at run time.

{% tabs %}
{% highlight xaml %}
 <Button Name="AddButton" Width="100"  Height="30" IsEnabled="True" Content="Add Phase" ToolTip="Add Phase" Command="{Binding AddCommand}" Cursor="Hand"></Button>
<Button Name="RemoveButton" Width="100"  Height="30" IsEnabled="True" Content="Remove Phase" ToolTip="Remove Phase" Command="{Binding RemoveCommand}" Cursor="Hand">
</Button>
 <syncfusion:SfDiagram x:Name="diagram" Nodes="{Binding Nodes}" 
    Swimlanes="{Binding Swimlanes}"                            Connectors="{Binding Connectors}"                         SelectedItems="{Binding SelectedItems}"                              SnapSettings="{Binding SnapSettings}"                              HorizontalRuler="{Binding HorizontalRuler}"                              VerticalRuler="{Binding VerticalRuler}"/>

{% endhighlight %}
{% highlight c# %}
public class DiagramVM : DiagramViewModel
{
#region Fields

private ICommand _AddCommand;
private ICommand _RemoveCommand;
#endregion
public DiagramVM()
{
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
}
private void InitializeDiagram()
{
 //Initialize the SwimlaneCollection to SfDiagram
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
   //Creating a header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "SALES PROCESS FLOW CHART"
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
      Annotation=new AnnotationEditorViewModel(){Content="Phase 1"},
     }
    }
  };

//Add Swimlane to the Swimlanes property of the diagram
(this.Swimlanes as SwimlaneCollection).Add(swimlane);
}
#region Commands

public ICommand AddCommand
{
  get { return _AddCommand; }
  set { _AddCommand = value; }
}

public ICommand RemoveCommand
{
 get { return _RemoveCommand; }
 set { _RemoveCommand = value; }
}

#endregion
#region Helper Methods
//Add Lane into the Lanes collection
 private void OnAdd(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
   if (swimlane != null)
    {
     (swimlane.Phases as PhaseCollection).Add(new PhaseViewModel() { UnitWidth = 100,Header=new SwimlaneHeader() { Annotation=new AnnotationEditorViewModel() { Content = "Phase"+ " " + ((swimlane.Phases as PhaseCollection).Count + 1) } } });
    }
 }
 //Remove Lane from the Lanes collection
 private void OnRemove(object obj)
 {
  var swimlane = (this.Swimlanes as SwimlaneCollection).FirstOrDefault() as SwimlaneViewModel;
  if (swimlane != null && (swimlane.Phases as PhaseCollection).Count>1)
  {
   (swimlane.Phases as PhaseCollection).Remove((swimlane.Phases as PhaseCollection).LastOrDefault());
  }
 }
 #endregion
}
{% endhighlight %}
{% endtabs %}

![Phase Add Remove](Swimlane-images/Phase_Add_Remove.gif)

[View sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Swimlane/Swimlane_Add_Remove_Phase)

## Create the Phase Header and Header customization

* The [`Header`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.PhaseViewModel~Header.html) property of Phase allows you to textually describe the phase and to customize the appearance of the description.
* The size of Phase header can be controlled by using the [`UnitWidth`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitWidth.html) and [`UnitHeight`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~UnitHeight.html) properties of header.
* The appearance of Phase header can be set by using the [`ShapeStyle`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.SwimlaneChildViewModel~ShapeStyle.html) properties.

The following code example explains how to define a Phase header and its customization.

{% tabs %}
{% highlight xaml %}

<Style x:Key="PhaseHeaderStyle" TargetType="Path">
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
                                        <syncfusion:AnnotationEditorViewModel Content="SALES PROCESS FLOW CHART"> </syncfusion:AnnotationEditorViewModel>
                                    </syncfusion:SwimlaneHeader.Annotation>
                                </syncfusion:SwimlaneHeader>
                            </syncfusion:SwimlaneViewModel.Header>
                            <syncfusion:SwimlaneViewModel.Phases>
                            <syncfusion:PhaseCollection>
                                <!--Initialize the Lane-->
                                <syncfusion:PhaseViewModel UnitHeight="100">
                                    <syncfusion:PhaseViewModel.Header>
                                        <!--Create a header for Lane-->
                                        <syncfusion:SwimlaneHeader UnitWidth="30" ShapeStyle="{StaticResource phaseHeaderStyle}" >
                                            <syncfusion:SwimlaneHeader.Annotation>
                                                <syncfusion:AnnotationEditorViewModel Content="Phase 1" ViewTemplate="{StaticResource viewTemplate}"></syncfusion:AnnotationEditorViewModel>
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
 //Initialize the SwimlaneCollection to SfDiagram
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
   //Creating a Header for SwimlaneViewModel
   swimlane.Header = new SwimlaneHeader()
   {
     UnitHeight = 32,
     Annotation = new AnnotationEditorViewModel()
     {
      Content = "SALES PROCESS FLOW CHART"
     },
   };

  swimlane.Phases = new PhaseCollection()
  {
   new PhaseViewModel()
   {
    UnitHeight=100,
    Header=new SwimlaneHeader()
    {
        UnitWidth=30,
        Annotation=new AnnotationEditorViewModel(){Content="Phase 1",ViewTemplate = this.Resources["viewTemplate"] as DataTemplate},
        ShapeStyle=this.Resources["PhaseHeaderStyle"] as Style,
    }
   }
  };

//Add Swimlane to the Swimlanes property of the diagram
(diagram.Swimlanes as SwimlaneCollection).Add(swimlane);

{% endhighlight %}
{% endtabs %}

![Phase Header](Swimlane-images/Swimlane_Phase_Header.PNG).

## Header Selection and Resize

 * You can select the individual phase header by clicking on the header twice. For first click, the respective phase can select. 

 * You can support to resize the individual phase header. While resizing the phase, it has maintain 20px distances from Lane children.

 * The `NodeChangedEvent` will notify the `UnitHeight` and `UnitWidth` changes with their old and new values. Along with that, this event will give information about  interaction state. To explore about arguments, refer to the [NodeChangedEventArgs](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.NodeChangedEventArgs.html) 

 The following image shows how to select and resize the phase header.

![Header Select and Resize](Swimlane-images/Header_Selection_Resize.gif).

## Phase header editing

The diagram provides the support to edit phase headers at runtime. You can achieve the header editing by double click event. Double clicking the header label will enables the editing of that.

The following image shows how to edit the phase header.

![Phase Header Editing](Swimlane-images/Phase_Header_Edit.gif)


## Phase interaction

### Select

Phase can be selected by clicking (tap) the header of the phase.

### Resizing

* The phase can be resized by using its selector.
* You must select the phase header to enable the phase selection.
* Once the phase can be resized, the lane size will be updated automatically.
* Phase can be resized by resizing the right and bottom direction for horizontal, and the top and bottom direction for vertical swimlane.