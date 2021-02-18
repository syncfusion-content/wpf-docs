---
layout: post
title: Troubleshooting | Wpf | Syncfusion
description: Syncfusion Troubleshooter is Visual Studio extension to troubleshoot the configuration issues in Syncfusion assembly reference, webconfig entries in projects.
platform: wpf
control: Syncfusion Extensions
documentation: ug
---

# Troubleshoot the project

Troubleshoot the project with the Syncfusion configuration and apply the fix like, wrong .NET Framework version of added Syncfusion assembly to the project or missing any Syncfusion dependent assembly of a referred assembly. The Syncfusion Troubleshooter can do the following:

* Report the Configuration issues.  
* Apply the solution

## Report the Configuration issues

The following steps help you to utilize the Syncfusion Troubleshooter by Visual Studio. 

> Before use the Syncfusion Troubleshooter for WPF, check whether the **WPF Extensions - Syncfusion** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed.

1. To open Syncfusion Troubleshooter Wizard, follow either one of the options below: 
   
   **Option 1**  
   Open an existing Syncfusion WPF Application, Click **Syncfusion Menu** and choose **Essential Studio for WPF > Troubleshoot…** in Visual Studio.

   ![Syncfusion Troubleshooter via Syncfusion menu](SyncfusionTroubleshooter_images/Syncfusion_Menu_Troubleshooter.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**  
   Right-click the Project file in Solution Explorer, then select the command Syncfusion Troubleshooter…

   ![Syncfusion Troubleshooter add-in](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img1.png)

2. Now, analyze the project and it will report the project configuration issues of Syncfusion controls in the Troubleshooter dialog if any issues found. If the project does not have any configuration issues, the dialog box will show there is no configuration changes required in following areas:

* Syncfusion assembly references.
* Syncfusion NuGet Packages. 
* Syncfusion Toolbox Configuration.

   ![No configuration changes required dialog box](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img2.png)

I> The Syncfusion Troubleshooter command will be visible only for Syncfusion projects that means the project should contain Syncfusion assemblies or Syncfusion NuGet packages referred.

The Syncfusion Troubleshooter handles the following project configuration issues: 

1. Assembly Reference Issues.

2. NuGet related Issues.

3. Toolbox Configuration Issues.

### Assembly Reference Issues

The Syncfusion Troubleshooter deals with the following assembly reference issues in Syncfusion Projects. 

1. Dependent assemblies are missing for referred assemblies from project. 

   **For Instance:**  : If “Syncfusion.Chart.WPF” assembly referred in project and “Syncfusion.Shared.WPF” (dependent of Syncfusion.Chart.Base) not referred in project, the Syncfusion Troubleshooter will show dependent assembly missing.

   ![Dependent assemblies missing issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img3.png)

2. Syncfusion assembly version mismatched. Compare to all Syncfusion assembly’s versions in the same project. If found any Syncfusion assembly version inconsistency, the Syncfusion Troubleshooter will show Syncfusion assemblies version mismatched. 

   **For Instance:**  If “Syncfusion.Tools.WPF” assembly (v17.1450.0.32) referred in project, but other Syncfusion assemblies referred assembly version is v17.1450.0.38. The Syncfusion Troubleshooter will show Syncfusion assembly version mismatched.

   ![Assembly version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img4.png)

3. Framework version mismatching (Syncfusion Assemblies) with project’s .NET Framework version. Find the supported .NET Framework details for Syncfusion assemblies in the following link,

   <https://help.syncfusion.com/common/essential-studio/assembly-information#supported-framework-version-for-essential-studio-assemblies> 

   **For Instance:** The.NET Framework of the application is v4.5 and “Syncfusion.Tools.WPF” assembly (v17.1460.0.38 & .NET Framework version 4.6) referred in same application. The Syncfusion Troubleshooter will show Syncfusion assembly .NET Framework version is incompatible with project’s .NET Framework version.

   ![Target Framework version of application](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img5.jpg)

   ![Framework mismatch issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img6.png)

### NuGet Issues

The Syncfusion Troubleshooter deals with the following NuGet package related issues in Syncfusion projects. 

1. Multiple versions of Syncfusion NuGet Packages are installed. If Syncfusion NuGet Package version is differ from other Syncfusion NuGet Package version, the Syncfusion Troubleshooter will show Syncfusion NuGet package version is mismatched. 

   **For Instance:** Syncfusion WPF platform packages installed multiple version (v16.4.0.54 & v17.1.0.38), Syncfusion Troubleshooter will be shown Syncfusion package version mismatched.
 
   ![Syncfusion NuGet Packages version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img7.png)

2. Installed Syncfusion NuGet package’s Framework version is differing from the project’s .NET Framework version.

   **For Instance:** If “Syncfusion.SfBulletGraph.WPF40” NuGet package version(v15.4.0.17 with 4.0 Framework) installed in project, But the project .NET Framework version is 4.5. So, the Syncfusion Troubleshooter will show Syncfusion package Framework version is mismatched.
  
   ![Syncfusion NuGet packages Framework version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img8.png)

3. Dependent NuGet package of the installed Syncfusion NuGet packages is missing.

   **For Instance:** If install Syncfusion.Chart.WPF NuGet package alone in project, Syncfusion Troubleshooter will show the Syncfusion.Chart.Base and other dependent NuGet package missing.
 
   ![Dependent NuGet package missing issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img9.png)

I> Internet connection is required to restore the missing dependent packages. If internet is not available, the dependent packages will not be restored.

### Toolbox Configuration Issues

The Syncfusion Troubleshooter deals with the following Toolbox Configuration related issues in Syncfusion projects. 

1. If the project .NET Framework version is not installed/configured Syncfusion Toolbox, the Syncfusion Troubleshooter will show Syncfusion Toolbox .NET Framework version is mismatched. 

   **For Instance:** The project .NET Framework version is 4.5 and Syncfusion Toolbox is not configured 4.6 framework assemblies only in corresponding Visual Studio, the Syncfusion Troubleshooter will show Syncfusion Toolbox framework version mismatched.
 
   ![Syncfusion Toolbox Framework version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img10.png)

2. If Syncfusion Toolbox configured version is differed from latest Syncfusion assembly reference version or NuGet package version in same project, the Syncfusion Troubleshooter will show Syncfusion Toolbox version is mismatched.

   **For Instance:** If latest Syncfusion assembly reference version is v17.1.0.38 but Toolbox assemblies configured v17.1.0.32, the Syncfusion Troubleshooter will show Syncfusion Toolbox version mismatched.
  
   ![Syncfusion Toolbox version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img11.png)

## Apply the solution

1. After loading the Syncfusion Troubleshooter dialog, check the corresponding check box of the issue to be resolved. Then click the “Fix Issue(s)” button. 

   ![Syncfusion Troubleshooter wizard with project configuration issues](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img12.png)

2. A dialog appears, which will ask to take a backup of the project before performing the troubleshooting process. If you need to backup the project before troubleshooting, click “Yes” button. 

   ![Syncfusion Troubleshooter backup dialog](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img13.jpeg)

3. Wait for a while, the Syncfusion Troubleshooter is resolving the selected issues. After the troubleshooting process completed, there will be a status message in the Visual Studio status bar as “Troubleshooting process completed successfully”.

   ![Syncfusion Troubleshooter process success status message in visual studio status bar](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img14.jpeg)

4. Then, Syncfusion licensing registration required message box will be shown, if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the  [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.   

   ![Syncfusion license registration required information dialog in Syncfusion Troubleshooter](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img15.jpeg)