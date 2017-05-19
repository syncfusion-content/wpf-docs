---
layout: post
title: Data Binding for Syncfusion Essential Diagram for WPF.
description: Data Binding for properties of ViewModel are bind to View. 
platform: wpf
control: SfDiagram
documentation: ug

---

# Data Binding

Any objects can be added as Node/Connector/Annotation/Group for the diagram. But to have better access to diagram, some interfaces have to be implemented by the such objects. Such interfaces are already implemented as a set of ViewModel classes. There classes will just implement properties, they don’t have any logic. 
By default, View will be generated for each ViewModel and Properties of ViewModel (NodeViewModel) are bind to View (Node). We have changed this Default Behavior (ViewModel to View binding will not work).


The following code illustrates how to achieve View to View Model binding by using “BindingStyle.xaml”

{% highlight xaml %}
<!--For View to ViewModel binding-->
<ResourceDictionary.MergedDictionaries>
     <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BindingStyle.xaml" />
</ResourceDictionary.MergedDictionaries>


<!--To apply Style for NodeViewModel,ConnectorViewModel,NodePortViewModel,ConnectorPortViewModel-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
   <!--Common code for NodeViewModel-->
</Style>
<Style TargetType="syncfusion:Connector" BasedOn="{StaticResource ConnectorBindingStyle}">
   <!--Common code for ConnectorViewModel-->
</Style>
<Style TargetType="syncfusion:NodePort" BasedOn="{StaticResource NodePortBindingStyle}">
   <!--Common code for NodePortViewModel-->
</Style>
<Style TargetType="syncfusion:ConnectorPort" BasedOn="{StaticResource ConnectorPortBindingStyle}">
   <!--Common code for ConnectorPortViewModel-->
</Style>
<Style TargetType="syncfusion:AnnotationEditor" BasedOn="{StaticResource AnnotationEditorBindingStyle}">
   <!--Common code for AnnotationEditorViewModel-->        
 </Style>

{% endhighlight %}