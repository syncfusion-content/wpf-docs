---
layout: post
title: Syncfusion Item Template for WPF | Wpf | Syncfusion
description: Syncfusion item template extension supports to add the Syncfusion WPF Window into WPF application with add Syncfusion WPF references.
platform: wpf
control: Syncfusion Extensions
documentation: ug
---


# Add Syncfusion Components to the WPF Application

Syncfusion supports Visual Studio Item Templates to add Syncfusion WPF Components to a WPF application with Syncfusion WPF references. 

I> The Syncfusion WPF item templates are available from v19.1.0.54. 

The following steps will guide you to add the Syncfusion WPF Components to your Visual Studio WPF application.

> Check whether the **WPF Extensions - Syncfusion** are installed or not in Visual Studio Extension Manager by going to **Extensions -> Manage Extensions -> Installed** for Visual Studio 2019 or later and Visual Studio 2017 or lower by going to **Tools -> Extensions and Updates -> Installed**. If this extension is not installed, please install the extension by following the steps from the [download and installation](https://help.syncfusion.com/wpf/visual-studio-integration/download-and-installation) help topic.

## Add Components using Syncfusion Item Template

1.	Open a new or existing WPF application.

	**Option 1:**

2.	From the **Solution Explorer, right-click** on the WPF application. Choose **Add Syncfusion Item...**.

	![Choose Add Syncfusion Item option from right click project](Add-Item-images/Add-syncfusion-item.png)

	**Option 2:**

3.	Click **Extensions > Essential Studio for WPF > Add Syncfusion Item…** in Visual Studio.

	![Choose Add Syncfusion Item option from menu](Add-Item-images/Add-item.png)


4.	The Syncfusion WPF Item Template wizard will be launched as follows.

	![Syncfusion WPF Item template Components](Add-Item-images/Add-syncfusion-ui.png)

5.	Select the WPF Components from the Component list within your WPF Item Template. The features associated with the selected Component will be presented. From here, 		choose the specific features that are essential for your project.

6.	Choose an assembly reference option such as GAC location, Essential Studio installed location, or NuGet packages to specify where the required Syncfusion assemblies 	are added to the project.

	N> If the Syncfusion Essential WPF build is installed, the Installed location and GAC options will be enabled. Without installing the Syncfusion Essential WPF setup, use the NuGet option. The GAC option will not be available when using the Syncfusion WPF Components in a .NET Core application. The Version drop-down lists the installed WPF versions.

7.  Click **Add**, and a pop-up will appear providing information about adding Component **files** and **NuGet/Assemblies** details.

	![Syncfusion WPF Item template details](Add-Item-images/Add-syncfusion-item-3.png)	

8.	Click **OK** to incorporate the chosen Components into the WPF application, along with the necessary Syncfusion assemblies.

	![Syncfusion WPF Item template Gallery](Add-Item-images/Add-syncfusion-item-details.png)

9.	Then, Syncfusion licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion introduced the 			licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/			licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to 		your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post 	 for understanding the licensing changes introduced in Essential Studio.

    ![Syncfusion WPF Item template Gallery](Add-Item-images/LicensePage.png)
	