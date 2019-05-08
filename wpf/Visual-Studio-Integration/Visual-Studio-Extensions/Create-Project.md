---
layout: post
title: Create Project | Wpf | Syncfusion
description: Syncfusion provides the Visual Studio Project Templates for the Syncfusion WPF platform to create Syncfusion WPF Application by addiing the required assemblies
platform: wpf
control: Syncfusion Extensions
documentation: ug
---


# Create Project

Syncfusion provides the Visual Studio Project Templates for the Syncfusion WPF platform to create the Syncfusion WPF Application by adding the required Syncfusion assemblies and XMAL. 

I> The Syncfusion WPF templates are available from v16.1.0.24. 

Use the following steps to create the Syncfusion WPF project through the Visual Studio Project Template. 

1. To create a Syncfusion WPF project, follow either one of the options below:

   **Option 1:**  
   Click **Syncfusion Menu** and choose **Essential Studio for WPF > Create New Syncfusion Project…** in **Visual Studio**.
    
   ![Choose Syncfusion WPF Application from Visual Studio new project dialog via Syncfusion menu](Project-Template-images\Syncfusion_Menu_ProjectTemplate.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2:**   
   Choose **File > New > Project** and navigate to **Syncfusion > Windows > Syncfusion WPF Application** in **Visual Studio**.

   ![Choose Syncfusion WPF Application from Visual Studio new project dialog](Project-Template-images\Syncfusion-Project-Template-Gallery-1.png)

2. Name the **Project**, choose the destination location when required, and set the Framework of the project, then click **OK**.  

   N> Minimum target Framework is 4.0 for Syncfusion WPF project templates. 

3. Choose the options to configure the Syncfusion WPF Application by using the following Project Configuration Wizard.  
  
   ![Syncfusion WPF project configuration wizard](Project-Template-images\Syncfusion-Project-Template-Gallery-2.png)
                                                     
   **Project Configurations**

   **Language:** Select the language, either C# or VB. 

   ![Choose the language in Syncfusion WPF project configuration wizard](Project-Template-images\Syncfusion-Project-Template-Gallery-3.png)

   **Assemblies From:** Choose the assembly location from, where the assembly is added to the project. 

   ![Choose the required assemblies from option from where assemblies to be referred in the project](Project-Template-images\Syncfusion-Project-Template-Gallery-5.png)

   N> Installed location and GAC option will be available only when the Syncfusion Essential WPF setup has been installed. You can use NuGet option without installing the Syncfusion Essential WPF setup.

   **Installed ES Build Version:** Choose the build version to add the corresponding version assemblies to the project.

   ![Choose the build version to add the corresponding version assemblies to the project](Project-Template-images\Syncfusion-Project-Template-Gallery-6.png)

   N> Installed ES build version option will be available only when you install the Syncfusion Essential WPF setup and choose the assembly location as Installed Location or GAC.

   **Choose Theme:** Choose the required theme. 

   ![Choose theme in Syncfusion WPF project configuration wizard](Project-Template-images\Syncfusion-Project-Template-Gallery-4.png)

   **Select Control:** Choose the control as required. 

   ![Choose the control based in Syncfusion WPF project configuration wizard](Project-Template-images\Syncfusion-Project-Template-Gallery-7.png)
      
4. After the Project Configuration Wizard is done, the Syncfusion WPF project is created with required references and XAML. 

   ![Syncfusion WPF project created with required Syncfusion WPF assemblies](Project-Template-images\Syncfusion-Project-Template-Gallery-8.png)

   ![Syncfusion WPF project created with required Syncfusion XAML files](Project-Template-images\Syncfusion-Project-Template-Gallery-9.png)

5. Then, Syncfusion licensing registration required message box will be shown, if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the  [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.

   ![Syncfusion license registration required information dialog in Syncfusion WPF project](Project-Template-images\Syncfusion-Project-Template-Gallery-10.png)   