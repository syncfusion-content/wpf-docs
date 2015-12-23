---
layout: post
title: Define and add the frequently used Nodes/Connectors to the Stencil.
description: How to add Symbol to the Stencil and drag and drop them over the drawing area?
platform: wpf
control: SfDiagram
documentation: ug
---

#Stencil

Stencil has a collection of Symbols. Stencil is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram. Each symbol can be grouped together by using the SymbolGroupProvider and filteres by using the SymbolFilterProvider through delegates.

{% highlight xml %}

xmlns:stencil="using:Syncfusion.UI.Xaml.Diagram.Stencil"

{% endhighlight %}

![](Stencil_images/Stencil_img1.jpeg)

Key Terms Table

| Key Terms | Description |
|---|---|
| Symbol | To visualize the items in Stencil. |

Properties Table

| Properties | Description |
|---|---|
| SymbolGroups | Collection of SymbolGroupProvider To Group the Symbols based on the MappingName Property. |
| SymbolFilters | Collection of SymbolFilterProvider To filter/Hide the Symbols based on MappingName Property. |
| SymbolSource | ItemSource for Stencil to populate the SymbolGroups with symbol. | 

##Symbol

Symbol is used to implement the ISymbol interface. The ISymbol interface consists of two properties to visualize symbols in Stencil:

Symbol and SymbolTemplate

{% highlight C# %}

public class SymbolItem : ISymbol
{
	public object Symbol { get; set; }

	public object Key { get; set; }

	public DataTemplate SymbolTemplate { get; set; }

	public ISymbol Clone()
	{
		return new SymbolItem()
		{
			Symbol = this.Symbol,
			SymbolTemplate = this.SymbolTemplate,
		};
	}
	public object GroupName { get; set; }
}

{% endhighlight %}

###Adding the Symbol

The following example illustrates how to add the Symbol into a Collection:

####Create the ISymbol with Symbol and SymbolTemplate properties.

{% highlight xml %}

<local:SymbolItem GroupName="Flow Chart" Symbol="FlowChart_Star" 
                  SymbolTemplate="{StaticResource FlowChart_Star}"/>

{% endhighlight %}

####Define the SymbolTemplate.

{% highlight xml %}

<DataTemplate x:Key="FlowChart_Star">
  <Path Style="{StaticResource SymbolStyle}" Data="M 9,2 11,7 17,7 12,10 14,15 9,12   
        4,15 6,10 1,7 7,7 Z" Stretch="Fill"/>
</DataTemplate>

{% endhighlight %}

####Add the ISymbol into the Collection.

{% highlight C# %}

public class SymbolCollection : ObservableCollection<ISymbol>
{

}

{% endhighlight %}

{% highlight xml %}

<local:SymbolCollection x:Key="symbolcollection">
  <local:SymbolItem GroupName="Flow Chart" Symbol="FlowChart_Star" 
                    SymbolTemplate="{StaticResource FlowChart_Star}"/>
</local:SymbolCollection>

{% endhighlight %}

![](Stencil_images/Stencil_img2.jpeg)

This Collection will be the SymbolSource to the Stencil. Based on the SymbolSource, the Stencil will populate the Symbols.

###Add Node, Connector and Group to Stencil

####Create a custom class (SymbolItem in this example) that derives ISymbol and implements necessary things.

{% highlight C# %}

public class SymbolItem : ISymbol
{
	public object Symbol { get; set; }

	public object GroupName { get; set; }

	public DataTemplate SymbolTemplate { get; set; }
	public ISymbol Clone()
	{
		return new SymbolItem()
		{
			Symbol = this.Symbol,
			SymbolTemplate = this.SymbolTemplate
		};
	}

	public object Key { get; set; }
}

{% endhighlight %}

####Create a Node ,Connector and Group and to SymbolCollection.

{% highlight xml %}

<!--Collection of Symbols-->
<sync:SymbolCollection>
<!--ISymbol-->
	<local:SymbolItem GroupName="Nodes">
		<local:SymbolItem.Symbol>
		<!--NodeViewModel-->
		<sync:NodeViewModel UnitHeight="50" UnitWidth="50" OffsetX="200" OffsetY="200" ShapeStyle="{StaticResource nodestyle}">
			<sync:NodeViewModel.Shape>
				<RectangleGeometry Rect="10,10,10,10"></RectangleGeometry>
			</sync:NodeViewModel.Shape>
		</sync:NodeViewModel>
		</local:SymbolItem.Symbol>
	</local:SymbolItem>
	<local:SymbolItem GroupName="Connectors">
		<local:SymbolItem.Symbol>
		<!--ConnectorViewModel-->
		<sync:ConnectorViewModel ConnectorGeometryStyle="{StaticResource connectorstyle}" SourcePoint="100,100" TargetPoint="200,200"/>
		</local:SymbolItem.Symbol>
	</local:SymbolItem>
	<local:SymbolItem GroupName="Groups">
	<local:SymbolItem.Symbol>
		<!--GroupViewModel-->
		<sync:GroupViewModel>
		<!--GroupViewModel.Nodes-->
		<sync:GroupViewModel.Nodes>
			<sync:NodeCollection>
				<sync:NodeViewModel UnitHeight="50" UnitWidth="50" OffsetX="300" OffsetY="300" ShapeStyle="{StaticResource nodestyle}">
				<sync:NodeViewModel.Shape>
					<EllipseGeometry RadiusX="10" RadiusY="10"/>
				</sync:NodeViewModel.Shape>
				</sync:NodeViewModel>
			</sync:NodeCollection>
		</sync:GroupViewModel.Nodes>
		<!--GroupViewModel.Connectors-->
		<sync:GroupViewModel.Connectors>
			<sync:ConnectorCollection>
				<sync:ConnectorViewModel ConnectorGeometryStyle="{StaticResource connectorstyle}" SourcePoint="100,100" TargetPoint="200,200"/>
			</sync:ConnectorCollection>
		</sync:GroupViewModel.Connectors>
		</sync:GroupViewModel>
	</local:SymbolItem.Symbol>
	</local:SymbolItem>
</sync:SymbolCollection>

{% endhighlight %}

####Add SymbolCollection to SymbolSource of Stencil.

{% highlight xml %}

<stencil:Stencil x:Name="stencil" ExpandMode="All">
	<stencil:Stencil.SymbolSource>
		<!--Collection of Symbols-->
		<sync:SymbolCollection>
			<!—from Step2-->
		</sync:SymbolCollection>
	</stencil:Stencil.SymbolSource>
	<!--SymbolGroup-->
	<stencil:Stencil.SymbolGroups>
		<stencil:SymbolGroups>
			<!--To Map Symbols based on GroupName-->
			<stencil:SymbolGroupProvider MappingName="GroupName"/>
		</stencil:SymbolGroups>
	</stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}

![](Stencil_images/Stencil_img3.jpeg)

##SymbolGroups

The SymbolGroupProvider groups the symbols into SymbolGroup based on the MappingName property.

| Name | Description |
|---|---|
| MappingName | Used to group the symbols by mapping this property to the custom property of Symbols. |

The following code example illustrates how to create a SymbolGroup.

{% highlight xml %}

<stencil:Stencil x:Name="stencil" SymbolSource="{StaticResource symbolcollection}">
  <stencil:Stencil.SymbolGroups>
    <stencil:SymbolGroups>
      <stencil:SymbolGroupProvider MappingName="GroupName"/>
    </stencil:SymbolGroups>
  </stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}

###Expand or Collapse SymbolGroup

Expand and Collapse can be performed on SymbolGroup (updating the Visibility of the Symbols) based on the ExpandMode property. It includes the following options. The default option is One.

| Expand Mode | Description |
|---|---|
| One | Always one SymbolGroup is in expanded state. |
| OneOrMore | At least one SymbolGroup is in expanded state. |
| ZeroOrOne | Not more than a single SymbolGroup is in expanded state. All ‘SymbolGroup’ can be in collapsed state. |
| ZeroOrMore | Any number of SymbolGroup can be in the expanded state. All ‘SymbolGroup’ can be in collapsed state. |
| All | All the SymbolGroup is in expanded state. |

##SymbolFilters

`SymboFilterProvider` is used to filter or hide the symbols by using delegates. SymbolFilters are the collection of SymbolFilterProvider.

The following code example shows how to create and add the SymbolFilter. Based on the return Boolean value of the SymbolFilter delegate, the corresponding item is reoved from Stencil. When a SymbolGroup does not have any Symbols, the corresponding SymbolGroup is also removed.

{% highlight C# %}

private void CreateFilters()
{
	stencil.SymbolFilters = new SymbolFilters();
	SymbolFilterProvider allFilter = new SymbolFilterProvider
	{
		Content = "All",
		Filter = SymbolFilter
	};
	SymbolFilterProvider kitchenFilter = new SymbolFilterProvider
	{
		Content = "Kitchen",
		Filter = SymbolFilter
	};
	stencil.SymbolFilters.Add(addFilter);
	stencil.SymbolFilters.Add(kitchenFilter);
}


// sender: used to get the selected SymbolFilters
private bool SymbolFilter(SymbolFilterProvider sender, ISymbol symbol)
{
	if (sender.Content.ToString() == "All")
	{
		return true;
	}
	if ((symbol as SymbolItem).GroupName == sender.Content.ToString())
	{
		return true;
	}
	return false;
}

{% endhighlight %}

###SelectedFilter

There can be multiple SymbolFilters, but only one filter can be selected at a time. These SymbolFilters are visually represented in a combo box. When the selected item is changed in the combo box, SelectedFilter is updated accordingly.

![](Stencil_images/Stencil_img5.jpeg)

## Preview for Drag and Drop

SfDiagram provides preview support for Stencil. When you drag an item from Stencil to Diagram, a preview of the dragged item will be displayed. You can enable or disable the preview support. You can also customize the preview.

####Use Case Scenario

This feature displays a preview of the item you drag from Stencil, enabling you to identify the item you are dragging from the Stencil to the SfDiagram control. It also it gives a preview of the size and appearance of the item before it is dropped.

####Enabling preview

To enable preview for the dragged item from Stencil, set the Constraints property of Stencil to ShowPreview. To disable preview, remove ShowPreview from Constraints property. By default, preview for drag and drop is enabled.

The following code example illustrates how to enable preview support.

{% highlight C# %}

//Enables the drag and drop preview.
stencil.Constraints = stencil.Constraints | StencilConstraints.ShowPreview;

//Disables the drag and drop preview.
stencil.Constraints = stencil.Constraints & ~StencilConstraints.ShowPreview;

{% endhighlight %}

Here, Stencil is an instance of Stencil.

![](Stencil_images/Stencil_img4.jpeg)

####Customization of Preview for Drag and Drop

You can customize the preview content by overriding the PrepareDragDropPreview method of the Stencil feature. The following code example illustrates how to customize preview content.

{% highlight C# %}

public class CustomStencil : Stencil
{
	protected override void PrepareDragDropPreview()
	{
		this.SymbolPreview = new ContentPresenter()
		{
			Content = new Rectangle()
			{
				Width = 50,
				Height = 50,
				Fill = new SolidColorBrush(Colors.SteelBlue)
			}
		};
	}
}

{% endhighlight %}