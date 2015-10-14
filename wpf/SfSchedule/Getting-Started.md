---
layout: post
title: Getting Started| SfSchedule | Wpf | Syncfusion
description: getting started
platform: wpf
control: SfSchedule
documentation: ug
---

# Getting Started

## Creating a Schedule

1. Schedule is available in the following assembly and namespace:


   Assembly: Syncfusion.SfSchedule.WPF

   Namespace: Syncfusion.UI.Xaml.Schedule

   Refer to the following code to add a Schedule:


   ~~~xaml
   
	<Window x:Class="SfScheduleSample.MainWindow"       xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

	        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

	        xmlns:schedule="http://schemas.syncfusion.com/wpf"

	        WindowStartupLocation="CenterScreen" WindowStyle="None"

	        Width="950" Height="600">

	    <Grid x:Name="LayoutRoot">

	        <schedule:SfSchedule/>

	    </Grid>

        </Window>

   ~~~



   ~~~csharp


	SfSchedule schedule = new SfSchedule();

	this.grid.Children.Add(schedule);

   ~~~


2. Run the above code and now the empty Scheduler can be seen as follows but with no appointments. In order to display the appointments on the scheduler, either the local or remote data needs to be passed to it.





  ![](Getting-Started_images/Getting-Started_img1.png)



## Creating the SfSchedule Control with the Syncfusion Reference Manager

Syncfusion Reference Manager is used to add   Syncfusion Tools in Visual Studio.

To Add SfSchedule Control, follow the steps below:

1. Create a simple WPF application using Visual Studio.

   ![](Getting-Started_images/Getting-Started_img2.png)



2. Right Click on the Project and select Syncfusion Reference Manager.

   ![](Getting-Started_images/Getting-Started_img3.png)



3. The Syncfusion Reference Manager Wizard will be opened as shown in the figure below.

   ![](Getting-Started_images/Getting-Started_img4.png)



4. Search for “SfSchedule” using SearchBox and select SfSchedule Control.  Click on done to add selected SfSchedule Control.

   ![](Getting-Started_images/Getting-Started_img5.png)
 


5. The SfSchedule assemblies will be automatically added to the Project after Clicking OK

   ![](Getting-Started_images/Getting-Started_img6.png)



   ![](Getting-Started_images/Getting-Started_img7.png)



6. Create a namespace reference to the SfSchedule control using Syncfusion’s global namespace reference schemas.syncfusion.com or the SfSchedule control’s namespace reference Syncfusion.UI.Xaml.Schedule available in the Syncfusion.SfSchedule.WPF assembly.


   ~~~xaml
   
      xmlns:schedule="http://schemas.syncfusion.com/wpf"



         (or)



   xmlns:schedule="clr-namespace:Syncfusion.UI.Xaml.Schedule;assembly=Syncfusion.SfSchedule.WPF"








   ~~~






7. Add the following code to create a simple SfSchedule control.

   ~~~xaml

		<Window x:Class="SfScheduleSample.MainWindow"       xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

		        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

		        xmlns:schedule="http://schemas.syncfusion.com/wpf"

		        WindowStartupLocation="CenterScreen" WindowStyle="None"

		        Width="950" Height="600">

		    <Grid x:Name="LayoutRoot">

		        <schedule:SfSchedule/>
	
	       </Grid>

	  </Window>



   ~~~



   ~~~csharp

		using Syncfusion.UI.Xaml.Schedule;

		using System.Windows;



		namespace SfScheduleSample

		{

		    public partial class MainWindow : Window

		    {

		        public MainWindow()

		        {

		            InitializeComponent();

		            SfSchedule sfSchedule = new SfSchedule();

		            this.LayoutRoot.Children.Add(sfSchedule);

		        }

		    }

		}
		
   ~~~


8. The simple SfSchedule control will be created as shown in the figure below.

   ![C:/Users/jeyasri/Pictures/Schedule/Default.png](Getting-Started_images/Getting-Started_img8.png)



N>1. The Syncfusion Reference Manager is available in versions 11.3.0.30 and later. It supports referencing assemblies from version 10.4.0.71 version to the current version. 2. The Syncfusion Reference Manager can be used only in Visual Studio 2010, 2012, and 2013.



