---
layout: post
title: Define and add the frequently used Nodes/Connectors to the Stencil.
description: How to add Symbol to the Stencil and drag and drop them over the drawing area?
platform: wpf
control: SfDiagram
documentation: ug
---

# Stencil

Stencil has a collection of Symbols. Stencil is used to clone the desired symbol by dragging it from the Stencil and dropping it into the SfDiagram. Each symbol can be grouped together by using the SymbolGroupProvider and filters by using the SymbolFilterProvider through delegates.

{% highlight xaml %}

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

## Symbol

Symbol is used to implement the ISymbol interface. The ISymbol interface consists of two properties to visualize symbols in Stencil:

#### Symbol and SymbolTemplate

{% highlight C# %}

public class SymbolItem : ISymbol
{
	//Symbol-Any Object
    public object Symbol { get; set; }

    //Custom property for grouping.
    public object GroupName { get; set; }

	//Data template to visualize the object.
    public DataTemplate SymbolTemplate { get; set; }

    //For cloning the symbol from the given object and data template.
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

### Adding the Symbol

The following example illustrates how to add the Symbol into a Collection:

#### Define the SymbolTemplate.

{% highlight xaml %}

<DataTemplate x:Key="Star">
	<Path Stretch="Fill" Data="M 9,2 11,7 17,7 12,10 14,15 9,12 4,15 6,10 1,7 7,7 Z"
          Stroke="Black" StrokeThickness="1" />
</DataTemplate>

{% endhighlight %}

#### Create the ISymbol with Symbol and SymbolTemplate properties.

{% highlight xaml %}

<local:FloorPlanSymbolItem GroupName="Flow Chart" Symbol="Star"
                           SymbolTemplate="{StaticResource Star}"/>

{% endhighlight %}

#### Add the ISymbol into the Collection.

{% highlight C# %}

// SymbolSource to Stencil
public class SymbolCollection : ObservableCollection<ISymbol>
{

}

{% endhighlight %}

{% highlight xaml %}

<local:SymbolCollection x:Key="symbolcollection">
	<!--Adding Symbol into a collection-->
	<local:FloorPlanSymbolItem GroupName="Flow Chart" Symbol="Star"
                               SymbolTemplate="{StaticResource Star}"/>
</local:SymbolCollection>

{% endhighlight %}

![](Stencil_images/Stencil_img2.jpeg)

This Collection will be the SymbolSource to the Stencil. Based on the SymbolSource, the Stencil will populate the Symbols.

### Add Node, Connector and Group to Stencil

#### Create a Node ,Connector and Group and to SymbolCollection.

{% highlight xaml %}

<!--Collection of Symbols-->
<local:SymbolCollection x:Key="symbolcollection">
	<!--Creates the NodeViewModel-->
	<syncfusion:NodeViewModel UnitHeight="100" UnitWidth="100" 
			                  Shape="{StaticResource Rectangle}" Key="Nodes"/>
            
	<!--Creates the ConnectorViewModel-->
   	<syncfusion:ConnectorViewModel SourcePoint="100,100" TargetPoint="200,200"
                                   Key="Connectors"/>
            
	<!--Creates the GroupViewModel-->
   	<syncfusion:GroupViewModel Key="Groups">
		<!--Creates the Groupable Nodes-->
        <syncfusion:GroupViewModel.Nodes>
			<syncfusion:NodeCollection>
            	<syncfusion:NodeViewModel UnitHeight="100" UnitWidth="100" 
                            			  Shape="{StaticResource Ellipse}">
				</syncfusion:NodeViewModel>
			</syncfusion:NodeCollection>
		</syncfusion:GroupViewModel.Nodes>
                
		<!--Creates the Groupable Connectors-->
        <syncfusion:GroupViewModel.Connectors>
        	<syncfusion:ConnectorCollection>
            	<syncfusion:ConnectorViewModel SourcePoint="0,0"  
                                               TargetPoint="100,100"/>
			</syncfusion:ConnectorCollection>
		</syncfusion:GroupViewModel.Connectors>
	</syncfusion:GroupViewModel>
</local:SymbolCollection>

{% endhighlight %}

#### Add SymbolCollection to SymbolSource of Stencil.

{% highlight xaml %}

<stencil:Stencil x:Name="stencil" ExpandMode="All">
	<stencil:Stencil.SymbolSource>
    	<!--Collection of Symbols-->
        <local:SymbolCollection>
        	<!--From step2, Create a Node, Connector and Group to SymbolCollection.-->
      	</local:SymbolCollection>
	</stencil:Stencil.SymbolSource>
</stencil:Stencil>

{% endhighlight %}

## SymbolGroups

The SymbolGroupProvider groups the symbols into SymbolGroup based on the MappingName property.

| Name | Description |
|---|---|
| MappingName | Used to group the symbols by mapping this property to the custom property of Symbols. |

The following code example illustrates how to create a SymbolGroup.

{% highlight xaml %}

<stencil:Stencil x:Name="stencil" ExpandMode="All" 
		         SymbolSource="{StaticResource symbolcollection}">
	<!--SymbolGroup-->
    <stencil:Stencil.SymbolGroups>
    	<stencil:SymbolGroups>
        	<!--To Map Symbols based on GroupName-->
			<stencil:SymbolGroupProvider MappingName="Key"/>
		</stencil:SymbolGroups>
	</stencil:Stencil.SymbolGroups>
</stencil:Stencil>

{% endhighlight %}

![](Stencil_images/Stencil_img3.jpeg)

### Expand or Collapse SymbolGroup

Expand and Collapse can be performed on SymbolGroup (updating the Visibility of the Symbols) based on the ExpandMode property. It includes the following options. The default option is One.

| Expand Mode | Description | Images |
|---|---|---|
| One | Always one SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img4.jpeg) |
| OneOrMore | At least one SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img5.jpeg) | ![](Stencil_images/Stencil_img6.jpeg) |
| ZeroOrOne | Not more than a single SymbolGroup is in expanded state. All ‘SymbolGroup’ can be in collapsed state. | ![](Stencil_images/Stencil_img7.jpeg) | ![](Stencil_images/Stencil_img8.jpeg) |
| ZeroOrMore | Any number of SymbolGroup can be in the expanded state. All ‘SymbolGroup’ can be in collapsed state. | ![](Stencil_images/Stencil_img9.jpeg) | ![](Stencil_images/Stencil_img10.jpeg) |
| All | All the SymbolGroup is in expanded state. | ![](Stencil_images/Stencil_img11.jpeg) |

## SymbolFilters

`SymbolFilterProvider` is used to filter or hide the symbols by using delegates. SymbolFilters are the collection of SymbolFilterProvider.

The following code example shows how to create and add the SymbolFilter. Based on the return Boolean value of the SymbolFilter delegate, the corresponding item is removed from Stencil. When a SymbolGroup does not have any Symbols, the corresponding SymbolGroup is also removed.

{% highlight C# %}

stencil.SymbolFilters = new SymbolFilters();

//Creates the SymbolFilterProvider
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

//Add the SymbolFilterprovider to SymbolFilters collection
stencil.SymbolFilters.Add(allFilter);
stencil.SymbolFilters.Add(kitchenFilter);

// sender: used to get the selected SymbolFilters
private bool SymbolFilter(SymbolFilterProvider sender, object symbol)
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

![](Stencil_images/Stencil_img12.jpeg)

### SelectedFilter

There can be multiple SymbolFilters, but only one filter can be selected at a time. These SymbolFilters are visually represented in a combo box. When the selected item is changed in the combo box, SelectedFilter is updated accordingly.

![](Stencil_images/Stencil_img13.jpeg)

## Preview for Drag and Drop

SfDiagram provides preview support for Stencil. When you drag an item from Stencil to Diagram, a preview of the dragged item will be displayed. You can enable or disable the preview support. You can also customize the preview.

#### Use Case Scenario

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

#### Preview of the dragging Symbol

![](Stencil_images/Stencil_img14.jpeg)

#### Dragged Symbol

![](Stencil_images/Stencil_img15.jpeg)

#### Customization of Preview for Drag and Drop

You can customize the preview content by overriding the PrepareDragDropPreview method of the Stencil feature. The following code example illustrates how to customize preview content.

{% highlight C# %}

public class CustomStencil : Stencil
{
	//Virtual method to customize the preview of dragging the symbol from Stencil.
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

![](Stencil_images/Stencil_img16.jpeg)