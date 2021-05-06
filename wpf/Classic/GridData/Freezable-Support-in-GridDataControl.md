---
layout: post
title: Freezable Support in WPF GridData Control | Syncfusion
description: Learn here all about Freezable Support in Syncfusion WPF GridDataControl (Classic) control, its elements and more details.
platform: wpf
control: GridData (Classic)
documentation: ug
---
# Freezable Support in WPF GridDataControl (Classic)

GridDataControl now supports inheritance context using Freezable. Developers can use this feature to bind values to elements not present in the Visual Tree. Usually, the ElementName and DataContext bindings are resolved based on the target dependency object’s position within the element tree (or the name scope to which the target dependency object belongs).  But in case, if the target dependency object is not in the tree such as HeaderText in GridDataVisibleColumn, then having an inheritance context for DependencyObjects external to an element tree is the solution. We can achieve this by using Freezable.

The reason the Freezable trick works is because a Freezable object has its own notion of “inheritance context”.  When the property engine sets the effective value of a dependency property, it looks at that new value to determine whether it is a dependency object that would like to be part of a special inheritance tree.  A Freezable is one such object that always wants to be in the inheritance tree when not frozen.  

{% highlight xaml %}

<TextBox Text="Test" x:Name="txtBlock" />

A Separate TextBlock Text can be binded to GridDataVisibleColumn using the following code.

<syncfusion:GridDataControl AutoPopulateColumns="False" x:Name="dataGrid" ItemsSource="{Binding}">

	<syncfusion:GridDataControl.VisibleColumns  >

		<syncfusion:GridDataVisibleColumn  MappingName="Status"  Width="200"  HeaderText="{Binding Text,ElementName=txtBlock}" />

	</syncfusion:GridDataControl.VisibleColumns>

</syncfusion:GridDataControl>

{% endhighlight  %}