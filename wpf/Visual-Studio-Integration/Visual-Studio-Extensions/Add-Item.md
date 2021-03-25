---
layout: post
title: Syncfusion Item Template for WPF | Wpf | Syncfusion
description: Syncfusion item template extension supports to add the Syncfusion WPF Window into WPF application with add Syncfusion WPF references.
platform: wpf
control: Syncfusion Extensions
documentation: ug
---


# Add Syncfusion window to WPF application

Syncfusion provides the Visual Studio Item Templates support to add Syncfusion WPF Window into the WPF application with Syncfusion WPF references. Syncfusion WPF window provides an option to customize the window title bar quickly and comes with various built-in themes to present an appealing User Interface.

I> The Syncfusion WPF item templates are available from v19.1.0.54. 

The following steps help you to add the Syncfusion WPF window in the Visual Studio WPF application. 

> Before using the Syncfusion WPF Item Template, check whether the **WPF Extensions - Syncfusion** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed. If It is not installed, then install the [Syncfusion WPF Extensions](https://help.syncfusion.com/wpf/visual-studio-integration/visual-studio-extensions/download-and-installation).

1. Open a new or existing WPF application.
2. Right-click on the WPF application from the Solution Explorer. Select the Add Syncfusion Item… option.

      ![Choose Add Syncfusion Item option from right click project](Add-Item-images\Add-syncfusion-item.png)

3. The Syncfusion WPF Item Template Gallery wizard will open.

      ![Syncfusion WPF Item template Gallery](Add-Item-images\Syncufsion-Item-Template-Gallery.png)
4.	Syncfusion provided the Chromeless Window and Ribbon Window. Select the required window in the Select Window section. 
5.	Choose the assembly reference option for wherefrom the required Syncfusion assemblies are added to the project.

    > The Installed location and GAC option will enable if Syncfusion Essential WPF build are installed. You can use the NuGet option without installing the Syncfusion Essential WPF setup. The GAC option will not be listed if adding the Syncfusion WPF window in the .NET Core application. The WPF installed versions are listed in the Version dropdown.
6.	Provide the name for the selected window.
7.	Click Add button to add the selected window into the WPF application along with required Syncfusion assemblies.

      ![Syncfusion WPF Item template Gallery](Add-Item-images\Added-Item.png)
8.	The Syncfusion licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from the 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the help topic, which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this blog post for understanding the licensing changes introduced in Essential Studio.

      ![Syncfusion WPF Item template Gallery](Add-Item-images\LicensePage.png)

## Add window using the Visual Studio Add New Item dialog

The Syncfusion Item Template can also be added from the Visual Studio Add New Item dialog.


1.	To add a Syncfusion WPF window, follow either one of the following options:

      **Option 1:**

      Click Extensions ->Syncfusion Menu and choose Essential Studio for WPF > Add ChromelessWindow… or any other window in Visual Studio.    

      ![Syncfusion Menu](Add-Item-images\SyncfusionMenu.png)

      > In Visual Studio 2017 or lower, the Syncfusion menu is available in the Visual Studio menu.

      **Option 2:**

      Right-click the WPF application in Solution Explorer, select Add > New Item, and then navigate to Visual C# Items or VB Items. Refer to the following screenshot for more information.

      ![Add New Item Dialog](Add-Item-images\AddNewMenu.png)

      > The Syncfusion WPF Item Templates are available under the Syncfusion -> WPF tab. It is available for both C# Items and VB Items.

      ![Add New Item Dialog](Add-Item-images\AddNewItemDialog.png)

2.	Click Add button and now the selected window is added to the project along with the Syncfusion NuGet reference.
      ![Syncfusion WPF Item template Gallery](Add-Item-images\Added-Item.png)

3.	 The Syncfusion licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from the 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the help topic, which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this blog post for understanding the licensing changes introduced in Essential Studio.

      ![Syncfusion WPF Item template Gallery](Add-Item-images\LicensePage.png)