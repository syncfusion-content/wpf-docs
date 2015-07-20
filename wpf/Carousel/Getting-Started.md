---
layout: post
title: Getting-Started
description: getting started
platform: wpf
control: Carousel
documentation: ug
---

# Getting Started

## Structure of the Carousel Control

{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


## Add Carousel to an Application

The Carousel control can be added to an application by using Visual Studio and Blend.

### Add through C#

Follow the steps to add the Carousel control by using VisualStudio.

1. Open Visual Studio. On the File menu, select New -> Project. This opens the New Project Dialog box.

{ ![C:/Documents and Settings/labuser/My Documents/WPF Tools correct Image.png](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


2. In the Project Dialog window, select WPF Application and in the name field type the name of the project, and then click OK.
3. Add the reference with the sample project, Syncfusion.Shared.Wpf.dll
4. Click and open the C# file and add the Carousel control to your application.

The following code shows how the Carousel control can be added to an application:

[C#]



Carousel carousel = new Carousel();
carousel.Items.Add(new CarouselItem() { Content = "1" });
carousel.Items.Add(new CarouselItem() { Content = "2" });
carousel.Items.Add(new CarouselItem() { Content = "3" });
carousel.Items.Add(new CarouselItem() { Content = "4" });
carousel.Items.Add(new CarouselItem() { Content = "5" });
this.LayoutRoot.Children.Add(carousel);



### Add through XAML

Follow the steps to add Carousel by using Visual Studio in XAML.

1. Create a new application in Visual Studio.
2. In the Visual Studio Toolbox, click Syncfusion Silverlight Toolbox tab and select Carousel.
3. Drag and Drop the Carousel to design view, in order to add the Carousel control to your application.
4. In the properties window, customize the properties of the Carousel.



The following code shows how Carousel can be added to an application by using Visual Studio in XAML:

[XAML]



&lt;syncfusion:Carousel x:Name="carousel" Height="400" Width="450"&gt;
    &lt;syncfusion:Carousel.Path&gt;
        &lt;Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/&gt;
    &lt;/syncfusion:Carousel.Path&gt;
    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;

            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Chrysanthemum.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Desert.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Hydrangeas.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Jellyfish.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Koala.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Lighthouse.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Penguins.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

    &lt;syncfusion:CarouselItem&gt;
        &lt;syncfusion:CarouselItem.Content&gt;
            &lt;Viewbox Height="100" Width="100"&gt;
                &lt;Image Source="/CarouselDemo;component/Images/Tulips.jpg"/&gt;
            &lt;/Viewbox&gt;
        &lt;/syncfusion:CarouselItem.Content&gt;
    &lt;/syncfusion:CarouselItem&gt;

&lt;/syncfusion:Carousel&gt;





{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


### Add through Blend

Follow the steps to add Carousel in an application by using Blend.

1. Open Blend, and on the File Menu, click New Project. This opens the New Project dialog box as shown below.



{ ![](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }




2. In the Project type’s panel, select WPF application and then click OK.



{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }


3. Add the following Reference with the sample project.

Syncfusion.Shared.Wpf.dll

4. On the Window menu, select Assets. This opens the Assets Library dialog box.
5. In the Search box, type Carousel. This displays the search results.
6. Drag the Carousel control to DesignView.







{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }


