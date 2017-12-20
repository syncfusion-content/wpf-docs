---
layout: post
title: Hide properties in PropertyGrid | PropertyGrid  | wpf | Syncfusion
description: hide properties in propertygrid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Hide properties in PropertyGrid

In PropertyGrid, `HidePropertiesCollection` property is used to hide the mentioned properties which are already present in SelectedObject. Properties can also be hide at the run time using this property.

{% tabs %}

{% highlight xaml %}

<syncfusion:PropertyGrid x:Name="propertyGrid" SelectedObject="{Binding ElementName=Btn}" Margin="50"  Width="350" BorderBrush="Gray" BorderThickness="3" HorizontalAlignment="Center"  VerticalAlignment="Stretch" LineColor="Red" CategoryForeground="Black">

</syncfusion:PropertyGrid>

{% endhighlight  %}

{% highlight c# %}

this.propertyGrid.HidePropertiesCollection.Add("ActualWidth");

this.propertyGrid.HidePropertiesCollection.Add("ActualHeight");

{% endhighlight  %}

{% endtabs %}

N>`HidePropertiesCollection` cannot hide the properties which are added through `DynamicDescriptor`.