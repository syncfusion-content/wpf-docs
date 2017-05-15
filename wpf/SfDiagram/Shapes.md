---
layout: post
title: Basic Shapes with Syncfusion Essential Diagram for WPF.
description: How do add different shapes to diagram 
platform: wpf
control: SfDiagram
documentation: ug
---

##Shapes

We have provided some basic built-in shapes as ResourceDictionary.

The following code example illustrates how to merge shapes into diagram.

{% highlight xaml %}
<ResourceDictionary.MergedDictionaries>
       <!--Initialize Shapes-->
       <ResourceDictionary Source="/Syncfusion.SfDiagram.Wpf;component/Resources/BasicShapes.xaml" />
</ResourceDictionary.MergedDictionaries>  
{% endhighlight %}


###Basic Shapes

The following code example illustrates how to assign Shape property of the Node.

{% highlight xaml %}
<!--Style for Node-->
<Style TargetType="syncfusion:Node" BasedOn="{StaticResource NodeBindingStyle}">
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

 ![](Shapes_images\Shapes_image1.PNG)
 
 
 The list of basic shapes are as follows
 
 ![](Shapes_images\Shapes_image2.PNG)
 

The list of flow shapes are as follows

![](Shapes_images\Shapes_image4.PNG)
 
The list of arrow shapes are as follows

![](Shapes_images\Shapes_image5.PNG)





 
 











