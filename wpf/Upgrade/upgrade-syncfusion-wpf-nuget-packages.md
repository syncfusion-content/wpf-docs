---
layout: post
title: Upgrade Syncfusion WPF NuGet packages| WPF Forms | Syncfusion
description: This section provides the information about upgrade the Syncfusion WPF NuGet packages by using Package Manager UI, .NET CLI, and Package Manager Console.
platform: WPF
control: Essential Studio
documentation: ug
---

# Upgrading Syncfusion WPF NuGet packages to a latest version

Every three months, Syncfusion releases new volumes with interesting new features. For this volume, there will be weekly NuGet release and one service pack. Syncfusion WPF NuGet packages are released on a weekly basis to address critical issue fixes.

From any Syncfusion WPF NuGet version you have installed; you can update to our most recent version.


## Upgrade NuGet packages through Package Manager UI

The NuGet **Package Manager UI** in Visual Studio allows you to easily install, uninstall, and update NuGet packages in applications and solutions. You can find and upgrade the Syncfusion WPF NuGet packages to the most recent version or to specific version in the WPF solution or application and this process is easy with the steps below:

1. Right-click on the WPF application or solution in the Solution Explorer tab, and choose **Manage NuGet Packages...**

    ![Manage NuGet Packages add-in](Upgrade-images/manage-nuget.png)

    As an alternative, after opening the WPF application in Visual Studio, go to the **Tools** menu and after hovering **NuGet Package Manager**, select **Manage NuGet Packages for Solution...**

2. The Manage NuGet Packages window will open. Navigate to the Updates tab, then search for the Syncfusion WPF NuGet packages using a term like **"Syncfusion"** and and select the appropriate Syncfusion WPF NuGet package for your application.

    > The [nuget.org](https://api.nuget.org/v3/index.json) package source is selected by default in the Package source drop-down. If your Visual Studio does not have nuget.org configured, follow the instructions in the [Microsoft documents](https://docs.microsoft.com/en-us/nuget/tools/package-manager-ui#package-sources) to set up the nuget.org feed URL.

3. By default, the package selected with latest version. You can select the required version and click the Update button and accept the license terms. The package will be upgraded to selected version in your WPF application.

    ![WPF Upgrade](Upgrade-images/NuGetUpgrade.png)

    You can choose the multiple NuGet packages by selecting the checkbox like below and click the **Update** button to update the multiple Syncfusion NuGet packages in your application.

    ![Winform NuGet Upgrade](Upgrade-images/MultipleNuGetUpgrade.png)

## Upgrade NuGet packages through .NET CLI

There is no distinct command for the update procedure in the .NET CLI. Unless you specify the package version, .NET CLI installs the latest version of the Syncfusion WPF NuGet packages when you use the dotnet add package command.

To specify a version, add the -v parameter:

```dotnet add package Syncfusion.SfGrid.WPF -v 19.3.0.44.```

## Upgrade NuGet packages through Package Manager Console

The **Package Manager Console** saves saves NuGet packages upgrade time since you don't have to search for the package you want to update, and you can just type the command to update the appropriate Syncfusion WPF NuGet package. Follow the steps below to upgrade the installed Syncfusion NuGet packages using the Package Manager Console in your WPF application.

1. To show the Package Manager Console, open your WPF application in Visual Studio and navigate to **Tools** in the Visual Studio menu and after hovering **NuGet Package Manager**, select **Package Manager Console**.

    ![Package Manager Console](Upgrade-images/console.png)

2.  The Package Manager Console will be shown at the bottom of the screen. You can install the Syncfusion WPF NuGet packages by enter the following NuGet update commands.

    ***Update specified Syncfusion WPF NuGet package***

    The below command will update the Syncfusion WPF NuGet package in the default WPF application.

    ```Update-Package <Package Name>```

    **For example:** Update-Package Syncfusion.SfGrid.WPF

    ***Update specified Syncfusion WPF NuGet package in specified WPF application***

    The below command will update the Syncfusion WPF NuGet package in the given WPF application alone.

    ```Update-Package <Package Name> -ProjectName <Project Name>```

    **For example:** Update-Package Syncfusion.SfGrid.WPF -ProjectName SyncfusionWpfApp

3. By default, the package will be installed with latest version. You can give the required version with the -Version term like below to install the Syncfusion WPF NuGet packages in the appropriate version.

    ```Update-Package Syncfusion.SfGrid.WPF -Version 19.3.0.44```

    ![Package Manager Console Output](Upgrade-images/UpdateConsole.png)

4. The NuGet package manager will update the Syncfusion WPF NuGet package as well as the dependencies it has.