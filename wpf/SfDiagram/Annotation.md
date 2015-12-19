# Annotation

Annotation is a block of text that can be displayed over a Node or Connector. Annotation is used to textually represent an object with a string that can be edited at run time. You can add Multiple Labels to a Node/Connector.

Create Annotation

You can add an Annotation to a Node/Connector by defining the label object and adding that to the Annotation collections of Node/Connector. The Text property of label defines the text to be displayed. The following code illustrates how to create an Annotation.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations=new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>Alignment=ConnectorAnnotationAlignment.Center,<br/><br/>HorizontalAlignment=HorizontalAlignment.Center,<br/><br/>VerticalAlignment=VerticalAlignment.Center,<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/>ObservableCollection<ConnectorViewModel> lines = new ObservableCollection<ConnectorViewModel>();<br/><br/>ConnectorViewModel connector = new ConnectorViewModel()<br/><br/>{<br/><br/>SourcePoint = new Point(200, 50),<br/><br/>TargetPoint = new Point(300, 150),<br/><br/>Segments=new ObservableCollection<IConnectorSegment>()<br/><br/>{<br/><br/>new OrthogonalSegment()<br/><br/>{<br/><br/>Direction=OrthogonalDirection.Bottom,<br/><br/>Length=50<br/><br/>}<br/><br/>},<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>}<br/><br/>},<br/><br/>TargetDecoratorStyle = this.diagram.Resources["decoratorstyle1"] as Style,<br/><br/>};<br/><br/>lines.Add(connector);<br/><br/>diagram.Connectors = lines;   <br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img1.jpeg)


Alignment

Annotation can be aligned relative to the Node boundaries. It has margin, Offset, horizontal and vertical alignment settings. It is quite tricky when all four alignments are used together but gives you more control over alignment.

Offset

The Offset property of label is used to align the labels based on fractions. 0 represents top/left corner, 1 represents bottom/right corner, and 0.5 represents half of width/height.

The following image shows the relationship between the Annotation position (black colored circle) and Offset (fraction values).

![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img2.png](Annotation_images/Annotation_img2.jpeg)


By using Offset property, without creating the template we can arrange the Annotaion.

![C:/Users/muniyarajm/Pictures/Screenshot/Connector/offset1.png](Annotation_images/Annotation_img3.jpeg)


Horizontal and vertical alignments

The HorizontalAlignment property of labels is used to set how the label is horizontally aligned at the label position determined from the fraction values. The VerticalAlignment property is used to set how Annotation is vertically aligned at the Annotation position.

The following table illustrates all the possible alignments visually with **Offset** **(****0****,** **0****).**

<table>
<tr>
<td>
Horizontal Alignment<br/><br/></td><td>
Vertical Alignment <br/><br/></td><td>
Output with Offset(0,0)<br/><br/></td></tr>
<tr>
<td>
Left<br/><br/></td><td>
Top<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img3.png](Annotation_images/Annotation_img4.jpeg)'| markdownify }}
<br/><br/><br/><br/><br/><br/></td></tr>
<tr>
<td>
Center<br/><br/></td><td>
<br/><br/></td><td>
<br/><br/>{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img4.png](Annotation_images/Annotation_img5.jpeg)'| markdownify }}
<br/><br/><br/><br/></td></tr>
<tr>
<td>
Right<br/><br/></td><td>
<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img5.png](Annotation_images/Annotation_img6.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Left<br/><br/></td><td>
Center<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img6.png](Annotation_images/Annotation_img7.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Center<br/><br/></td><td>
<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img7.png](Annotation_images/Annotation_img8.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Right<br/><br/></td><td>
<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img8.png](Annotation_images/Annotation_img9.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Left<br/><br/></td><td>
Bottom<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img9.png](Annotation_images/Annotation_img10.jpeg)'| markdownify }}
<br/><br/><br/><br/></td></tr>
<tr>
<td>
Center<br/><br/></td><td>
<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img10.png](Annotation_images/Annotation_img11.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Right<br/><br/></td><td>
<br/><br/></td><td>
{{'![D:/Diagram/Diagram2015Vol4/2015 November 1st Sprint/UG/Diagram Images/Diagram/Label_images/Label_img11.png](Annotation_images/Annotation_img12.jpeg)'| markdownify }}
<br/><br/></td></tr>
</table>
The following table illustrates all the possible alignments visually with **Offset****.**

<table>
<tr>
<td>
Horizontal Alignment<br/><br/></td><td>
Vertical Alignment<br/><br/></td><td>
Offset<br/><br/></td><td>
Image<br/><br/></td></tr>
<tr>
<td>
Center<br/><br/></td><td>
Top<br/><br/></td><td>
(0.2,1)<br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/align1.png](Annotation_images/Annotation_img13.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Right<br/><br/></td><td>
Middle<br/><br/></td><td>
(0.5,0.3)<br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/align2.png](Annotation_images/Annotation_img14.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Left<br/><br/></td><td>
Bottom<br/><br/></td><td>
(0.5,0.7)<br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/align3.png](Annotation_images/Annotation_img15.jpeg)'| markdownify }}
<br/><br/></td></tr>
</table>
The following codes illustrates how to align annotations.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations=new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>Offset=new Point(0,0.5),<br/><br/>Alignment=ConnectorAnnotationAlignment.Center,<br/><br/>HorizontalAlignment=HorizontalAlignment.Left,<br/><br/>VerticalAlignment=VerticalAlignment.Center,<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img16.jpeg)


Margin

Margin is an absolute value used to add some blank space in any one of its four sides. You can displace the Annotations with the Margin property. The following code example illustrates how to align an Annotation based on its Offset, horozontalAlignment, VerticalAlignment and Margin values.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations=new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>Margin=new Thickness(0,10,0,0),<br/><br/>Offset=new Point(0.5,1),<br/><br/>Alignment=ConnectorAnnotationAlignment.Center,<br/><br/>HorizontalAlignment=HorizontalAlignment.Center,<br/><br/>VerticalAlignment=VerticalAlignment.Top,<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img17.jpeg)


The following code illustrates how to displace Annotation through with the Margin property.

<table>
<tr>
<td>
new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>//Based on Offset value, we can align the Annotation<br/><br/>Offset = new Point(0,0),<br/><br/>//Align the Annotation with respect to absolute position<br/><br/>Margin = new Thickness(100,100,0,0),<br/><br/>}<br/><br/><br/><br/></td></tr>
</table>
![C:/Users/muniyarajm/Pictures/Screenshot/Connector/margin1.png](Annotation_images/Annotation_img18.jpeg)


__Annotation__ __Displacement__ __through__ __margin______

Wrapping

When text overflows Node boundaries, you can control it by using text wrapping. So, it is wrapped into multiple lines. The Wrapping property of Annotation defines how the text should be wrapped. The following code illustrates how to wrap a text in a Node.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations=new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation Text Wrapping",<br/><br/>WrapText=TextWrapping.Wrap<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img19.jpeg)


<table>
<tr>
<td>
Values<br/><br/></td><td>
Description<br/><br/></td><td>
Node<br/><br/></td><td>
Connector                                <br/><br/></td></tr>
<tr>
<td>
NoWrap<br/><br/></td><td>
Text will not be wrapped<br/><br/></td><td>
{{'![](Annotation_images/Annotation_img20.jpeg)'| markdownify }}
<br/><br/><br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/nowrap.png](Annotation_images/Annotation_img21.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
Wrap<br/><br/></td><td>
Text-wrapping occurs when the text overflows beyond the available Node width.<br/><br/></td><td>
<br/><br/>{{'![](Annotation_images/Annotation_img22.jpeg)'| markdownify }}
<br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/wrap.png](Annotation_images/Annotation_img23.jpeg)'| markdownify }}
<br/><br/></td></tr>
<tr>
<td>
WrapWithOverflow<br/><br/>(Default)<br/><br/></td><td>
Text-wrapping occurs when the text overflows beyond the available Node width. However, the text may overflow beyond the Node width in the case of a very long word.<br/><br/></td><td>
<br/><br/>{{'![](Annotation_images/Annotation_img24.jpeg)'| markdownify }}
<br/><br/></td><td>
{{'![C:/Users/muniyarajm/Pictures/Screenshot/Connector/wrap.png](Annotation_images/Annotation_img25.jpeg)'| markdownify }}
<br/><br/></td></tr>
</table>
Appearance 

You can change the appearance by ViewTemplate. The following code illustrate how to customize the appearance of an Annotation.

[XAML]

<table>
<tr>
<td>
<DataTemplate x:Key="viewtemplate"><br/><br/><TextBlock Text="{Binding Path=Content, Mode=TwoWay}" FontStyle="Italic" <br/><br/>FontSize="12" FontFamily="TimesNewRomen"<br/><br/>TextDecorations="Underline" FontWeight="Bold"<br/><br/>Foreground="Black"/> <br/><br/></DataTemplate><br/><br/><br/><br/></td></tr>
</table>
[C#]

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation Text",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img26.jpeg)


The fill and border appearance of the text can also be customized with appearance specific properties of Annotation. The following code illustrates how to customize background and border of a Annotation.

[XAML]

<table>
<tr>
<td>
<DataTemplate x:Key="viewtemplate"><br/><br/><Border BorderBrush="Black" BorderThickness="1"><br/><br/><TextBlock Text="{Binding Path=Content, Mode=TwoWay}"  Background="White" <br/><br/>Foreground="Black"/><br/><br/></Border><br/><br/></DataTemplate><br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img27.jpeg)


Drag

An Annotation can be displaced from its original position to any preferred location interactively. Dragging is displaced by default. You can enable label dragging with the Constraints property of Node/Connector. The following code illustrates how to enable Annotation **dragging** for Node.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Constraints=NodeConstraints.Default | NodeConstraints.DragAnnotation,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation Text"<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img28.jpeg)


The following code illustrates how to enable DragAnnotation for Connector.

<table>
<tr>
<td>
connector.Constraints = ConnectorConstraints.Default | ConnectorConstraints.DragAnnotation;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img29.jpeg)


Edit

Diagram provides support to edit an Annotation at runtime, either programmatically or interactively.

Double-clicking any Annotation will enables editing of that. Double-clicking the Node enables first Annotation editing. When the focus of editor is lost, the Annotation for the Node is updated.

The following code illustrates how to edit the Annotation programmatically.

<table>
<tr>
<td>
ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>EditTemplate=this.diagram.Resources["edittemplate"] as DataTemplate,<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>NodeViewModel node1 = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100, <br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 350,<br/><br/>OffsetY = 200,<br/><br/>Constraints = NodeConstraints.Default | NodeConstraints.DragAnnotation,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content="Annotation",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>nodes.Add(node1);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img30.jpeg)


Read Only Annotation

Diagram allows to create read only Annotation. You have to set the readOnly property of Annotation to enable/disable the read only mode. The following code illustrates how to enable **ReadOnly** mode.

<table>
<tr>
<td>
NodeViewModel node1 = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100, <br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 100,<br/><br/>OffsetY = 100,<br/><br/>Annotations = new ObservableCollection<IAnnotation>()<br/><br/>{<br/><br/>new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Annotation",<br/><br/>ViewTemplate = this.diagram.Resources["viewtemplate"] as DataTemplate,<br/><br/>ReadOnly = true<br/><br/>}<br/><br/>},<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/><br/><br/></td></tr>
</table>
Multiple Annotations

You can add any number of Annotations to a Node or Connector. The following code illustrates how to add multiple Annotations to a Node.

<table>
<tr>
<td>
ObservableCollection<AnnotationEditorViewModel> annotations = new ObservableCollection<AnnotationEditorViewModel>();<br/><br/><br/><br/>AnnotationEditorViewModel annotation1 = new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Left",<br/><br/>ViewTemplate=this.diagram.Resources["viewtemplate"] as DataTemplate,<br/><br/>Offset = new Point(0.1, 0.12)<br/><br/>};<br/><br/>AnnotationEditorViewModel annotation2 = new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Center",<br/><br/>ViewTemplate = this.diagram.Resources["viewtemplate"] as DataTemplate,<br/><br/>Offset = new Point(0.5, 0.5)<br/><br/>};<br/><br/>AnnotationEditorViewModel annotation3 = new AnnotationEditorViewModel()<br/><br/>{<br/><br/>Content = "Right",<br/><br/>ViewTemplate = this.diagram.Resources["viewtemplate"] as DataTemplate,<br/><br/>Offset = new Point(0.82, 0.9)<br/><br/>};<br/><br/>annotations.Add(annotation1);<br/><br/>annotations.Add(annotation2);<br/><br/>annotations.Add(annotation3);<br/><br/>ObservableCollection<NodeViewModel> nodes = new ObservableCollection<NodeViewModel>();<br/><br/>NodeViewModel node = new NodeViewModel()<br/><br/>{<br/><br/>UnitWidth = 100,<br/><br/>UnitHeight = 100,<br/><br/>OffsetX = 200,<br/><br/>OffsetY = 200,<br/><br/>Annotations = annotations,<br/><br/>Shape = new RectangleGeometry() { Rect = new Rect(0, 0, 10, 10) },<br/><br/>ShapeStyle = this.diagram.Resources["shapestyle"] as Style<br/><br/>};<br/><br/>nodes.Add(node);<br/><br/>diagram.Nodes = nodes;<br/><br/><br/><br/></td></tr>
</table>
![](Annotation_images/Annotation_img31.jpeg)


