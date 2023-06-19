---
layout: post
title: Shapes in WPF Diagram control | Syncfusion
description: Learn here all about Shapes support in Syncfusion WPF Diagram (SfDiagram) control, its elements and more.
platform: wpf
control: SfDiagram
documentation: ug
---

# Shapes in WPF Diagram (SfDiagram)

We have provided some basic built-in shapes as ResourceDictionary.

The following code example illustrates how to merge shapes into diagram.

{% tabs %}
{% highlight xaml %}
<ResourceDictionary.MergedDictionaries>
    <!--Initialize Shapes-->
    <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
</ResourceDictionary.MergedDictionaries>  
{% endhighlight %}
{% endtabs %}

## Basic Shapes

The following code example illustrates how to assign Shape property of the Node.

{% tabs %}
{% highlight xaml %}
<!--Style for Node-->
<Style TargetType="syncfusion:Node">
    <Setter Property="ShapeStyle">
        <Setter.Value>
            <Style TargetType="Path">
                <Setter Property="Fill" Value="CornflowerBlue"/>
                <Setter Property="Stretch" Value="Fill"/>
                <Setter Property="Stroke" Value="Black"/>
            </Style>
        </Setter.Value>
   </Setter>
</Style>

<!--Initialize the SfDiagram-->
<syncfusion:SfDiagram x:Name="diagram">
    <!--Initialize the NodeCollection-->
    <syncfusion:SfDiagram.Nodes>
        <syncfusion:NodeCollection>
            <!--Add Node with basic shape-->
            <syncfusion:NodeViewModel x:Name="Node" UnitHeight="100" UnitWidth="100" 
                                      OffsetX="100" OffsetY="100" 
                                      Shape="{StaticResource Rectangle}"/>  
        </syncfusion:NodeCollection>
    </syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>
{% endhighlight %}
{% highlight C# %}

//Initialize the diagram
SfDiagram diagram = new SfDiagram();

//Initialize the NodeViewModel
NodeViewModel node = new NodeViewModel()
{
    UnitHeight = 100,
    UnitWidth = 100,
    OffsetX = 100,
    OffsetY = 100,
    Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },
};

// Add the node into Nodes collection
(diagram.Nodes as NodeCollection).Add(node);
{% endhighlight %}
{% endtabs %}

Output Node will be,

![WPF Diagram Shapes](shapes_images\wpf-diagram-shapes.PNG)
  
The list of shapes are available in the resource dictionary as follows
 
| Shape Category | Shape Name | Output Shape |
|---|---|---|
| Basic Shapes | Rectangle | ![Basic Rectangle in WPF Diagram ](shapes_images\wpf-diagram-basic-rectangle.PNG) |
|  | Triangle| ![Basic Triangle in WPF Diagram](shapes_images\wpf-diagram-basic-triangle.PNG) |
|  | Plus| ![Basic Plus in WPF Diagram](shapes_images\wpf-diagram-basic-plus.PNG) |
|  | Pentagon | ![Basic Pentagon in WPF Diagram](shapes_images\wpf-diagram-basic-pentagon.PNG) |
|  | Hexagon | ![Basic Hexagon in WPF Diagram](shapes_images\wpf-diagram-basic-hexagon.PNG) |
|  |Heptagon | ![Basic Heptagon in WPF Diagram](shapes_images\wpf-diagram-basic-heptagon.PNG) |
|  | Octagon | ![Basic Octagon in WPF Diagram](shapes_images\wpf-diagram-basic-octagon.PNG) |
|  |Trapezoid | ![Basic Trapezoid in WPF Diagram](shapes_images\wpf-diagram-basic-trapezoid.PNG) |
|  | Decagon|![Basic Decagon in WPF Diagram](shapes_images\wpf-diagram-basic-decagon.PNG) |
|  | RightTriangle| ![Basic Right Triangle in WPF Diagram](shapes_images\wpf-diagram-basic-right-triangle.PNG)|
|  | Cylinder| ![Basic Cylinder in WPF Diagram](shapes_images\wpf-diagram-basic-cylinder.PNG)|
|  | Diamond| ![Basic Diamond in WPF Diagram ](shapes_images\wpf-diagram-basic-diamond.PNG)|
|  |TwoSideFlatCorner | ![Basic Two Side Flat Corner in WPF Diagram](shapes_images\wpf-diagram-basic-two-side-flat-corner.PNG)|
|  | TwoSideRoundCorner| ![Basic Two Side Round Corner in WPF Diagram](shapes_images\wpf-diagram-basic-two-side-round-corner.PNG)|
|  |RoundedRectangle | ![Basic Rounded Rectangle in WPF Diagram](shapes_images\wpf-diagram-basic-rounded-rectangle.PNG)|
|  | Cloud | ![Basic Cloud in WPF diagram](shapes_images\wpf-diagram-basic-cloud.PNG)|
|  |CloudCallOut | ![Basic Cloud CallOut in WPF Diagram](shapes_images\wpf-diagram-basic-cloud-callout.PNG)|
|  | Paralleogram| ![Basic Paralleogram in WPF Diagram](shapes_images\wpf-diagram-basic-paralleogram.PNG)|
|  |Frame | ![Basic Frame in WPF Diagram](shapes_images\wpf-diagram-basic-frame.PNG)|
|  | Donut| ![Basic Donut in WPF Diagram](shapes_images\wpf-diagram-basic-donut.PNG)|
|  |RectangleCallOut | ![Basic Rectangle CallOut](shapes_images\wpf-diagram-basic-rectangle-callout.PNG)|
|  |RoundedRectangleCallOut | ![Basic Rounded Rectangle CallOut in WPF Diagram](shapes_images\wpf-diagram-basic-rounded-rectangle-callout.PNG)|
|  | OvalCallOut| ![Basic Oval CallOut in WPF Diagram](shapes_images\wpf-diagram-basic-oval-callout.PNG)|
|  | Cube| ![Basic Cube in WPF Diagram](shapes_images\wpf-diagram-basic-cube.PNG)|
|  |NoSymbol | ![Basic No Symbol in WPF Diagram](shapes_images\wpf-diagram-basic-no-symbol.PNG)|
|  |FourPointStar | ![Basic Four Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-four-point-star.PNG)|
|  |FivePointStar | ![Basic Five Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-five-point-star.PNG)|
|  | SixPointStar| ![Basic Six Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-six-point-star.PNG)|
|  |SevenPointStar | ![Basic Seven Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-seven-point-star.PNG)|
|  |SixteenPointStar | ![Basic Sixteen Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-sixteen-point-star.PNG)|
|  |TwentyFourPointStar | ![Basic Twenty Four Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-twenty-four-point-star.PNG)|
|  |ThirtyTwoPointStar | ![Basic Thirty Two Point Star in WPF Diagram](shapes_images\wpf-diagram-basic-thirty-two-point-star.PNG)|
| Flow Shapes |Process | ![Flow Process in WPF Diagram](shapes_images\wpf-diagram-flow-process.PNG)|
|  | Decision| ![Flow Decision in WPF Diagram](S\shapes_images\wpf-diagram-flow-decision.PNG)|
|  |Terminator | ![Flow Terminator in WPF Diagram](shapes_images\wpf-diagram-flow-terminator.PNG)|
|  |Sort | ![Sort in WPF Diagram](shapes_images\wpf-diagram-flow-sort.PNG)|
| |Document | ![Flow Sort in WPF Diagram](shapes_images\wpf-diagram-flow-document.PNG)|
|  |MultiDocument | ![Flow MultiDocument in WPF Diagram](shapes_images\wpf-diagram-flow-multi-document.PNG)|
| |DirectData | ![Flow Direct Data in WPF Diagram](shapes_images\wpf-diagram-flow-direct-data.PNG)|
|  |SequentialData | ![Flow Sequential Data in WPF Diagram](shapes_images\wpf-diagram-flow-sequential-data.PNG)|
|  |PaperTap | ![Flow Paper Tap in WPF Diagram](shapes_images\wpf-diagram-flow-paper-tap.PNG)|
|  | Collate| ![Flow Collate in WPF Diagram](shapes_images\wpf-diagram-flow-collate.PNG)|
|  | SummingJunction| ![Flow Summing Junction in WPF Diagram](shapes_images\wpf-diagram-flow-summing-junction.PNG)|
|  |Or | ![Flow Or WPF Diagram](shapes_images\wpf-diagram-flow-or.PNG)|
| |InternalStorage | ![Flow Internal Storage in WPF Diagram](shapes_images\wpf-diagram-flow-internal-storage.PNG)|
|  |PredefinedProcess | ![Flow Predefined Process in WPF Diagram](shapes_images\wpf-diagram-flow-predefined-process.PNG)|
| |Extract | ![Flow Extract in WPF Diagram](shapes_images\wpf-diagram-flow-extract.PNG)|
|  |Merge | ![Flow Merge in WPF Diagram](shapes_images\wpf-diagram-flow-merge.PNG)|
|  | OffPageReference| ![Flow Off Page Reference in WPF Diagram](shapes_images\wpf-diagram-basic-flow-offpage-reference.PNG)|
|  |SequentialAccessStorage | ![Flow Sequential Access Storage in WPF Diagram](shapes_images\wpf-diagram-flow-sequential-access-storage.PNG)|
|  |Delay | ![Flow Delay in WPF Diagram](shapes_images\wpf-diagram-flow-delay.PNG)|
|  | StoredData| ![Flow Stored Data in WPF Diagram](shapes_images\wpf-diagram-flow-stored-data.PNG)|
|  |Display | ![Flow Display in WPF Diagram](shapes_images\wpf-diagram-flow-display.PNG)|
|  |ManualOperation | ![Flow Manual Operation in WPF Diagram](shapes_images\wpf-diagram-flow-manual-operation.PNG)|
|  |Data | ![Flow Data in WPF Diagram](shapes_images\wpf-diagram-flow-data.PNG)|
|  | OnPageReference| ![Flow On Page Reference in WPF Diagram](shapes_images\wpf-diagram-flow-onpage-reference.PNG)|
|  |Prepration | ![Flow Prepration in WPF Diagram](shapes_images\wpf-diagram-flow-prepration.PNG)|
|  |PunchedCard | ![Flow Punched Card in WPF Diagram](shapes_images\wpf-diagram-flow-punched-card.PNG)|
|  |Card | ![Flow Card in WPF Diagram](shapes_images\wpf-diagram-flow-card.PNG)|
|  | LoopLimit| ![Loop Limit in WPF Diagram](shapes_images\wpf-diagram-flow-loop-limit.PNG)|
|  |ManualInput | ![Manual Input in WPF Diagram](shapes_images\wpf-diagram-flow-manual-input.PNG)|
| Arrow Shapes |CurvedDownArrow | ![Curved DownArrow in WPF Diagram](shapes_images\wpf-diagram-curved-down-arrow.PNG)|
|  | CurvedLeftArrow| ![Curved Left Arrow in WPF Diagram](shapes_images\wpf-diagram-curved-left-arrow.PNG)|
|  |CurvedRightArrow| ![Curved Right Arrow in WPF Diagram](shapes_images\wpf-diagram-curved-right-arrow.PNG)|
|  | CurvedUpArrow| ![Curved UpArrow in WPF Diagram](shapes_images\wpf-diagram-curved-up-arrow.PNG)|
|  |CircularArrow | ![Circular Arrow in WPF Diagram](shapes_images\wpf-diagram-circular-arrow.PNG)|
|  | JumpingLeftArrow| ![Jumping Left Arrow in WPF Diagram](shapes_images\wpf-diagram-jumping-left-arrow.PNG)|
|  | JumpingRightArrow| ![Jumping Right Arrow in WPF Diagram](shapes_images\wpf-diagram-jumping-right-arrow.PNG)|
|  |UTurnArrow | ![UTurn Arrow in WPF Diagram](shapes_images\wpf-diagram-uturn-arrow.PNG)|
|  | LeftArrow| ![Left Arrow in WPF Diagram](shapes_images\wpf-diagram-left-arrow.PNG)|
|  |RightArrow | ![Right Arrow in WPF Diagram](shapes_images\wpf-diagram-right-arrow.PNG)|
|  |DoubleArrow | ![Double Arrow in WPF Diagram](shapes_images\wpf-diagram-double-arrow.PNG)|
|  |TopArrow | ![Top Arrow in WPF Diagram](shapes_images\wpf-diagram-top-arrow.PNG)|
|  |BottomArrow | ![Bottom Arrow in WPF Diagram](shapes_images\wpf-diagram-bottom-arrow.PNG)|
|  | MultiArrow| ![Multi Arrow in WPF Diagram](shapes_images\wpf-diagram-multi-arrow.PNG)|
|  |BlockArrow | ![Block Arrow in WPF Diagram](shapes_images\wpf-diagram-block-arrow.PNG)|
|  |QuadBlockArrow | ![Quad Block Arrow in WPF Diagram](shapes_images\wpf-diagram-quad-block-arrow.PNG)|
|  | NotchedArrow| ![Notched Arrow in WPF Diagram](shapes_images\wpf-diagram-notched-arrow.PNG)|
|  |LeftRightBlockArrow | ![left Right Block Arrow in WPF Diagram](shapes_images\wpf-diagram-left-right-block-arrow.PNG)|
|  |QuadArrow | ![Quad Arrow in WPF Diagram](shapes_images\wpf-diagram-quad-arrow.PNG)|
|  |FlexibleArrow | ![Flexible Arrow](shapes_images\wpf-diagram-flexible-arrow.PNG)|
|Data Flow Shapes  |OvalProcess | ![Oval Process in WPF Diagram](shapes_images\wpf-diagram-data-flow-oval-process.PNG)|
|  |ExternalIndicator | ![External Indicator in WPD Diagram](shapes_images\wpf-diagram-data-flow-external-indicator.PNG)|
|  |Object | ![Object in WPF Diagram](shapes_images\wpf-diagram-data-flow-object.PNG)|
|  |MultipleProcess | ![Multiple Process in WPF Diagram](shapes_images\wpf-diagram--data-flow-multiple-process.PNG)|
|  |State | ![State in WPF Diagram](shapes_images\wpf-diagram-data-flow-state.PNG)|
|  | Stop1| ![Stop1 in WPF Diagram](shapes_images\wpf-diagram-data-flow-stop-one.PNG)|
|  |Entity1 | ![Entity1 in WPF Diagram](shapes_images\wpf-diagram-data-flow-entity-one.PNG)|
|  |Entity2 | ![Entity2 in WPF Diagram](shapes_images\wpf-diagram-data-flow-entity-two.PNG)|
|Electrical Shapes  |Resistor | ![Resistor in WPF Diagram](shapes_images\wpf-diagram-electrical-resistor.PNG)|
|  |Capacitor | ![Capacitor in WPF Diagram](shapes_images\wpf-diagram-electrical-capacitor.PNG)|
|  | AC| ![AC in WPF Diagram](shapes_images\wpf-diagram-electrical-ac.PNG)|
|  |Dc1 | ![Dc1 in WPF Diagram](shapes_images\wpf-diagram-electrical-dc-one.PNG)|
|  |EquiPotent | ![EquiPotent in WPF Diagram](shapes_images\wpf-diagram-electrical-equipotent.PNG)|
|  | Inductor| ![Inductor in WPF Diagram](shapes_images\wpf-diagram-electrical-inductor.PNG)|
|  |Crystal | ![Crystal in WPF Diagram](shapes_images\wpf-diagram-electrical-crystal.PNG)|
|  | Attenuator| ![Attenuator in WPF Diagram](shapes_images\wpf-diagram-electrical-chassis.PNG)|
|  | Antenna| ![Antenna in WPF Diagram](shapes_images\wpf-diagram-electrical-antenna.PNG)|
|  | LoopAntenna| ![Loop Antenna in WPF Diagram](shapes_images\wpf-diagram-electrical-loop-antenna.PNG)|
|  |CircuitBreaker | ![Circuit Breaker in WPF Diagram](shapes_images\wpf-diagram-electrical-circuit-breaker.PNG)|
|  |Fuse | ![Fuse in WPF Diagram](shapes_images\wpf-diagram-electrical-fuse.PNG)|
|  | IdealSource| ![Ideal Source in WPF Diagram](shapes_images\wpf-diagram-electrical-ideal-source.PNG)|
|  |GenericComponent | ![Generic Component in WPF Diagram](shapes_images\wpf-diagram-electrical-generic-component.PNG)|
|  |Transducer | ![Transducer in WPF Diagram](shapes_images\wpf-diagram-electrical-transducer.PNG)|
|  |Transducer2 | ![Transducer2 in WPF Diagram](shapes_images\wpf-diagram-electrical-transducer-two.PNG)|
|  |PickupHead | ![Pickup Head in WPF Diagram](shapes_images\wpf-diagram-electrical-pickup-head.PNG)|
|  |HalfConductor | ![Half Conductor in WPF Diagram](shapes_images\wpf-diagram-electrical-half-conductor.PNG)|
|  | Pulse| ![Pulse in WPF Diagram](shapes_images\wpf-diagram-electrical-pulse.PNG)|
|  |Pulse1 | ![Pulse1 in WPF Diagram](shapes_images\wpf-diagram-electrical-pulse-one.PNG)|
|  |Sawtooth | ![Sawtooth in WPF Diagram](shapes_images\wpf-diagram-electrical-sawtooth.PNG)|
|  | Step| ![Step in WPF Diagram](shapes_images\wpf-diagram-electrical-step.PNG)|
|  | SensingLinkSquib| ![Sensing Link Squib in WPF Diagram](shapes_images\wpf-diagram-electrical-sensing-link-squib.PNG)|
|  |Indicator | ![Indicator in WPF Diagram](shapes_images\wpf-diagram-electrical-indicator.PNG)|
|  | Material| ![Material in WPF Diagram](shapes_images\wpf-diagram-electrical-material.PNG)|
|  |DelayElement | ![Delay Element in WPF Diagram](shapes_images\wpf-diagram-electrical-delay-element.PNG)|
|  | SurgeProtector| ![Surge Protector in WPF Diagram](shapes_images\wpf-diagram-electrical-surge-protector.PNG)|
|  |SurgeProtector1 | ![Surge Protector1 in WPF Diagram](shapes_images\wpf-diagram-electrical-surge-protector-one.PNG)|
|  |PermanentMagnet | ![Permanen tMagnet in WPF Diagram](shapes_images\wpf-diagram-electrical-permanent-magnet.PNG)|
|  |Magnetoresistor_shape | ![Magnetoresistor_shape in WPF Diagram](shapes_images\wpf-diagram-electrical-magnetoresistor-shape.PNG)|
|  | IgnitorPlug| ![Ignitor Plug in WPF Diagram](shapes_images\wpf-diagram-electrical-ignitor-plug.PNG)|
|  |Bell | ![Bell in WPF Diagram](shapes_images\wpf-diagram-electrical-bell.PNG)|
|  | Buzzer| ![Buzzer in WPF Diagram](shapes_images\wpf-diagram-electrical-buzzer.PNG)|
|  |ThermalElement | ![Thermal Element in WPF Diagram](shapes_images\wpf-diagram-electrical-thermal-element.PNG)|
|  | ThermoCouple| ![ThermoCouple in WPF Diagram](shapes_images\wpf-diagram-electrical-thermo-couple.PNG)|

Find the [Shapes sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Shapes) to depict the shapes.









 
 











