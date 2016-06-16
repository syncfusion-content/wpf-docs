---
layout: post
title: Create custom connection points to draw connections with any specific point of Node.
description: How to draw connections with specific points of Node?
platform: wpf
control: SfDiagram
documentation: ug
---

#Port

Essential Diagram for WPF provides support to define ports for making connections.

![](Port_images/Port_img1.jpeg)![](Port_images/Port_img2.jpeg)

When a Connector is connected between two Nodes, its end points are automatically docked to Node’s nearest boundary as shown in the following image.

![](Port_images/Port_img3.jpeg)

Port act as the connection points of node and allows to create connections with only specific points as shown in the following image.

![](Port_images/Port_img4.jpeg)![](Port_images/Port_img5.jpeg)

###Data Binding

In order to achieve Properties of ViewModel are bind to View, we have provided the Default Style for View in “BindingStyle.xaml”. For more information, refer to [Data Binding](/wpf/sfdiagram/Data-Binding).

##Node Port

###Add ports to Nodes

To add a collection port, you need to define the port object and add it to `Ports` property of Node. The `NodeOffsetX` and `NodeOffsetY` property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports to the Node.

The following code illustrates how to add ports to Node.

[XAML]

{% highlight xaml %}

<!--Style for Node-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="DarkCyan"></Setter>
				<Setter Property="Stroke" Value="Black"></Setter>
       	        <Setter Property="StrokeThickness" Value="2"></Setter>
				<Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
		</Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
        	<RectangleGeometry Rect="0,0,10,10"/>
       	</Setter.Value>
	</Setter>
</Style>

<!--Style for NodePort-->
<Style TargetType="syncfusion:NodePort" BasedOn="{StaticResource NodePortBindingStyle}">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
		</Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
        	<RectangleGeometry Rect="0,0,10,10"/>
        </Setter.Value>
	</Setter>
</Style>

{% endhighlight %}

[C#]

{% highlight C# %}

//Create port collection
public class PortCollection : ObservableCollection<IPort>
{

}

{% endhighlight %}

[XAML]

{% highlight xaml %}

<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible">
	<syncfusion:SfDiagram.Nodes>
		<syncfusion:NodeCollection>
        	<syncfusion:NodeViewModel x:Name="node" OffsetX="100" 
				                      OffsetY="100" UnitHeight="100"
									  UnitWidth="100">                                    
				<syncfusion:NodeViewModel.Ports>
					<local:PortCollection>
						<syncfusion:NodePortViewModel x:Name="port" UnitWidth="10"
                                                      UnitHeight="10" NodeOffsetX="0.5"
                                                      NodeOffsetY="0.5">
						</syncfusion:NodePortViewModel>
					</local:PortCollection>
                </syncfusion:NodeViewModel.Ports>
        	</syncfusion:NodeViewModel>
       	</syncfusion:NodeCollection>
	</syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}

![](Port_images/Port_img6.jpeg)

##ConnectorPort

###Add Port to Connector
To add a collection port, you need to define the port object and add it to `Ports` property of Connector. The `Length` property of Port accepts an object of fractions and used to determine the position of Ports. The following code illustrates how to add ports to the Connector.

The following code illustrates how to add ports to Connector.

[XAML]

{% highlight xaml %}

<!--Style for Connector-->
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle}">
	<Setter Property="TargetDecoratorStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black" />
                <Setter Property="Stretch" Value="Fill" />
            </Style>
		</Setter.Value>
	</Setter>
</Style>

<!--Style for ConnectorPort-->
<Style TargetType="syncfusion:ConnectorPort" BasedOn="{StaticResource ConnectorPortBindingStyle}">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Black"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
			</Style>
      	</Setter.Value>
   	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
        	<RectangleGeometry Rect="0,0,10,10"/>
      	</Setter.Value>
   	</Setter>
</Style>

{% endhighlight %}

[C#]

{% highlight C# %}

//Create port collection
public class PortCollection : ObservableCollection<IPort>
{

}

{% endhighlight %}

[XAML]

{% highlight xaml %}

<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible" DefaultConnectorType="Line">
	<syncfusion:SfDiagram.Connectors>
    	<syncfusion:ConnectorCollection>
        	<syncfusion:ConnectorViewModel x:Name="connector" SourcePoint="100,100" TargetPoint="300,300">
				<syncfusion:ConnectorViewModel.Ports>
                	<local:PortCollection>
                    	<syncfusion:ConnectorPortViewModel x:Name="port" UnitWidth="7"
                                                           UnitHeight="7" 
                                                           Length="0.5">
						</syncfusion:ConnectorPortViewModel>
					</local:PortCollection>
                </syncfusion:ConnectorViewModel.Ports>
			</syncfusion:ConnectorViewModel>
       	</syncfusion:ConnectorCollection>
	</syncfusion:SfDiagram.Connectors>
</syncfusion:SfDiagram>

{% endhighlight %}

![](Port_images/Port_img7.jpeg)

##Connect with ports

Connector’s `SourcePort` and `TargetPort` properties allow to create connections between some specific points of source/target Nodes. For More information about creating connections with port, refer to [Connections with Ports](/wpf/sfdiagram/Connector#Connections-with-Ports "Connections with Ports").

##Appearance

You can change the shape of port by using its shape property. The appearance of ports can be customized with a set of style specific properties.

The following code illustrates how to change the appearance of port.

[XAML]

{% highlight xaml %}

<!--Style for NodePort-->
<Style TargetType="syncfusion:NodePort" BasedOn="{StaticResource NodePortBindingStyle}">
	<Setter Property="ShapeStyle">
    	<Setter.Value>
        	<Style TargetType="Path">
            	<Setter Property="Fill" Value="Yellow"></Setter>
                <Setter Property="Stretch" Value="Fill"></Setter>
            </Style>
        </Setter.Value>
	</Setter>
    <Setter Property="Shape">
    	<Setter.Value>
			<EllipseGeometry RadiusX="10" RadiusY="10"/>
        </Setter.Value>
	</Setter>
</Style>

{% endhighlight %}

[XAML]

{% highlight xaml %}

<syncfusion:SfDiagram x:Name="diagram" PortVisibility="Visible">
	<syncfusion:SfDiagram.Nodes>
		<syncfusion:NodeCollection>
              	<syncfusion:NodeViewModel x:Name="node" OffsetX="100" OffsetY="100" 	
				  		                  UnitHeight="100" UnitWidth="100">                                    
					<syncfusion:NodeViewModel.Ports>
						<local:PortCollection>
							<syncfusion:NodePortViewModel x:Name="port" UnitWidth="7"
                                                      	  UnitHeight="7"
                                                          NodeOffsetX="1"
                                                          NodeOffsetY="0.5">
							</syncfusion:NodePortViewModel>
						</local:PortCollection>
                	</syncfusion:NodeViewModel.Ports>
              	</syncfusion:NodeViewModel>
       	</syncfusion:NodeCollection>
	</syncfusion:SfDiagram.Nodes>
</syncfusion:SfDiagram>

{% endhighlight %}

![](Port_images/Port_img8.jpeg)

##Constraints

The `Constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/wpf/sfdiagram/Constraints#PortConstraints "Port Constraints").