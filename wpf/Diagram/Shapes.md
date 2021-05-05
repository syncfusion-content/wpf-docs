---
layout: post
title: Shapes in WPF Diagram control | Syncfusion
description: Learn here all about Shapes support in Syncfusion WPF Diagram (SfDiagram) control and more.
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

![Shapes_image1](Shapes_images\Shapes_image1.PNG)
  
The list of shapes are available in the resource dictionary as follows
 
| Shape Category | Shape Name | Output Shape |
|---|---|---|
| Basic Shapes | Rectangle | ![BasicRectangle](Shapes_images\BasicRectangle.PNG) |
|  | Triangle| ![BasicTriangle](Shapes_images\BasicTriangle.PNG) |
|  | Plus| ![BasicPlus](Shapes_images\BasicPlus.PNG) |
|  | Pentagon | ![BasicPentagon](Shapes_images\BasicPentagon.PNG) |
|  | Hexagon | ![BasicHexagon](Shapes_images\BasicHexagon.PNG) |
|  |Heptagon | ![BasicHeptagon](Shapes_images\BasicHeptagon.PNG) |
|  | Octagon | ![BasicOctagon](Shapes_images\BasicOctagon.PNG) |
|  |Trapezoid | ![BasicTrapezoid](Shapes_images\BasicTrapezoid.PNG) |
|  | Decagon|![BasicDecagon](Shapes_images\BasicDecagon.PNG) |
|  | RightTriangle| ![BasicRightTriangle](Shapes_images\BasicRightTriangle.PNG)|
|  | Cylinder| ![BasicCylinder](Shapes_images\BasicCylinder.PNG)|
|  | Diamond| ![BasicDiamond](Shapes_images\BasicDiamond.PNG)|
|  |TwoSideFlatCorner | ![BasicTwoSideFlatCorner](Shapes_images\BasicTwoSideFlatCorner.PNG)|
|  | TwoSideRoundCorner| ![BasicTwoSideRoundCorner](Shapes_images\BasicTwoSideRoundCorner.PNG)|
|  |RoundedRectangle | ![BasicRoundedRectangle](Shapes_images\BasicRoundedRectangle.PNG)|
|  | Cloud | ![BasicCloud](Shapes_images\BasicCloud.PNG)|
|  |CloudCallOut | ![BasicCloudCallOut](Shapes_images\BasicCloudCallOut.PNG)|
|  | Paralleogram| ![BasicParalleogram](Shapes_images\BasicParalleogram.PNG)|
|  |Frame | ![BasicFrame](Shapes_images\BasicFrame.PNG)|
|  | Donut| ![BasicDonut](Shapes_images\BasicDonut.PNG)|
|  |RectangleCallOut | ![BasicRectangleCallOut](Shapes_images\BasicRectangleCallOut.PNG)|
|  |RoundedRectangleCallOut | ![BasicRoundedRectangleCallOut](Shapes_images\BasicRoundedRectangleCallOut.PNG)|
|  | OvalCallOut| ![BasicOvalCallOut](Shapes_images\BasicOvalCallOut.PNG)|
|  | Cube| ![BasicCube](Shapes_images\BasicCube.PNG)|
|  |NoSymbol | ![BasicNoSymbol](Shapes_images\BasicNoSymbol.PNG)|
|  |FourPointStar | ![BasicFourPointStar](Shapes_images\BasicFourPointStar.PNG)|
|  |FivePointStar | ![BasicFivePointStar](Shapes_images\BasicFivePointStar.PNG)|
|  | SixPointStar| ![BasicSixPointStar](Shapes_images\BasicSixPointStar.PNG)|
|  |SevenPointStar | ![BasicSevenPointStar](Shapes_images\BasicSevenPointStar.PNG)|
|  |SixteenPointStar | ![BasicSixteenPointStar](Shapes_images\BasicSixteenPointStar.PNG)|
|  |TwentyFourPointStar | ![BasicTwentyFourPointStar](Shapes_images\BasicTwentyFourPointStar.PNG)|
|  |ThirtyTwoPointStar | ![BasicThirtyTwoPointStar](Shapes_images\BasicThirtyTwoPointStar.PNG)|
| Flow Shapes |Process | ![FlowProcess](Shapes_images\FlowProcess.PNG)|
|  | Decision| ![FlowDecision](Shapes_images\FlowDecision.PNG)|
|  |Terminator | ![FlowTerminator](Shapes_images\FlowTerminator.PNG)|
|  |Sort | ![Sort](Shapes_images\FlowSort.PNG)|
| |Document | ![FlowSort](Shapes_images\FlowDocument.PNG)|
|  |MultiDocument | ![FlowMultiDocument](Shapes_images\FlowMultiDocument.PNG)|
| |DirectData | ![FlowDirectData](Shapes_images\FlowDirectData.PNG)|
|  |SequentialData | ![FlowSequentialData](Shapes_images\FlowSequentialData.PNG)|
|  |PaperTap | ![FlowPaperTap](Shapes_images\FlowPaperTap.PNG)|
|  | Collate| ![FlowCollate](Shapes_images\FlowCollate.PNG)|
|  | SummingJunction| ![FlowSummingJunction](Shapes_images\FlowSummingJunction.PNG)|
|  |Or | ![Or](Shapes_images\FlowOr.PNG)|
| |InternalStorage | ![FlowInternalStorage](Shapes_images\FlowInternalStorage.PNG)|
|  |PredefinedProcess | ![FlowPredefinedProcess](Shapes_images\FlowPredefinedProcess.PNG)|
| |Extract | ![FlowExtract](Shapes_images\FlowExtract.PNG)|
|  |Merge | ![FlowMerge](Shapes_images\FlowMerge.PNG)|
|  | OffPageReference| ![FlowOffPageReference](Shapes_images\FlowOffPageReference.PNG)|
|  |SequentialAccessStorage | ![FlowSequentialAccessStorage](Shapes_images\FlowSequentialAccessStorage.PNG)|
|  |Delay | ![FlowDelay](Shapes_images\FlowDelay.PNG)|
|  | StoredData| ![FlowStoredData](Shapes_images\FlowStoredData.PNG)|
|  |Display | ![FlowDisplay](Shapes_images\FlowDisplay.PNG)|
|  |ManualOperation | ![FlowManualOperation](Shapes_images\FlowManualOperation.PNG)|
|  |Data | ![FlowData](Shapes_images\FlowData.PNG)|
|  | OnPageReference| ![FlowOnPageReference](Shapes_images\FlowOnPageReference.PNG)|
|  |Prepration | ![FlowPrepration](Shapes_images\FlowPrepration.PNG)|
|  |PunchedCard | ![FlowPunchedCard](Shapes_images\FlowPunchedCard.PNG)|
|  |Card | ![FlowCard](Shapes_images\FlowCard.PNG)|
|  | LoopLimit| ![LoopLimit](Shapes_images\FlowLoopLimit.PNG)|
|  |ManualInput | ![ManualInput](Shapes_images\FlowManualInput.PNG)|
| Arrow Shapes |CurvedDownArrow | ![CurvedDownArrow](Shapes_images\ArrowCurvedDownArrow.PNG)|
|  | CurvedLeftArrow| ![CurvedLeftArrow](Shapes_images\ArrowCurvedLeftArrow.PNG)|
|  |CurvedRightArrow| ![CurvedRightArrow](Shapes_images\ArrowCurvedRightArrow.PNG)|
|  | CurvedUpArrow| ![CurvedUpArrow](Shapes_images\ArrowCurvedUpArrow.PNG)|
|  |CircularArrow | ![CircularArrow](Shapes_images\ArrowCircularArrow.PNG)|
|  | JumpingLeftArrow| ![JumpingLeftArrow](Shapes_images\ArrowJumpingLeftArrow.PNG)|
|  | JumpingRightArrow| ![JumpingRightArrow](Shapes_images\ArrowJumpingRightArrow.PNG)|
|  |UTurnArrow | ![UTurnArrow](Shapes_images\ArrowUTurnArrow.PNG)|
|  | LeftArrow| ![LeftArrow](Shapes_images\ArrowLeftArrow.PNG)|
|  |RightArrow | ![RightArrow](Shapes_images\ArrowRightArrow.PNG)|
|  |DoubleArrow | ![DoubleArrow](Shapes_images\ArrowDoubleArrow.PNG)|
|  |TopArrow | ![TopArrow](Shapes_images\ArrowTopArrow.PNG)|
|  |BottomArrow | ![BottomArrow](Shapes_images\ArrowBottomArrow.PNG)|
|  | MultiArrow| ![MultiArrow](Shapes_images\ArrowMultiArrow.PNG)|
|  |BlockArrow | ![BlockArrow](Shapes_images\ArrowBlockArrow.PNG)|
|  |QuadBlockArrow | ![QuadBlockArrow](Shapes_images\ArrowQuadBlockArrow.PNG)|
|  | NotchedArrow| ![NotchedArrow](Shapes_images\ArrowNotchedArrow.PNG)|
|  |LeftRightBlockArrow | ![LeftRightBlockArrow](Shapes_images\ArrowLeftRightBlockArrow.PNG)|
|  |QuadArrow | ![QuadArrow](Shapes_images\ArrowQuadArrow.PNG)|
|  |FlexibleArrow | ![FlexibleArrow](Shapes_images\ArrowFlexibleArrow.PNG)|
|Data Flow Shapes  |OvalProcess | ![OvalProcess](Shapes_images\DataFlowOvalProcess.PNG)|
|  |ExternalIndicator | ![ExternalIndicator](Shapes_images\DataFlowExternalIndicator.PNG)|
|  |Object | ![Object](Shapes_images\DataFlowObject.PNG)|
|  |MultipleProcess | ![MultipleProcess](Shapes_images\DataFlowMultipleProcess.PNG)|
|  |State | ![State](Shapes_images\DataFlowState.PNG)|
|  | Stop1| ![Stop1](Shapes_images\DataFlowStop1.PNG)|
|  |Entity1 | ![Entity1](Shapes_images\DataFlowEntity1.PNG)|
|  |Entity2 | ![Entity2](Shapes_images\DataFlowEntity2.PNG)|
|Electrical Shapes  |Resistor | ![Resistor](Shapes_images\ElectricalResistor.PNG)|
|  |Capacitor | ![Capacitor](Shapes_images\ElectricalCapacitor.PNG)|
|  | AC| ![AC](Shapes_images\ElectricalAC.PNG)|
|  |Dc1 | ![Dc1](Shapes_images\ElectricalDc1.PNG)|
|  |EquiPotent | ![EquiPotent](Shapes_images\ElectricalEquiPotent.PNG)|
|  | Inductor| ![Inductor](Shapes_images\ElectricalInductor.PNG)|
|  |Crystal | ![Crystal](Shapes_images\ElectricalCrystal.PNG)|
|  | Attenuator| ![Attenuator](Shapes_images\ElectricalChassis.PNG)|
|  | Antenna| ![Antenna](Shapes_images\ElectricalAntenna.PNG)|
|  | LoopAntenna| ![LoopAntenna](Shapes_images\ElectricalLoopAntenna.PNG)|
|  |CircuitBreaker | ![CircuitBreaker](Shapes_images\ElectricalCircuitBreaker.PNG)|
|  |Fuse | ![Fuse](Shapes_images\ElectricalFuse.PNG)|
|  | IdealSource| ![IdealSource](Shapes_images\ElectricalIdealSource.PNG)|
|  |GenericComponent | ![GenericComponent](Shapes_images\ElectricalGenericComponent.PNG)|
|  |Transducer | ![Transducer](Shapes_images\ElectricalTransducer.PNG)|
|  |Transducer2 | ![Transducer2](Shapes_images\ElectricalTransducer2.PNG)|
|  |PickupHead | ![PickupHead](Shapes_images\ElectricalPickupHead.PNG)|
|  |HalfConductor | ![HalfConductor](Shapes_images\ElectricalHalfConductor.PNG)|
|  | Pulse| ![Pulse](Shapes_images\ElectricalPulse.PNG)|
|  |Pulse1 | ![Pulse1](Shapes_images\ElectricalPulse1.PNG)|
|  |Sawtooth | ![Sawtooth](Shapes_images\ElectricalSawtooth.PNG)|
|  | Step| ![Step](Shapes_images\ElectricalStep.PNG)|
|  | SensingLinkSquib| ![SensingLinkSquib](Shapes_images\ElectricalSensingLinkSquib.PNG)|
|  |Indicator | ![Indicator](Shapes_images\ElectricalIndicator.PNG)|
|  | Material| ![Material](Shapes_images\ElectricalMaterial.PNG)|
|  |DelayElement | ![DelayElement](Shapes_images\ElectricalDelayElement.PNG)|
|  | SurgeProtector| ![SurgeProtector](Shapes_images\ElectricalSurgeProtector.PNG)|
|  |SurgeProtector1 | ![SurgeProtector1](Shapes_images\ElectricalSurgeProtector1.PNG)|
|  |PermanentMagnet | ![PermanentMagnet](Shapes_images\ElectricalPermanentMagnet.PNG)|
|  |Magnetoresistor_shape | ![Magnetoresistor_shape](Shapes_images\ElectricalMagnetoresistor_shape.PNG)|
|  | IgnitorPlug| ![IgnitorPlug](Shapes_images\ElectricalIgnitorPlug.PNG)|
|  |Bell | ![Bell](Shapes_images\ElectricalBell.PNG)|
|  | Buzzer| ![Buzzer](Shapes_images\ElectricalBuzzer.PNG)|
|  |ThermalElement | ![ThermalElement](Shapes_images\ElectricalThermalElement.PNG)|
|  | ThermoCouple| ![ThermoCouple](Shapes_images\ElectricalThermoCouple.PNG)|

Find the [Shapes sample](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Shapes) to depict the shapes.









 
 











