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



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.State="Dock"   syncfusion:DockingManager.Header="Dock Window"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetHeader(grid1,"Dock Window");DockingManager.SetState(grid1, DockState.Dock);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockingWindow.jpg](Basic-Features_images/Basic-Features_img1.jpeg) | markdownify }
{:.image }


Float State:

Float State displays the child in FloatWindow as shown below:



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;   &lt;Grid Name="grid1" syncfusion:DockingManager.State="Float"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetState(grid1, DockState.Float);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/FloatState.jpg](Basic-Features_images/Basic-Features_img2.jpeg) | markdownify }
{:.image }


Auto Hidden State:

Auto hidden state hides the children in one of the side panels available with the DockingManager.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;   &lt;Grid Name="grid1" syncfusion:DockingManager.State="AutoHidden"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetState(grid1, DockState.AutoHidden);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/FloatState.jpg](Basic-Features_images/Basic-Features_img3.jpeg) | markdownify }
{:.image }


### Document State Child

The Document state is the child’s children, which can be displayed as a Tabbed document or (Multiple Document Interface) MDI.

Document State Child can be of two types.

* TDI (Tabbed Document Interface)
* MDI (Multiple Document Interface)

You can create MDI Documents by specifying ContainerMode to MDI as a child state,and as Document , as shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="MDI"&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.State="Document" syncfusion:DockingManager.Header="MDI"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#] DockingManager manager=new DockingManager();manager.UseDocumentContainer = true;manager.ContainerMode = DocumentContainerMode.MDI;Grid child=new Grid();DockingManager.SetHeader(child, "MDI");DockingManager.SetState(child,DockState.Document);manager.Children.Add(child);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/MDI.jpg](Basic-Features_images/Basic-Features_img4.jpeg) | markdownify }
{:.image }


Similarly you can create a TDI Document by specifying ContainerMode as TDI and child state as document.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager UseDocumentContainer="True" ContainerMode="TDI"&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.State="Document" syncfusion:DockingManager.Header="TDI"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#] DockingManager manager=new DockingManager();manager.UseDocumentContainer = true;manager.ContainerMode = DocumentContainerMode.TDI;Grid child=new Grid();DockingManager.SetHeader(child, "TDI");DockingManager.SetState(child,DockState.Document);manager.Children.Add(child);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/TDI.jpg](Basic-Features_images/Basic-Features_img5.jpeg) | markdownify }
{:.image }


Refer Also:

How to Create Docking Manager?

## Layout of the child

We can achieve the layout that we want using TargetName attached property.  Target names are generally used to specify where the child needs to be docked or floated. The following code shows the usage of TargetNameInDockMode.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.Header="grid1"/&gt;&lt;Grid Name="grid2" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.TargetNameInDockedMode="grid1" syncfusion:DockingManager.SideInDockedMode="Bottom"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetTargetNameInDockedMode(grid2, "grid1");</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/TargetNameInDockMode.jpg](Basic-Features_images/Basic-Features_img6.jpeg) | markdownify }
{:.image }


Refer Also:

How to Create Docking Manager?

## DockSide for Docked State child’s

SideInDockMode and SideInFloatMode are used to decide the dock side of child with respect to their target names in dock mode and float mode.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Left" syncfusion:DockingManager.Header="Dock Left"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetHeader(grid1, "Dock Left");DockingManager.SetSideInDockedMode(grid1, DockSide.Left);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockLeft.jpg](Basic-Features_images/Basic-Features_img7.jpeg) | markdownify }
{:.image }


The following code represents child in a Dock right position.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;            &lt;Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.Header="Dock Right"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetHeader(grid1, "Dock Right");DockingManager.SetSideInDockedMode(grid1, DockSide.Right);</td></tr>
</table>
{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockRight.jpg](Basic-Features_images/Basic-Features_img8.jpeg) | markdownify }
{:.image }




<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Top"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetHeader(grid1, "Dock Top");DockingManager.SetSideInDockedMode(grid1, DockSide.Top);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockTop.jpg](Basic-Features_images/Basic-Features_img9.jpeg) | markdownify }
{:.image }


The code below shows child position in a Dock bottom.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.SideInDockedMode="Bottom" syncfusion:DockingManager.Header="Dock Bottom"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetHeader(grid1, "Dock Bottom");DockingManager.SetSideInDockedMode(grid1, DockSide.Bottom);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockBottom.jpg](Basic-Features_images/Basic-Features_img10.jpeg) | markdownify }
{:.image }




<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.Header="grid1"/&gt;&lt;Grid Name="grid2" syncfusion:DockingManager.TargetNameInDockedMode="grid1" syncfusion:DockingManager.Header="grid2" syncfusion:DockingManager.SideInDockedMode="Tabbed" /&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetTargetNameInDockedMode(grid2, "grid1");DockingManager.SetSideInDockedMode(grid2, DockSide.Tabbed);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockTabbed.jpg](Basic-Features_images/Basic-Features_img11.jpeg) | markdownify }
{:.image }


Refer Also:

How to Create Docking Manager?

