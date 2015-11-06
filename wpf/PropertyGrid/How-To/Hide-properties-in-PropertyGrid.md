---
layout: post
title: Hide properties in PropertyGrid | PropertyGrid  | wpf | Syncfusion
description: hide properties in propertygrid
platform: wpf
control: PropertyGrid 
documentation: ug
---

# Hide properties in PropertyGrid

You can hide the group of properties using HidePropertiesCollection property. You have to add the property names, which must be collapsed into HidePropertiesCollection.

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
