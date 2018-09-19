---
layout: post
title: Getting Started documentation of Carousel control for WPF
description: getting started documentation of Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# Getting started

This section describes how to design a `Carousel` control in a WPF application and overview of its basic functionalities.

## Structure of the Carousel Control

![](Getting-Started_images/Getting-Started_img1.jpeg)

# Creating simple application with Carousel

The Carousel control can be added to an application by using Visual Studio and Blend.

You can create the WPF application with Carousel control as follows:

1. [Creating project](#creating-the-project)
2. [Adding control via designer](#adding-control-via-designer)
3. [Adding control manually in code](#adding-control-manually-in-code)
4. [Adding Carousel Items](#adding-carousel-items)
5. [Adding images into Carousel](#adding-images-into-carousel)

### Creating the project

The steps to create a Carousel control by using Visual Studio in C# are as follows:

1.	Open Visual Studio.

2.	On the File menu, select New -> Project. This opens the New Project Dialog box.

   ![](Getting-Started_images/Getting-Started_img4.jpeg)

## Adding control via designer

Carousel control can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly references will be added automatically:

* Syncfusion.Shared.WPF.dll

    ![](Getting-Started_images/Getting-Started_img6.jpeg)

	![](Getting-Started_images/Getting-Started_img2.jpeg)

## Adding control manually in code

To add control manually in C#, follow the given steps:

**Step 1** - Add the following required assembly **Syncfusion.Shared.WPF.dll** references to the project:

**Step 2** - Include the namespaces **Syncfusion.Windows.Shared**

**Step 3** - Create `Carousel` control instance and add it to the Window.

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel();

this.LayoutRoot.Children.Add(carousel);

{% endhighlight %}

{% highlight VB %}

Dim carousel As New Carousel()

Me.LayoutRoot.Children.Add(carousel)

{% endhighlight %}

{% endtabs %}

## Adding Carousel Items

The below code show how carousel items can be added in carousel via code behind.

{% tabs %}

{% highlight C# %}

carousel.Items.Add(new CarouselItem(){Content="1"});
carousel.Items.Add(new CarouselItem(){Content="2"});
carousel.Items.Add(new CarouselItem(){Content="3"});
carousel.Items.Add(new CarouselItem(){Content="4"});
carousel.Items.Add(new CarouselItem(){Content="5"});

{% endhighlight %}

{% highlight VB %}

carousel.Items.Add(New CarouselItem() With { Key .Content = "1" })
carousel.Items.Add(New CarouselItem() With { Key .Content = "2" })
carousel.Items.Add(New CarouselItem() With { Key .Content = "3" })
carousel.Items.Add(New CarouselItem() With { Key .Content = "4" })
carousel.Items.Add(New CarouselItem() With { Key .Content = "5" })

{% endhighlight %}

{% endtabs %}

## Adding images into Carousel

The below code shows how Carousel can be added to an application using Visual Studio in XAML and code behind

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel" Height="400" Width="450">        

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/1.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/2.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/3.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/4.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/5.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/6.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/7.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/8.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

</syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel() { Margin=40, RadiusX = 220, RadiusY = -100, ScaleFraction=0.60 };

Image image = new Image();
Image image1 = new Image();
Image image2 = new Image();
Image image3 = new Image();
Image image4 = new Image();
Image image5 = new Image();
Image image6 = new Image();
Image image7 = new Image();

BitmapImage bitimg1 = new BitmapImage(new Uri("/Sample;component/Images/1.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg2 = new BitmapImage(new Uri("/Sample;component/Images/2.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg3 = new BitmapImage(new Uri("/Sample;component/Images/3.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg4 = new BitmapImage(new Uri("/Sample;component/Images/4.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg5 = new BitmapImage(new Uri("/Sample;component/Images/5.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg6 = new BitmapImage(new Uri("/Sample;component/Images/6.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg7 = new BitmapImage(new Uri("/Sample;component/Images/7.png", UriKind.RelativeOrAbsolute));
BitmapImage bitimg8 = new BitmapImage(new Uri("/Sample;component/Images/8.png", UriKind.RelativeOrAbsolute));

image.Source = bitimg1 as ImageSource;
image1.Source = bitimg2 as ImageSource;
image2.Source = bitimg3 as ImageSource;
image3.Source = bitimg4 as ImageSource;
image4.Source = bitimg5 as ImageSource;
image5.Source = bitimg6 as ImageSource;
image6.Source = bitimg7 as ImageSource;
image7.Source = bitimg8 as ImageSource;

Viewbox viewbox1 = new Viewbox();
Viewbox viewbox2 = new Viewbox();
Viewbox viewbox3 = new Viewbox();
Viewbox viewbox4 = new Viewbox();
Viewbox viewbox5 = new Viewbox();
Viewbox viewbox6 = new Viewbox();
Viewbox viewbox7 = new Viewbox();
Viewbox viewbox8 = new Viewbox();

viewbox1.Child = image;
viewbox2.Child = image1;
viewbox3.Child = image2;
viewbox4.Child = image3;
viewbox5.Child = image4;
viewbox6.Child = image5;
viewbox7.Child = image6;
viewbox8.Child = image7;
            
carousel.Items.Add(new CarouselItem() {Content = viewbox1 });
carousel.Items.Add(new CarouselItem() { Content = viewbox2 });
carousel.Items.Add(new CarouselItem() { Content = viewbox3 });
carousel.Items.Add(new CarouselItem() { Content = viewbox4 });
carousel.Items.Add(new CarouselItem() { Content = viewbox5 });
carousel.Items.Add(new CarouselItem() { Content = viewbox6 });
carousel.Items.Add(new CarouselItem() { Content = viewbox7 });
carousel.Items.Add(new CarouselItem() { Content = viewbox6 });

{% endhighlight %}

{% highlight VB %}

Dim carousel As Carousel = New Carousel

Dim image As Image = New Image
Dim image1 As Image = New Image
Dim image2 As Image = New Image
Dim image3 As Image = New Image
Dim image4 As Image = New Image
Dim image5 As Image = New Image
Dim image6 As Image = New Image
Dim image7 As Image = New Image

Dim bitimg1 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/1.png", UriKind.RelativeOrAbsolute))
Dim bitimg2 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/2.png", UriKind.RelativeOrAbsolute))
Dim bitimg3 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/3.png", UriKind.RelativeOrAbsolute))
Dim bitimg4 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/4.png", UriKind.RelativeOrAbsolute))
Dim bitimg5 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/5.png", UriKind.RelativeOrAbsolute))
Dim bitimg6 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/6.png", UriKind.RelativeOrAbsolute))
Dim bitimg6 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/7.png", UriKind.RelativeOrAbsolute))
Dim bitimg8 As BitmapImage = New BitmapImage(New Uri("/Sample;component/Images/8.png", UriKind.RelativeOrAbsolute))

image.Source = CType(bitimg1,ImageSource)
image1.Source = CType(bitimg2,ImageSource)
image2.Source = CType(bitimg3,ImageSource)
image3.Source = CType(bitimg4,ImageSource)
image4.Source = CType(bitimg5,ImageSource)
image5.Source = CType(bitimg6,ImageSource)
image6.Source = CType(bitimg7,ImageSource)
image7.Source = CType(bitimg8,ImageSource)

Dim viewbox1 As Viewbox = New Viewbox
Dim viewbox2 As Viewbox = New Viewbox
Dim viewbox3 As Viewbox = New Viewbox
Dim viewbox4 As Viewbox = New Viewbox
Dim viewbox5 As Viewbox = New Viewbox
Dim viewbox6 As Viewbox = New Viewbox
Dim viewbox7 As Viewbox = New Viewbox
Dim viewbox8 As Viewbox = New Viewbox

viewbox1.Child = image
viewbox2.Child = image1
viewbox3.Child = image2
viewbox4.Child = image3
viewbox5.Child = image4
viewbox6.Child = image5
viewbox7.Child = image6
viewbox8.Child = image7

carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.jpeg)