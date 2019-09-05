---
layout: post
title: Basic Shapes with Syncfusion Essential Diagram for WPF.
description: How do add different shapes to diagram 
platform: wpf
control: SfDiagram
documentation: ug
---

# Shapes

We have provided some basic built-in shapes as ResourceDictionary.

The following code example illustrates how to merge shapes into diagram.

{% highlight xaml %}
<ResourceDictionary.MergedDictionaries>
       <!--Initialize Shapes-->
       <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
</ResourceDictionary.MergedDictionaries>  
{% endhighlight %}


## Basic Shapes

The following code example illustrates how to assign Shape property of the Node.

{% highlight xaml %}
<!--Style for Node-->
<Style TargetType="syncfusion:Node" >
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
{% endhighlight %}
{% highlight xaml %}
<!--Add Node with basic shape-->
<syncfusion:NodeViewModel x:Name="Node" UnitHeight="100" UnitWidth=" 100" OffsetX="100" OffsetY="100" 
                          Shape="{StaticResource Rectangle}"
                          ShapeStyle="{StaticResource shapestyle}"/>   
{% endhighlight %}

Output Node will be,

 ![Shapes_image1](Shapes_images\Shapes_image1.PNG)
  
 The list of shapes are available in the resource dictionary as follows
 
| Shape Category | Shape Name | Output Shape |
|---|---|---|
| Basic Shapes | Rectangle | ![](Shapes_images\BasicRectangle.PNG) |
|  | Triangle| ![](Shapes_images\BasicTriangle.PNG) |
|  | Plus| ![](Shapes_images\BasicPlus.PNG) |
|  | Pentagon | ![](Shapes_images\BasicPentagon.PNG) |
|  | Hexagon | ![](Shapes_images\BasicHexagon.PNG) |
|  |Heptagon | ![](Shapes_images\BasicHeptagon.PNG) |
|  | Octagon | ![](Shapes_images\BasicOctagon.PNG) |
|  |Trapezoid | ![](Shapes_images\BasicTrapezoid.PNG) |
|  | Decagon|![](Shapes_images\BasicDecagon.PNG) |
|  | RightTriangle| ![](Shapes_images\BasicRightTriangle.PNG)|
|  | Cylinder| ![](Shapes_images\BasicCylinder.PNG)|
|  | Diamond| ![](Shapes_images\BasicDiamond.PNG)|
|  |TwoSideFlatCorner | ![](Shapes_images\BasicTwoSideFlatCorner.PNG)|
|  | TwoSideRoundCorner| ![](Shapes_images\BasicTwoSideRoundCorner.PNG)|
|  |RoundedRectangle | ![](Shapes_images\BasicRoundedRectangle.PNG)|
|  | Cloud | ![](Shapes_images\BasicCloud.PNG)|
|  |CloudCallOut | ![](Shapes_images\BasicCloudCallOut.PNG)|
|  | Paralleogram| ![](Shapes_images\BasicParalleogram.PNG)|
|  |Frame | ![](Shapes_images\BasicFrame.PNG)|
|  | Donut| ![](Shapes_images\BasicDonut.PNG)|
|  |RectangleCallOut | ![](Shapes_images\BasicRectangleCallOut.PNG)|
|  |RoundedRectangleCallOut | ![](Shapes_images\BasicRoundedRectangleCallOut.PNG)|
|  | OvalCallOut| ![](Shapes_images\BasicOvalCallOut.PNG)|
|  | Cube| ![](Shapes_images\BasicCube.PNG)|
|  |NoSymbol | ![](Shapes_images\BasicNoSymbol.PNG)|
|  |FourPointStar | ![](Shapes_images\BasicFourPointStar.PNG)|
|  |FivePointStar | ![](Shapes_images\BasicFivePointStar.PNG)|
|  | SixPointStar| ![](Shapes_images\BasicSixPointStar.PNG)|
|  |SevenPointStar | ![](Shapes_images\BasicSevenPointStar.PNG)|
|  |SixteenPointStar | ![](Shapes_images\BasicSixteenPointStar.PNG)|
|  |TwentyFourPointStar | ![](Shapes_images\BasicTwentyFourPointStar.PNG)|
|  |ThirtyTwoPointStar | ![](Shapes_images\BasicThirtyTwoPointStar.PNG)|
| Flow Shapes |Process | ![](Shapes_images\FlowProcess.PNG)|
|  | Decision| ![](Shapes_images\FlowDecision.PNG)|
|  |Terminator | ![](Shapes_images\FlowTerminator.PNG)|
|  |Sort | ![](Shapes_images\FlowSort.PNG)|
| |Document | ![](Shapes_images\FlowDocument.PNG)|
|  |MultiDocument | ![](Shapes_images\FlowMultiDocument.PNG)|
| |DirectData | ![](Shapes_images\FlowDirectData.PNG)|
|  |SequentialData | ![](Shapes_images\FlowSequentialData.PNG)|
|  |PaperTap | ![](Shapes_images\FlowPaperTap.PNG)|
|  | Collate| ![](Shapes_images\FlowCollate.PNG)|
|  | SummingJunction| ![](Shapes_images\FlowSummingJunction.PNG)|
|  |Or | ![](Shapes_images\FlowOr.PNG)|
| |InternalStorage | ![](Shapes_images\FlowInternalStorage.PNG)|
|  |PredefinedProcess | ![](Shapes_images\FlowPredefinedProcess.PNG)|
| |Extract | ![](Shapes_images\FlowExtract.PNG)|
|  |Merge | ![](Shapes_images\FlowMerge.PNG)|
|  | OffPageReference| ![](Shapes_images\FlowOffPageReference.PNG)|
|  |SequentialAccessStorage | ![](Shapes_images\FlowSequentialAccessStorage.PNG)|
|  |Delay | ![](Shapes_images\FlowDelay.PNG)|
|  | StoredData| ![](Shapes_images\FlowStoredData.PNG)|
|  |Display | ![](Shapes_images\FlowDisplay.PNG)|
|  |ManualOperation | ![](Shapes_images\FlowManualOperation.PNG)|
|  |Data | ![](Shapes_images\FlowData.PNG)|
|  | OnPageReference| ![](Shapes_images\FlowOnPageReference.PNG)|
|  |Prepration | ![](Shapes_images\FlowPrepration.PNG)|
|  |PunchedCard | ![](Shapes_images\FlowPunchedCard.PNG)|
|  |Card | ![](Shapes_images\FlowCard.PNG)|
|  | LoopLimit| ![](Shapes_images\FlowLoopLimit.PNG)|
|  |ManualInput | ![](Shapes_images\FlowManualInput.PNG)|
| Arrow Shapes |CurvedDownArrow | ![](Shapes_images\ArrowCurvedDownArrow.PNG)|
|  | CurvedLeftArrow| ![](Shapes_images\ArrowCurvedLeftArrow.PNG)|
|  |CurvedRightArrow| ![](Shapes_images\ArrowCurvedRightArrow.PNG)|
|  | CurvedUpArrow| ![](Shapes_images\ArrowCurvedUpArrow.PNG)|
|  |CircularArrow | ![](Shapes_images\ArrowCircularArrow.PNG)|
|  | JumpingLeftArrow| ![](Shapes_images\ArrowJumpingLeftArrow.PNG)|
|  | JumpingRightArrow| ![](Shapes_images\ArrowJumpingRightArrow.PNG)|
|  |UTurnArrow | ![](Shapes_images\ArrowUTurnArrow.PNG)|
|  | LeftArrow| ![](Shapes_images\ArrowLeftArrow.PNG)|
|  |RightArrow | ![](Shapes_images\ArrowRightArrow.PNG)|
|  |DoubleArrow | ![](Shapes_images\ArrowDoubleArrow.PNG)|
|  |TopArrow | ![](Shapes_images\ArrowTopArrow.PNG)|
|  |BottomArrow | ![](Shapes_images\ArrowBottomArrow.PNG)|
|  | MultiArrow| ![](Shapes_images\ArrowMultiArrow.PNG)|
|  |BlockArrow | ![](Shapes_images\ArrowBlockArrow.PNG)|
|  |QuadBlockArrow | ![](Shapes_images\ArrowQuadBlockArrow.PNG)v|'
|  | NotchedArrow| ![](Shapes_images\ArrowNotchedArrow.PNG)|
|  |LeftRightBlockArrow | ![](Shapes_images\ArrowLeftRightBlockArrow.PNG)|
|  |QuadArrow | ![](Shapes_images\ArrowQuadArrow.PNG)|
|  |FlexibleArrow | ![](Shapes_images\ArrowFlexibleArrow.PNG)|
|Data Flow Shapes  |OvalProcess | ![](Shapes_images\DataFlowOvalProcess.PNG)|
|  |ExternalIndicator | ![](Shapes_images\DataFlowExternalIndicator.PNG)|
|  |Object | ![](Shapes_images\DataFlowObject.PNG)|
|  |MultipleProcess | ![](Shapes_images\DataFlowMultipleProcess.PNG)|
|  |State | ![](Shapes_images\DataFlowState.PNG)|
|  | Stop1| ![](Shapes_images\DataFlowStop1.PNG)|
|  |Entity1 | ![](Shapes_images\DataFlowEntity1.PNG)|
|  |Entity2 | ![](Shapes_images\DataFlowEntity2.PNG)|
|Electrical Shapes  |Resistor | ![](Shapes_images\ElectricalResistor.PNG)|
|  |Capacitor | ![](Shapes_images\ElectricalCapacitor.PNG)|
|  | AC| ![](Shapes_images\ElectricalAC.PNG)|
|  |Dc1 | ![](Shapes_images\ElectricalDc1.PNG)|
|  |EquiPotent | ![](Shapes_images\ElectricalEquiPotent.PNG)|
|  | Inductor| ![](Shapes_images\ElectricalInductor.PNG)|
|  |Crystal | ![](Shapes_images\ElectricalCrystal.PNG)|
|  | Attenuator| ![](Shapes_images\ElectricalChassis.PNG)|
|  | Antenna| ![](Shapes_images\ElectricalAntenna.PNG)|
|  | LoopAntenna| ![](Shapes_images\ElectricalLoopAntenna.PNG)|
|  |CircuitBreaker | ![](Shapes_images\ElectricalCircuitBreaker.PNG)|
|  |Fuse | ![](Shapes_images\ElectricalFuse.PNG)|
|  | IdealSource| ![](Shapes_images\ElectricalIdealSource.PNG)|
|  |GenericComponent | ![](Shapes_images\ElectricalGenericComponent.PNG)|
|  |Transducer | ![](Shapes_images\ElectricalTransducer.PNG)|
|  |Transducer2 | ![](Shapes_images\ElectricalTransducer2.PNG)|
|  |PickupHead | ![](Shapes_images\ElectricalPickupHead.PNG)|
|  |HalfConductor | ![](Shapes_images\ElectricalHalfConductor.PNG)|
|  | Pulse| ![](Shapes_images\ElectricalPulse.PNG)|
|  |Pulse1 | ![](Shapes_images\ElectricalPulse1.PNG)|
|  |Sawtooth | ![](Shapes_images\ElectricalSawtooth.PNG)|
|  | Step| ![](Shapes_images\ElectricalStep.PNG)|
|  | SensingLinkSquib| ![](Shapes_images\ElectricalSensingLinkSquib.PNG)|
|  |Indicator | ![](Shapes_images\ElectricalIndicator.PNG)|
|  | Material| ![](Shapes_images\ElectricalMaterial.PNG)|
|  |DelayElement | ![](Shapes_images\ElectricalDelayElement.PNG)|
|  | SurgeProtector| ![](Shapes_images\ElectricalSurgeProtector.PNG)|
|  |SurgeProtector1 | ![](Shapes_images\ElectricalSurgeProtector1.PNG)|
|  |PermanentMagnet | ![](Shapes_images\ElectricalPermanentMagnet.PNG)|
|  |Magnetoresistor_shape | ![](Shapes_images\ElectricalMagnetoresistor_shape.PNG)|
|  | IgnitorPlug| ![](Shapes_images\ElectricalIgnitorPlug.PNG)|
|  |Bell | ![](Shapes_images\ElectricalBell.PNG)|
|  | Buzzer| ![](Shapes_images\ElectricalBuzzer.PNG)|
|  |ThermalElement | ![](Shapes_images\ElectricalThermalElement.PNG)|
|  | ThermoCouple| ![](Shapes_images\ElectricalThermoCouple.PNG)|












 
 











