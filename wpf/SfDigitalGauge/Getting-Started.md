---
layout: post
title: Getting Started | SfDigitalGauge | wpf | Syncfusion
description: getting started 
platform: wpf
control: SfDigitalGauge 
documentation: ug
---

# Getting Started 

## Creating Digital Gauge Programmatically

The following code example explains how to add a Digital Gauge in your application:

{% tabs %}

{% highlight xaml %}

<Window x:Class="SfDigitalGauge.MainWindow"

        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

        Title="MainWindow" Height="350" Width="525">

    <Grid Name="Grid">

        <syncfusion:SfDigitalGauge></syncfusion:SfDigitalGauge>

    </Grid>

</Window>

{% endhighlight %}

{% highlight c# %}

SfDigitalGauge digitalgauge = new SfDigitalGauge();

this.Grid.Children.Add(digitalgauge);

{% endhighlight %}

{% endtabs %}


### Screenshot:

![](Getting-Started_images/Getting-Started_img1.png)

## Creating a SfDigitalGauge with the Syncfusion Reference Manager

Syncfusion Reference Manager is used to add Syncfusion Tools.

To add SfDigitalGauge Control, refer to the following steps:

1. Create a simple WPF application by using Visual Studio.

   ![](Getting-Started_images/Getting-Started_img2.png)

2. Right-Click on the Project and select Syncfusion Reference Manager.

   ![](Getting-Started_images/Getting-Started_img3.png)

3. The Syncfusion Reference Manager Wizard is opened as follows.

   ![](Getting-Started_images/Getting-Started_img4.png)

4. Search SfDigitalGauge by using Search Box and select SfDigitalGauge Control.  Click done to add selected SfDigitalGauge Control.

   ![](Getting-Started_images/Getting-Started_img5.png)

5. The SfDigitalGauge  assemblies are automatically added to the Project after Clicking OK.

   ![](Getting-Started_images/Getting-Started_img6.png)

   ![](Getting-Started_images/Getting-Started_img7.png)

6. Create a namespace reference to the SfDigitalGauge control by using Syncfusion’s global namespace reference schemas.syncfusion.com or the SfDigitalGauge control’s namespace reference by using Syncfusion.UI.Xaml.Gauges available in the Syncfusion. SfDigitalGauge.WPF assembly.
 
   ~~~ xaml

		xmlns:syncfusion ="http://schemas.syncfusion.com/wpf" 

   ~~~   
   
7. Add the following code example to create a simple SfDigitalGauge control.

   ~~~ xaml

		<Window x:Class="SfDigitalGauge.MainWindow"

				xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

				xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

				xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

				Title="MainWindow" Height="350" Width="525">

			<Grid Name="Grid">

				<syncfusion:SfDigitalGauge></syncfusion:SfDigitalGauge>  

			</Grid>

		</Window> 

   ~~~

   ~~~ csharp

		using System.Windows;

		using Syncfusion.UI.Xaml.Gauges;

		namespace  DigitalGauge

		{
			public partial class MainWindow : Window

			{
				public MainWindow()

				{
					InitializeComponent();

					SfDigitalGauge digitalgauge = new SfDigitalGauge();

					this.Grid.Children.Add(digitalgauge);

				 }
			}
		}

   ~~~
   
8. The SfDigitalGauge control is created as follows.

   ![](Getting-Started_images/Getting-Started_img8.png)

N>
N> 1. The Syncfusion Reference Manager is available in versions 11.3.0.30 and later. It supports referencing assemblies from version 10.4.0.71 version to the current version.
N>
N> 2. The Syncfusion Reference Manager is used only in Visual Studio 2010, 2012, and 2013.
