---
layout: post
title: Behaviour-Changes
description: behaviour changes
platform: wpf
control: Diagram
documentation: ug
---

# Behaviour Changes

The following are the changes made from version 10.1.0.44: 

* The Bounds property of DiagramView will not have any effect and instead a new LayoutBounds property has been implemented with Horizontal and Vertical alignment of Diagram within rectangular bounds.
* Hereafter RefreshLayout has to be used to update the layout instead of calling StartNodeArrangement and PrepareActivity methods.

## Frequently Asked Questions

This section comprises an assembled list of questions and answers to provide expert solutions on product and its usage. It contains the following:

Common—Answers common questions that arises in minds of fresh users of Essential Diagram WPF.

Advanced—Answers questions that are in an advanced level, meant for experts.

## Common

This section answers the following common question that arises in the minds of fresh users of Essential Diagram WPF. 

## Refresh the Tree Layout while Binding Dynamic Data to the Diagram

Essential Diagram for WPF provides support to bind dynamic data to the diagram.. But once the new data is assigned, the tree needs to be refreshed. This can be done using the RefreshLayout method. 

The following code can be used to refresh the layout:
{% highlight c# %}




diagramModel.ItemsSource = dataobj;

DirectedTreeLayout tree = new DirectedTreeLayout(diagramModel, diagramView);

tree.RefreshLayout();

{% endhighlight  %}
{% highlight vbnet %}





diagramModel.ItemsSource = dataobj

Dim tree As New DirectedTreeLayout(DiagramModel, DiagramView)

tree.RefreshLayout()

{% endhighlight %}

In case the hierarchical layout is being used, then the following code can be used:

{% highlight c# %}





diagramModel.ItemsSource = dataobj;

HierarchicalTreeLayout tree = new HierarchicalTreeLayout(diagramModel, diagramView);

tree.RefreshLayout();

{% endhighlight %}
{% highlight vbnet %}




diagramModel.ItemsSource = dataobj

Dim tree As New HierarchicalTreeLayout(DiagramModel, DiagramView)

tree.RefreshLayout()

{% endhighlight %}

So once data has been assigned, call the RefreshLayout() method of the corresponding tree-layout.

## Host an UIElement as Node’s Content

You can host any content inside the node using the Content property.
{% highlight c# %}




Node n = new Node();

n.Shape = Shapes.FlowChart_Card;

Button b = new Button();

b.Content = "Click ME!";

n.Content = b;

(n.Content as Button).IsHitTestVisible = true;



{% endhighlight  %}
{% highlight vbnet %}




Dim n As New Node()

n.Shape = Shapes.FlowChart_Card

Dim b As New Button()

b.Content = "Click ME!"

n.Content = b

TryCast(n.Content, Button).IsHitTestVisible = True

{% endhighlight %}

![](Diagram-View_images/Diagram-View_img90.jpeg)



_NodeContent_

Here, Button is a UIElement. Similarly any UIElement can be hosted as Node’s Content.

## Customize Node’s Shape

Users can specify their own custom shapes to be used for the node as follows. First create a style resource that contains your custom shape.
{% highlight html %}




<Style TargetType="{x:Type Path}" x:Key="myNode">

    <Setter Property="Data" Value="M200,239L200,200 240,239 280,202 320,238 281,279 240,244 198,279z"></Setter>

    <Setter Property="Fill" Value="MidnightBlue" />

</Style>

{% endhighlight  %}

Now use it for the node; the following code can be used as an example.
{% highlight c# %}




Style s = (Style)this.Resources["myNode"];

Node n = new Node();

n.Shape = Shapes.CustomPath;

n.CustomPathStyle = s;

diagramModel.Nodes.Add(n);

{% endhighlight %}
{% highlight vbnet %}



Dim s As Style = CType(Me.Resources("myNode"), Style)

Dim n As New Node()

n.Shape = Shapes.CustomPath

n.CustomPathStyle = s

diagramModel.Nodes.Add(n)

{% endhighlight  %}

![](Diagram-View_images/Diagram-View_img91.jpeg)



_CustomNode_

## Apply Style with Triggers for all the Nodes

You can specify style with triggers which is applied to all the Nodes as shown in the following code snippet.
{% highlight html %}




            <Style TargetType="{x:Type syncfusion:Node}" x:Key="{x:Type syncfusion:Node}">

                <Setter Property="LabelHorizontalAlignment" Value="Center"/>

                <Setter Property="LabelVerticalAlignment" Value="Center"/>

                <Setter Property="Foreground" Value="Black"/>

                <Setter Property="FontWeight" Value="Bold"/>

                <Style.Triggers>

                    <Trigger Property="Level"  Value="0">

                        <Setter Property="CustomPathStyle">

                            <Setter.Value>

                                <Style TargetType="{x:Type Path}">

                                    <Setter Property="Fill" Value="LightGray" />

                                </Style>

                            </Setter.Value>

                        </Setter>

                    </Trigger>

                    <Trigger Property="Level"  Value="2">

                        <Setter Property="CustomPathStyle">

                            <Setter.Value>

                                <Style TargetType="{x:Type Path}">

                                    <Setter Property="Fill" Value="LightBlue" />

                                </Style>

                            </Setter.Value>

                        </Setter>

                    </Trigger>

                </Style.Triggers>

            </Style>
{% endhighlight  %}

## Restrict Port Connections

Using the events provided for LineConnectors we can restrict making connections to ports by checking the desired condition in the event handler. 

Let us consider a case where we want to restrict making connections to the port based on the color of the ports, say connections should only happen when the ports are of same color.

There are two scenarios that we need to take care of:

## Scenario 1

In case a new connection is being created by dragging from one port to another, The 
AfterConnectionCreate event can be used. This event fires soon after a new connection is created.

The following is the code example for restricting connections between ports and allowing connecting ports of the same color:
{% highlight c# %}




// Declare the event.

diagramView.AfterConnectionCreate += new ConnDragEndChangedEventHandler(diagramView_AfterConnectionCreate);



// Handle the event.

void diagramView_AfterConnectionCreate(object sender, ConnDragEndRoutedEventArgs evtArgs)

{

LineConnector line = evtArgs.Connector;

if (line.ConnectionTailPort != null && line.ConnectionHeadPort != null && line.ConnectionTailPort.PortStyle.Fill == line.ConnectionHeadPort.PortStyle.Fill)

{

// Do nothing.

}

else

{

// Remove the connection.

diagramModel.Connections.Remove(evtArgs.Connector);

}

}

{% endhighlight  %}
{% highlight vbnet %}




'Declare the event.

Private diagramView.AfterConnectionCreate += New ConnDragEndChangedEventHandler(AddressOf diagramView_AfterConnectionCreate)



'Handle the event.

Private Sub diagramView_AfterConnectionCreate(ByVal sender As Object, ByVal evtArgs As ConnDragEndRoutedEventArgs)

   Dim line As LineConnector = evtArgs.Connector

   If line.ConnectionTailPort IsNot Nothing AndAlso line.ConnectionHeadPort IsNot Nothing       AndAlso line.ConnectionTailPort.PortStyle.Fill = line.ConnectionHeadPort.PortStyle.Fill    Then

     'Do nothing.

   Else

     'Remove the connection.

      diagramModel.Connections.Remove(evtArgs.Connector)

   End If

End Sub


{% endhighlight  %}

## Scenario 2

In case an already existing connection is been dragged to connect to other ports, then the 
ConnectorDragStart and ConnectorDragEnd events can be used to restrict connections.
As the name implies, the ConnectorDragStart event fires when either ends of the connector is dragged.
The ConnectorDragEnd fires soon after the drag operation is complete.
The following is the code example for restricting connections between ports and allow only red ports to connect.
{% highlight c# %}




// Declare the event.

diagramView.ConnectorDragStart += new ConnDragChangedEventHandler(diagramView_ConnectorDragStart);



// To store the previous port to which the line was connected to.

ConnectionPort oldport;



// Handle the event.

void diagramView_ConnectorDragStart(object sender, ConnDragRoutedEventArgs evtArgs)

{

LineConnector line = evtArgs.Connector;

if (evtArgs.FixedNodeEnd == line.TailNode)

oldport = line.ConnectionHeadPort;

else

oldport = line.ConnectionTailPort;

}

{% endhighlight  %}
{% highlight vbnet %}





'Declare the event.

Private diagramView.ConnectorDragStart += New ConnDragChangedEventHandler(AddressOf diagramView_ConnectorDragStart)



        'To store the previous port to which the line was connected to.

        Private oldport As ConnectionPort



        'Handle the event.

Private Sub diagramView_ConnectorDragStart(ByVal sender As Object, ByVal evtArgs As ConnDragRoutedEventArgs)

        Dim line As LineConnector = evtArgs.Connector

        If evtArgs.FixedNodeEnd = line.TailNode Then

            oldport = line.ConnectionHeadPort

        Else

            oldport = line.ConnectionTailPort

        End If

End Sub

{% endhighlight %}

Now once you have stored the oldport, you can check for the condition in ConnectorDragEnd event as follows.
{% highlight c# %}




// Declare the event.

diagramView.ConnectorDragEnd += new ConnDragEndChangedEventHandler(diagramView_ConnectorDragEnd);



// Handle the event.

void diagramView_ConnectorDragEnd(object sender, ConnDragEndRoutedEventArgs evtArgs)

{

LineConnector line = evtArgs.Connector;

if (line.ConnectionTailPort != null && line.ConnectionHeadPort != null &&     line.ConnectionTailPort.PortStyle.Fill ==  line.ConnectionHeadPort.PortStyle.Fill)

{

// Do nothing.

}

else

{

// Check to which end the old port has to be restored.

if (evtArgs.HitNodeEnd == line.HeadNode && oldport != null)

{

evtArgs.Connector.ConnectionHeadPort = oldport;

evtArgs.Connector.HeadNode = oldport.Node;

}

else

{

evtArgs.Connector.ConnectionTailPort = oldport;

evtArgs.Connector.TailNode = oldport.Node;

}

}

}

{% endhighlight %}
{% highlight vbnet %}





'Declare the event.

Private diagramView.ConnectorDragEnd += New ConnDragEndChangedEventHandler(AddressOf diagramView_ConnectorDragEnd)



        'Handle the event.

        Private Sub diagramView_ConnectorDragEnd(ByVal sender As Object, ByVal evtArgs As ConnDragEndRoutedEventArgs)

            Dim line As LineConnector = evtArgs.Connector

            If line.ConnectionTailPort IsNot Nothing AndAlso line.ConnectionHeadPort IsNot Nothing AndAlso line.ConnectionTailPort.PortStyle.Fill = line.ConnectionHeadPort.PortStyle.Fill Then

                'Do nothing.

            Else

                'Check to which end the old port has to be restored.

                If evtArgs.HitNodeEnd = line.HeadNode AndAlso oldport IsNot Nothing Then

                    evtArgs.Connector.ConnectionHeadPort = oldport

                    evtArgs.Connector.HeadNode = oldport.Node

                Else

                    evtArgs.Connector.ConnectionTailPort = oldport

                    evtArgs.Connector.TailNode = oldport.Node

                End If

            End If

        End Sub


{% endhighlight  %}

## Hide Resizer or Rotator’s Visibility of a Node

Gripper or Rotator Visibility can be hidden using the following code example.
{% highlight c# %}




node.Loaded += new RoutedEventHandler(node_Loaded);

//Hide the Node's Resizer and Rotator in the Node's loaded event.

        void node_Loaded(object sender, RoutedEventArgs e)

        {

            Node node = sender as Node;

            //node.Template will be null if it's template is not applied.

            if (node != null && node.Template != null)

            {

                //To hide the Resizer.

                (node.Template.FindName("PART_Resizer", node) as Control).Template = null;

                //To hide the Rotator.

                (node.Template.FindName("PART_Rotator", node) as Control).Template = null;

            }

        }

{% endhighlight  %}
{% highlight vbnet %}





  Private node.Loaded += New RoutedEventHandler(AddressOf node_Loaded)

  'Hide the Node's Resizer and Rotator in the Node's loaded event.

   Private Sub node_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)

      Dim node As Node = TryCast(sender, Node)

      'node.Template will be null if it's template is not applied.

      If node IsNot Nothing AndAlso node.Template IsNot Nothing Then

        'To hide the Resizer.

        TryCast(node.Template.FindName("PART_Resizer", node), Control).Template = Nothing

        'To hide the Rotator.

        TryCast(node.Template.FindName("PART_Rotator", node), Control).Template = Nothing

      End If

    End Sub

{% endhighlight %}

N> Node’s Template will be available only after its template is applied, so if you try to do these operations before it will not give an expected result.

## Hide the Default Center Port of a Node

Each node will have a default center port visibility of this port can be hidden using the following statement.
{% highlight c# %}




node.Loaded += new RoutedEventHandler(node_Loaded);

        //Hide the Node's center port in the Node's loaded event.

        void node_Loaded(object sender, RoutedEventArgs e)

        {

            Node node = sender as Node;

            if (node.Ports.Count > 0)

            {

                node.Ports[0].Visibility = Visibility.Hidden;

            }

        }

{% endhighlight  %}
{% highlight vbnet %}





       Private node.Loaded += New RoutedEventHandler(AddressOf node_Loaded)

        'Hide the Node's center port in the Node's loaded event.

        Private Sub node_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)

            Dim node As Node = TryCast(sender, Node)

            If node.Ports.Count > 0 Then

                node.Ports(0).Visibility = Visibility.Hidden

            End If

        End Sub

{% endhighlight  %}


N> node.Ports[0] refers to the center port. This default center port will be available only after the Node’s Template is applied. So you have to change the Visibility accordingly.

## Programmatically Rotate a Node and Keep the Label Horizontal after Rotating

Node can be programmatically rotated and the Label can be kept horizontal after rotation using the following code example.
{% highlight c# %}




Node NewClient = new Node();

NewClient.Shape = Shapes.FlowChart_Card;

diagramModel.Nodes.Add(NewClient);



double angle = 90;

NewClient.RenderTransform = new RotateTransform(angle);

NewClient.Label = "90 deg rotation";

NewClient.RenderTransformOrigin = new System.Windows.Point(0.5, 0.5);

NewClient.LabelAngle = 360 - angle;

{% endhighlight  %}
{% highlight vbnet %}







Dim NewClient As New Node()

NewClient.Shape = Shapes.FlowChart_Card

diagramModel.Nodes.Add(NewClient)



Dim angle As Double = 90

NewClient.RenderTransform = New RotateTransform(angle)

NewClient.Label = "90 deg rotation"

NewClient.RenderTransformOrigin = New System.Windows.Point(0.5, 0.5)

NewClient.LabelAngle = 360 - angle


{% endhighlight  %}
Here diagramModel is an instance of DiagramModel.

## Identify the Shapes Dropped on the Page from the Palette

The SymbolPaletteItemName property can be used to identify the item dropped on the page in the NodeDrop event. This is particularly useful when you have to identify the item which is dropped and performs an operation on the node before it is added to the View. The Name property of the SymbolPaletteItem can be set while adding the item to the palette and thenby using SymbolPaletteItemName property in the eventargs of NodeDrop.A reference to the corresponding SymbolPaletteItem can be obtained.
{% highlight c# %}




SymbolPaletteItem ss = new SymbolPaletteItem();

Label l = new Label();

l.Content = "Label";

ss.Content = l;

ss.Name = "MyItem";

{% endhighlight %}
{% highlight vbnet %}





Dim ss As New SymbolPaletteItem()

Dim l As New Label()

l.Content = "Label"

ss.Content = l

ss.Name = "MyItem"

{% endhighlight %}

The NodeDrop event can be declared:
{% highlight c# %}




// Declare the event.

diagramView.NodeDrop += new NodeDroppedEventHandler(diagramView_NodeDrop);

// Handle the event.

void diagramView_NodeDrop(object sender, NodeDroppedRoutedEventArgs evtArgs)

{

if(evtArgs.SymbolPaletteItemName=="MyItem")

{

// User-specified code.

}}

{% endhighlight %}
{% highlight vbnet %}





'Declare the event.

Private diagramView.NodeDrop += New NodeDroppedEventHandler(AddressOf diagramView_NodeDrop)



        'Handle the event.

        Private Sub diagramView_NodeDrop(ByVal sender As Object, ByVal evtArgs As NodeDroppedRoutedEventArgs)

            If evtArgs.SymbolPaletteItemName = "MyItem" Then

                'User-specified code.

            End If

        End Sub
{% endhighlight %}

## Hide ContextMenu for all Nodes and Connections

ContextMenu for all Nodes and LineConnectors can be hidden using the following code snippet.
{% highlight c# %}



diagramView.NodeContextMenu = new ContextMenu { Visibility = Visibility.Collapsed };

diagramView.LineConnectorContextMenu = new ContextMenu { Visibility = Visibility.Collapsed };


{% endhighlight %}

{% highlight vbnet %}



diagramView.NodeContextMenu = New ContextMenu With {.Visibility = Visibility.Collapsed}

diagramView.LineConnectorContextMenu = New ContextMenu With {.Visibility = Visibility.Collapsed}

{% endhighlight  %}

Where, diagramView is an instance of DiagramView

## How can the nudge operation be stopped?

The nudge operation can be stopped by handling the DiagramControl’s PreviewKeyDown event, as shown in the code example displayed below.
{% highlight c# %}


        //Register the PreviewKeyDown event.

        diagramControl.PreviewKeyDown += new KeyEventHandler(MainWindow_PreviewKeyDown);

        //Handle the PreviewKeyDown event for the arrow keys.

        void MainWindow_PreviewKeyDown(object sender, KeyEventArgs e)

        {

            if (e.Key == Key.Up || e.Key == Key.Down || e.Key == Key.Right || e.Key == Key.Left)

            {

                e.Handled = true;

            }

        }
{% endhighlight  %}
{% highlight vbnet %}




'Register the PreviewKeyDown event.

Private diagramControl.PreviewKeyDown += New KeyEventHandler(AddressOf MainWindow_PreviewKeyDown)

        'Handle the PreviewKeyDown event for the arrow keys.

        Private Sub MainWindow_PreviewKeyDown(ByVal sender As Object, ByVal e As KeyEventArgs)

            If e.Key = Key.Up OrElse e.Key = Key.Down OrElse e.Key = Key.Right OrElse e.Key = Key.Left Then

                e.Handled = True

            End If

        End Sub
{% endhighlight  %}

##  How can MultipleTrigger be applied for a Node?

MultiTrigger enables you to set the property values or start actions based on a collection of conditions. A condition is met when the element’s property value matches the specified value. This comparison is performed by a reference equality check. The following example shows how to use MultipleTrigger.
{% highlight html %}


    <Style.Triggers>

        <MultiTrigger>

            <MultiTrigger.Conditions>

                <Condition Property="IsSelected" Value="True"/>

                <Condition Property="Tag" Value="True"/>

            </MultiTrigger.Conditions>

            <Setter Property="Effect">

                <Setter.Value>

                    <DropShadowEffect Color="Gray" BlurRadius="5" Direction="325" ShadowDepth="5"/>

                </Setter.Value>

            </Setter>

        </MultiTrigger>

    </Style.Triggers>

{% endhighlight %}

If a Node has the above Trigger set in its Style, then the Node will have a DropShadowEffect when both the IsSelected property and the Tag property are set to True.

##  Advanced

This section answers the following questions that are in an advanced level, meant for experts.

## Animate the Dodes in the Diagram

You can perform many kinds of animations on nodes by using the double animation. Rotation and Translation are some of the basic operations performed on the nodes. You can use double animation to perform these operations on the node in a specific pattern.

To rotate a node, the following code can be used.
{% highlight c# %}




DoubleAnimation nodeanimation = new DoubleAnimation();

nodeanimation.From = 0;

nodeanimation.To = 360;

nodeanimation.Duration = new Duration(new TimeSpan(0, 0, 0, 0, 500));

nodeanimation.RepeatBehavior = new RepeatBehavior(15);



RotateTransform rt = new RotateTransform();

nodeObj.RenderTransform = rt;

nodeObj.RenderTransformOrigin = new Point(.5, .5);

rt.BeginAnimation(RotateTransform.AngleProperty, nodeanimation);

{% endhighlight  %}
{% highlight vbnet %}





Dim nodeanimation As New DoubleAnimation()

nodeanimation.From = 0

nodeanimation.To = 360

nodeanimation.Duration = New Duration(New TimeSpan(0, 0, 0, 0, 500))

nodeanimation.RepeatBehavior = New RepeatBehavior(15)



Dim rt As New RotateTransform()

nodeObj.RenderTransform = rt

nodeObj.RenderTransformOrigin = New Point(.5,.5)

rt.BeginAnimation(RotateTransform.AngleProperty, nodeanimation)


{% endhighlight  %}
To translate a node with respect to the x-axis, the TranslateTransform can be applied.


{% highlight c# %}




DoubleAnimation nodeanimation = new DoubleAnimation();

nodeanimation.From = 500;

nodeanimation.To = 0;

nodeanimation.Duration = new Duration(new TimeSpan(0, 0, 0, 0, 500));

nodeanimation.RepeatBehavior = new RepeatBehavior(1);

{% endhighlight  %}
{% highlight  vbnet %}





Dim nodeanimation As New DoubleAnimation()

nodeanimation.From = 500

nodeanimation.To = 0

nodeanimation.Duration = New Duration(New TimeSpan(0, 0, 0, 0, 500))

nodeanimation.RepeatBehavior = New RepeatBehavior(1)
{% endhighlight  %}


Once you have created the double animation, you can then apply it to the node which we want to translate in the following way.

{% highlight c# %}





DoubleAnimation nodeanimation = new DoubleAnimation();

nodeanimation.From = 500;

nodeanimation.To = 0;

nodeanimation.Duration = new Duration(new TimeSpan(0, 0, 0, 0, 500));

nodeanimation.RepeatBehavior = new RepeatBehavior(1);



TranslateTransform rt = new TranslateTransform();

nodeObj.RenderTransform = rt;

rt.BeginAnimation(TranslateTransform.XProperty, nodeanimation);


{% endhighlight  %}
{% highlight vbnet %}




Dim nodeanimation As New DoubleAnimation()

nodeanimation.From = 500

nodeanimation.To = 0

nodeanimation.Duration = New Duration(New TimeSpan(0, 0, 0, 0, 500))

nodeanimation.RepeatBehavior = New RepeatBehavior(1)



Dim rt As New TranslateTransform()

nodeObj.RenderTransform = rt

rt.BeginAnimation(TranslateTransform.XProperty, nodeanimation)
{% endhighlight  %}

## Print DiagramPage in Uniform Print Mode Using Framework Print Dialog

DiagramPage can also be printed using Framework PrintDialog instead of using syncfusion DiagramControlPrintPreview Dialog, as shown in the following code example.

{% highlight c# %}



     //Create Framwork Print Dialog.

            PrintDialog PrintDialog = new PrintDialog();

            //Open Print Dialog.

            Nullable<Boolean> printClicked = PrintDialog.ShowDialog();



            //If Print is clicked.

            if (printClicked == true)

            {

                //Print the Diagram Page.

                //Get Printer Capabilities.

                PrintCapabilities printCapabilities = PrintDialog.PrintQueue.GetPrintCapabilities(PrintDialog.PrintTicket);

                Size pageAreaSize = new Size(printCapabilities.PageImageableArea.ExtentWidth, printCapabilities.PageImageableArea.ExtentHeight);



                //Visual Brush for the DiagramPage to be printed.

                VisualBrush VisualBrush = new VisualBrush(diagramView.Page);

                VisualBrush.Stretch = Stretch.Uniform;

                VisualBrush.ViewboxUnits = BrushMappingMode.Absolute;

                VisualBrush.Viewbox = new Rect(0, 0, diagramView.Page.ActualWidth, diagramView.Page.ActualHeight);



                //Rectangle to contain the VisualBrush. 

                Rectangle rect = new Rectangle();

                rect.Fill = VisualBrush;

                rect.Arrange(new Rect(new Point(0, 0), pageAreaSize));

                SetViewport(VisualBrush, new Size(diagramView.Page.ActualWidth, diagramView.Page.ActualHeight));



                //Print the Page.

                XpsDocumentWriter writer = PrintQueue.CreateXpsDocumentWriter(PrintDialog.PrintQueue);

                writer.Write(rect, PrintDialog.PrintTicket);

            }



        //Paint the brush to fit uniformly.

        private void SetViewport(VisualBrush brush, Size size)

        {

            double coefficientHeight = size.Height / brush.Viewbox.Height;

            double coefficientWidth = size.Width / brush.Viewbox.Width;



            if (coefficientHeight < coefficientWidth)

            {

                double width = coefficientHeight * brush.Viewbox.Width / size.Width;

                double x = (1 - width) / 2;

                brush.Viewport = new Rect(new Point(x, 0), new Size(width, 1));

            }

            else if (coefficientHeight > coefficientWidth)

            {

                double height = coefficientWidth * brush.Viewbox.Height / size.Height;

                double y = (1 - height) / 2;

                brush.Viewport = new Rect(new Point(0, y), new Size(1, height));

            }

        }



{% endhighlight  %}
{% highlight vbnet %}





     'Create Framwork Print Dialog.

        Dim PrintDialog As New PrintDialog()

        'Open Print Dialog.

        Dim printClicked As Nullable(Of Boolean) = PrintDialog.ShowDialog()



        'If Print is clicked.

If printClicked.GetValueOrDefault() = True Then

        'Print the Diagram Page.

        'Get Printer Capabilities.

        Dim printCapabilities As PrintCapabilities = PrintDialog.PrintQueue.GetPrintCapabilities(PrintDialog.PrintTicket)

        Dim pageAreaSize As New Size(PrintCapabilities.PageImageableArea.ExtentWidth, PrintCapabilities.PageImageableArea.ExtentHeight)



        'Visual Brush for the DiagramPage to be printed.

        Dim VisualBrush As New VisualBrush(DiagramView.Page)

VisualBrush.Stretch = Stretch.Uniform

VisualBrush.ViewboxUnits = BrushMappingMode.Absolute

VisualBrush.Viewbox = New Rect(0, 0, diagramView.Page.ActualWidth, diagramView.Page.ActualHeight)



        'Rectangle to contain the VisualBrush. 

        Dim rect As New Rectangle()

rect.Fill = VisualBrush

rect.Arrange(New Rect(New Point(0, 0), pageAreaSize))

SetViewport(VisualBrush, New Size(diagramView.Page.ActualWidth, diagramView.Page.ActualHeight))



        'Print the Page.

        Dim writer As XpsDocumentWriter = PrintQueue.CreateXpsDocumentWriter(PrintDialog.PrintQueue)

writer.Write(rect, PrintDialog.PrintTicket)

End If



        'Paint the brush to fit uniformly.

private void SetViewport(VisualBrush brush, Size size)

        Dim coefficientHeight As Double = Size.Height / Brush.Viewbox.Height

        Dim coefficientWidth As Double = Size.Width / Brush.Viewbox.Width



If coefficientHeight < coefficientWidth Then

        Dim width As Double = coefficientHeight * Brush.Viewbox.Width / Size.Width

        Dim x As Double = (1 - Width) / 2

brush.Viewport = New Rect(New Point(x, 0), New Size(width, 1))

ElseIf coefficientHeight > coefficientWidth Then

        Dim height As Double = coefficientWidth * Brush.Viewbox.Height / Size.Height

        Dim y As Double = (1 - Height) / 2

brush.Viewport = New Rect(New Point(0, y), New Size(1, height))

End If
{% endhighlight  %}

## Save the Current Zoom Settings and Load the Settings Back

Zoom settings can be saved into variables and this saved settings can be applied back again using the following code example.
{% highlight c# %}


            //Save current zoom setting.

            double SavedZoomFactor = diagramView.ZoomFactor;

            double SavedCurrentZoom = (double) diagramView.GetValue(DiagramView.CurrentZoomProperty);





            //Load the saved zoom settings.

            //Reset the current zoom

            ZoomCommands.Reset.Execute(diagramView.Page, diagramView);

            //Set the zoom factor temporarily to the stored CurrentZoomProperty 

            diagramView.ZoomFactor = SavedCurrentZoom - 1;

            //Now if a zoom operation is performed, we will get the stored zoom setting.

            ZoomCommands.ZoomIn.Execute(diagramView.Page, diagramView);

            //Change the Zoom factor to the required value.

            diagramView.ZoomFactor = SavedZoomFactorr;

{% endhighlight  %}
{% highlight vbnet %}





'Save current zoom setting.

        Dim SavedZoomFactor As Double = DiagramView.ZoomFactor

        Dim SavedCurrentZoom As Double = CDbl(DiagramView.GetValue(DiagramView.CurrentZoomProperty))



        'Load the saved zoom settings.

        'Reset the current zoom

ZoomCommands.Reset.Execute(diagramView.Page, diagramView)

        'Set the zoom factor temporarily to the stored CurrentZoomProperty 

diagramView.ZoomFactor = SavedCurrentZoom - 1

        'Now if a zoom operation is performed, we will get the stored zoom setting.

ZoomCommands.ZoomIn.Execute(diagramView.Page, diagramView)

        'Change the Zoom factor to the required value.

diagramView.ZoomFactor = SavedZoomFactorr
{% endhighlight  %}

## Label Alignment

You are provided with a lot more alignment options to customize Label of Node and Connector.

_Label Alignment_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Property Type</th><th>
Accepted Value</th><th>
Any other dependencies/ sub-properties associated</th></tr>
<tr>
<td>
LabelHorizontalTextAllignment</td><td>
Specifies the Horizontal Text alignment of the Label. </td><td>
Dependency property</td><td>
HorizontalAlignment.CenterHorizontalAlignment.LeftHorizontalAlignment.RightHorizontalAlignment.Stretch;</td><td>
No</td></tr>
<tr>
<td>
LabelVerticalTextAllignment</td><td>
Specifies the Vertical Text alignment of the Label.</td><td>
Dependency property</td><td>
VerticalAlignment.Center;VerticalAlignment.Top;VerticalAlignment.Bottom;VerticalAlignment.Stretch;</td><td>
No</td></tr>
</table>


The following code snippet depicts the behavior of LabelHorizontalTextAllignment and LabelVerticalTextAllignment.
{% highlight c# %}


Node node = new Node();

node.Label = "LabelText";

node.Shape = Shapes.FlowChart_Decision;

node.LabelHorizontalTextAlignment = HorizontalAlignment.Right;

node.LabelVerticalTextAlignment = VerticalAlignment.Top;


{% endhighlight %}
![C:/Users/saranya/Desktop/text.jpg](Diagram-View_images/Diagram-View_img92.jpeg)



_LabelAllignment_

##  Label Resizer

You are provided with support for Label Selection and Resizing at runtime. This feature can be enabled by using IsEnableLabelSelection property in DiagramView. By enabling this property you are able to resize, drag and rotate the LabelEditor like Nodes. The default value is “False”.

_Label Resizer_

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Property Type</th><th>
Accepted Value</th><th>
Any other dependencies/ sub-properties associated</th></tr>
<tr>
<td>
IsEnableLabelSelection</td><td>
Gets or sets a value indicating whether to select the node or not. The default value is “False”.</td><td>
Dependency property</td><td>
Boolean (True/False)</td><td>
No</td></tr>
</table>


The following code example is used to enable LabelEditor for Nodes.
{% highlight c# %}


DiagramView view = new DiagramView();

view.IsEnableLabelSelection = true;

Node node = new Node();

node.LabelWidth = 100;

node.LabelHeight = 100;

node.Label = "LabelEditor";

{% endhighlight  %}

![C:/Users/saranya/Desktop/ls.jpg](Diagram-View_images/Diagram-View_img93.jpeg)



_LableEditor for Node_

The following code example is used to enable LabelEditor for Connectors.
{% highlight c# %}


DiagramView view = new DiagramView();

view.IsEnableLabelSelection = true;

LineConnector conn = new LineConnector();

conn.LabelWidth = 100;

conn.LabelHeight = 100;

conn.Label = "LabelEditor";
{% endhighlight %}

![](Diagram-View_images/Diagram-View_img94.jpeg)



_LabelEditor for Connector_





