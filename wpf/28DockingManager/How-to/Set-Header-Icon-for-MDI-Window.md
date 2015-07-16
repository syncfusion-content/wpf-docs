---
layout: post
title: Set-Header-Icon-for-MDI-Window
description: set header icon for mdi window
platform: wpf
control: DockingManager
documentation: ug
---

### Set Header Icon for MDI Window

The Icon property is used to specify the icon for Document children. Consider the following code:



[XAML]

&lt;Window.Resources&gt;

  &lt;DrawingImage x:Key="closeBlue"&gt;

     &lt;DrawingImage.Drawing&gt;

       &lt;DrawingGroup&gt;

          &lt;DrawingGroup.Children&gt;

             &lt;GeometryDrawing Brush="#009A9A25" Geometry="F1 M 2.19338,1.73276L 18.1934,1.73276L 18.1934,17.7328L 2.19338,17.7328L 2.19338,1.73276 Z "/&gt;

             &lt;GeometryDrawing Brush="#dd656564" Geometry="F1 M 16.516,5.58942L 12.4854,5.58942L 10.1947,7.79742L 7.89471,5.58942L 3.87071,5.58942L 8.13871,9.76942L 3.87071,13.8761L 8.03871,13.8761L 10.1947,11.7734L 12.3427,13.8761L 16.5134,13.8761L 12.2427,9.76942L 16.516,5.58942 Z "/&gt;

          &lt;/DrawingGroup.Children&gt;

       &lt;/DrawingGroup&gt;

     &lt;/DrawingImage.Drawing&gt;

  &lt;/DrawingImage&gt;

&lt;/Window.Resources&gt;



    &lt;Grid&gt;

        &lt;syncfusion:DockingManager Name="DockingManager" ContainerMode="MDI"                UseDocumentContainer="True"&gt;

            &lt;syncfusion:DockingManager.Icon&gt;

                &lt;ImageBrush ImageSource="{StaticResource closeBlue}"/&gt;

            &lt;/syncfusion:DockingManager.Icon&gt;



        &lt;Grid Name="grid1"  syncfusion:DockingManager.State="Document"/&gt;

        &lt;/syncfusion:DockingManager&gt;

   &lt;/Grid&gt;



In the above code a DrawingImage object is created as a staticresource and assigned to the Icon property of DockingManager. The MDIWindow with the icon on left top corner will be displayed. 



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Icon.png](Set-Header-Icon-for-MDI-Window_images/Set-Header-Icon-for-MDI-Window_img1.png) | markdownify }
{:.image }


