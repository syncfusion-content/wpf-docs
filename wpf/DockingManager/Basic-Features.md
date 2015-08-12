---
layout: post
title: Basic-Features
description: basic features
platform: wpf
control: DockingManager
documentation: ug
---

# Basic Features

## Dealing with States

States of child is nothing but a different appearance of the DockingManager children.  State Property in DockingManager is used to set various states to the child element such as Docking, Floating, Auto Hide, and Hidden.

Dock State:

Dock State is a state which represents the child as Dock Window as shown below:



{% highlight xml %}
<syncfusion:DockingManager>
<Grid Name="grid1" syncfusion:DockingManager.State="Dock"   syncfusion:DockingManager.Header="Dock Window"/>
</syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetHeader(grid1,"Dock Window");DockingManager.SetState(grid1, DockState.Dock);
{% endhighlight %}


![](Basic-Features_images/Basic-Features_img1.jpeg)



#### Float State:

Float State displays the child in FloatWindow as shown below:



{% highlight xml %}
<syncfusion:DockingManager>
   <Grid Name="grid1" syncfusion:DockingManager.State="Float"/>
   </syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetState(grid1, DockState.Float);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img2.jpeg)



#### Auto Hidden State:

Auto hidden state hides the children in one of the side panels available with the DockingManager.



{% highlight xml %}
<syncfusion:DockingManager>
   <Grid Name="grid1" syncfusion:DockingManager.State="AutoHidden"/>
   </syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
[C#]DockingManager.SetState(grid1, DockState.AutoHidden);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img3.jpeg)



### Document State Child

The Document state is the child’s children, which can be displayed as a Tabbed document or (Multiple Document Interface) MDI.

Document State Child can be of two types.

* TDI (Tabbed Document Interface)
* MDI (Multiple Document Interface)

You can create MDI Documents by specifying ContainerMode to MDI as a child state,and as Document , as shown below.



{% highlight xml %}
<syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="MDI">
<Grid Name="grid1" syncfusion:DockingManager.State="Document" syncfusion:DockingManager.Header="MDI"/>
</syncfusion:DockingManager>
{% endhighlight %}
{% highlight c# %}
DockingManager manager=new DockingManager();
manager.UseDocumentContainer = true;
manager.ContainerMode = DocumentContainerMode.MDI;Grid child=new Grid();
DockingManager.SetHeader(child, "MDI");
DockingManager.SetState(child,DockState.Document);
manager.Children.Add(child);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img4.jpeg)



Similarly you can create a TDI Document by specifying ContainerMode as TDI and child state as document.



{% highlight xml %}
<syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="TDI">
<Grid Name="grid1" syncfusion:DockingManager.State="Document" syncfusion:DockingManager.Header="TDI"/>
</syncfusion:DockingManager>
{% endhighlight %}
{% highlight c# %}
 DockingManager manager=new DockingManager();
 manager.UseDocumentContainer = true;manager.ContainerMode = DocumentContainerMode.TDI;Grid child=new Grid();
 DockingManager.SetHeader(child, "TDI");
 DockingManager.SetState(child,DockState.Document);
 manager.Children.Add(child);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img5.jpeg)



Refer Also:

How to Create Docking Manager?

## Layout of the child

We can achieve the layout that we want using TargetName attached property.  Target names are generally used to specify where the child needs to be docked or floated. The following code shows the usage of TargetNameInDockMode.



{% highlight xml %}
<syncfusion:DockingManager>
<Grid Name="grid1" syncfusion:DockingManager.Header="grid1"/>
<Grid Name="grid2" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.TargetNameInDockedMode="grid1" syncfusion:DockingManager.SideInDockedMode="Bottom"/>
</syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetTargetNameInDockedMode(grid2, "grid1");
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img6.jpeg)



Refer Also:

How to Create Docking Manager?

## DockSide for Docked State child’s

SideInDockMode and SideInFloatMode are used to decide the dock side of child with respect to their target names in dock mode and float mode.



{% highlight xml %}
<syncfusion:DockingManager>
<Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Left" syncfusion:DockingManager.Header="Dock Left"/>
</syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetHeader(grid1, "Dock Left");DockingManager.SetSideInDockedMode(grid1, DockSide.Left);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img7.jpeg)



The following code represents child in a Dock right position.



{% highlight xml %}
[XAML]<syncfusion:DockingManager>
            <Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.Header="Dock Right"/> 
			</syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
[C#]DockingManager.SetHeader(grid1, "Dock Right");
DockingManager.SetSideInDockedMode(grid1, DockSide.Right);
{% endhighlight  %}
![](Basic-Features_images/Basic-Features_img8.jpeg)





{% highlight xml %}
<syncfusion:DockingManager><Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Top"/></syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetHeader(grid1, "Dock Top");DockingManager.SetSideInDockedMode(grid1, DockSide.Top);
{% endhighlight %}


![](Basic-Features_images/Basic-Features_img9.jpeg)



The code below shows child position in a Dock bottom.



{% highlight xml %}
<syncfusion:DockingManager><Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Bottom" syncfusion:DockingManager.Header="Dock Bottom"/>
</syncfusion:DockingManager>
{% endhighlight %}
{% highlight c# %}
DockingManager.SetHeader(grid1, "Dock Bottom");DockingManager.SetSideInDockedMode(grid1, DockSide.Bottom);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img10.jpeg)




{% highlight xml %}
<syncfusion:DockingManager>
<Grid Name="grid1" syncfusion:DockingManager.Header="grid1"/>
<Grid Name="grid2" syncfusion:DockingManager.TargetNameInDockedMode="grid1" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.SideInDockedMode="Tabbed" />
</syncfusion:DockingManager>
{% endhighlight  %}
{% highlight c# %}
DockingManager.SetTargetNameInDockedMode(grid2, "grid1");DockingManager.SetSideInDockedMode(grid2, DockSide.Tabbed);
{% endhighlight  %}


![](Basic-Features_images/Basic-Features_img11.jpeg)



Refer Also:

How to Create Docking Manager?

