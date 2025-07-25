---
layout: post
title: Create Project | Wpf | Syncfusion
description: Syncfusion provides the Visual Studio Project Templates for the Syncfusion WPF platform to create Syncfusion WPF Application by addiing the required assemblies
platform: wpf
control: Syncfusion Extensions
documentation: ug
---


# Create WPF application

The Visual Studio Project Templates for the Syncfusion® WPF platform allow you to quickly develop a Syncfusion WPF application by just adding the appropriate Syncfusion® assemblies and XAML. 

I> The Syncfusion WPF templates are available from v16.1.0.24. 

> WPF Project Template works seamlessly with Visual Studio 2015 or lower. For the Visual Studio 2017 or later versions, it is recommended to use a [WPF Template Studio](https://help.syncfusion.com/wpf/visual-studio-integration/template-studio).

Create the Syncfusion® WPF project using the Visual Studio Project Template by following the steps below: 

> Check whether the **WPF Extensions - Syncfusion** are installed or not in Visual Studio 2015 or lower by going to **Tools -> Extensions and Updates -> Installed**. If this extension is not installed, please install the extension by following the steps from the [download and installation](https://help.syncfusion.com/wpf/visual-studio-integration/download-and-installation) help topic.

1.	To create a Syncfusion® WPF project, follow either one of the options below:

	**Option 1:**  
	Click **Syncfusion** Menu and choose **Essential Studio® for WPF > Create New Syncfusion Project…**  in **Visual Studio**.
    
	![Choose Syncfusion WPF Application from Visual Studio new project dialog via Syncfusion menu](Project-Template-images/Syncfusion-Menu.png)

	N> In Visual Studio 2015 or lower, you can see the  Syncfusion menu directly in the Visual Studio menu.

	**Option 2:**   
	Choose **File -> New -> Project**. Opens a new dialog to create a new project. By filtering the project type with Syncfusion or using the Syncfusion keyword in the search option, you can get the templates offered by Syncfusion for WPF.

	![Choose Syncfusion WPF Application from Visual Studio new project dialog](Project-Template-images/Syncfusion-Project-Template-Gallery2019-1.png)

	In Visual Studio 2015 or lower, Select **File > New > Project** and navigate to **Syncfusion > Windows > Syncfusion WPF Application** in Visual Studio. 

	![Choose Syncfusion WPF Application from Visual Studio new project dialog](Project-Template-images/Syncfusion-Project-Template-Gallery-1.png)

2.	Name the **Project**, select the destination location when required, and specify the Framework of the project, then click **OK**.  

	N> For Syncfusion® WPF project templates, the minimum target Framework is 4.0. 

3.	Using the following Project Configuration Wizard, choose the options to configure the Syncfusion WPF Application.  
  
	![Syncfusion WPF project configuration wizard](Project-Template-images/Syncfusion-Project-Template-Gallery2019-2.png)
                                                 
	In Visual Studio 2015 or lower, Syncfusion WPF Application project configuration wizard. 

	![Syncfusion WPF project configuration wizard](Project-Template-images/Syncfusion-Project-Template-Gallery-2.png)

	**Project Configurations**

	**Language:** Select the language, either CSharp or VB.

	N> VB language is available only when you choose .NET Framework from option in Visual Studio.

	**Choose Theme:** Select the required theme.

	**Reference From:** Choose the assembly location such as NuGet, GAC Location, or Essential Studio® installed location, from where the assembly is added to the project.

	N> The **Installed Location** and **GAC** options will be available only after the Syncfusion® Essential WPF setup has been installed. You can use the NuGet option instead of installing the Syncfusion® Essential WPF setup.

	**Installed ES Build Version:** To add the appropriate version assemblies to the project, choose the build version.

	N> Installed ES build version option will be available only if you install the Syncfusion® Essential WPF setup and select Installed Location or GAC as the assembly location.

	**Size Mode:** Select the Size Mode either Default or Touch.

	**Select Window:** Choose the window as required for application.

	N> Project create option will be enabled only if you have selected the window
      
4.	After choosing the above project configuration options in the Project Configuration Wizard, click the Create button, and then the Syncfusion® WPF project is created with the necessary XAML files and required Syncfusion® WPF assemblies/NuGet packages.  

	![Syncfusion WPF project created with required Syncfusion WPF assemblies](Project-Template-images/Syncfusion-Project-Template-Gallery-7.png)

	![Syncfusion WPF project created with required Syncfusion XAML files](Project-Template-images/Syncfusion-Project-Template-Gallery-8.png)

	![Syncfusion WPF project created with readme](Project-Template-images/Syncfusion-Project-Template-Gallery-10.png)

5.	Then, Syncfusion® licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion® introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio® release. Navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/overview#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion® license key to your project. Refer to this [blog](https://www.syncfusion.com/blogs/post/whats-new-in-2018-volume-2.aspx) post for understanding the licensing changes introduced in Essential Studio®.

	![Syncfusion license registration required information dialog in Syncfusion WPF project](Project-Template-images/Syncfusion-Project-Template-Gallery-9.png)   