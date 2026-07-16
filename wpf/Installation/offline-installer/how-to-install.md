---
layout: post
title: Installing Syncfusion WPF offline installer - Syncfusion
description: Learn here about how to install Syncfusion WPF offline installer after downloading from our Syncfusion website.
platform: wpf
control: Installation and Deployment
documentation: ug

---

# Installing Syncfusion WPF offline installer


## Prerequisites

* You must have a valid licensed or trial unlock key. See [How to generate the unlock key](https://support.syncfusion.com/kb/article/2757/how-to-generate-syncfusion-setup-unlock-key-from-syncfusion-support-account).
* Close all running Visual Studio instances before starting the installation.
* The WPF platform requires .NET Framework 4.5 or later (or .NET Core 3.1 / .NET 5 or later for .NET-based WPF projects) on the target machine.

## Installing with UI

The steps below show how to install the Essential Studio WPF installer.

1. Open the Syncfusion WPF offline installer file from the downloaded location by double-clicking it. The Installer Wizard automatically opens and extracts the package.

    ![Installer extraction wizard](images/Step-by-Step-Installation_img1.png)

    > N> The Installer Wizard extracts the `syncfusionessentialwpf_{version}.exe` dialog, which displays the package's unzip operation.

2. To unlock the Syncfusion offline installer, you have two options:

    * *Login To Install*
    * *Use Unlock Key*

    **Login To Install**

    You must enter your Syncfusion email address and password. If you don't already have a Syncfusion account, you can sign up for one by clicking **"Create an account"**. If you have forgotten your password, click **"Forgot Password"** to create a new one. Once you've entered your Syncfusion email and password, click **Next**.

    ![Login credentials](images/Step-by-Step-Installation_img2.png)

    **Use Unlock Key**

    Unlock keys are used to unlock the Syncfusion offline installer, and they are platform- and version-specific. You should use either a Syncfusion licensed or trial unlock key to unlock the Syncfusion WPF installer.

    The trial unlock key is only valid for 30 days, and the installer will not accept an expired trial key.

    To learn how to generate an unlock key for both trial and licensed products, see [this](https://support.syncfusion.com/kb/article/2757/how-to-generate-syncfusion-setup-unlock-key-from-syncfusion-support-account) Knowledge Base article.

    ![Product key](images/Step-by-Step-Installation_img3.png)

3. After reading the License Terms and Privacy Policy, check the **"I agree to the License Terms and Privacy Policy"** check box. Click the **Next** button.

4. Change the install and sample locations here. You can also change the additional settings. Click **Next** or **Install** to install with the default settings.

    ![Advanced options](images/Step-by-Step-Installation_img4.png)

    **Additional Settings**

    * Select the **Install Demos** check box to install Syncfusion samples, or leave the check box unchecked if you do not want to install Syncfusion samples.
    * Select the **Register Syncfusion Assemblies in GAC** check box to install the latest Syncfusion assemblies in GAC, or clear this check box when you do not want to install the latest assemblies in GAC.
    * Select the **Configure Syncfusion controls in Visual Studio** check box to configure the Syncfusion controls in the Visual Studio toolbox, or clear this check box when you do not want to configure the Syncfusion controls in the Visual Studio toolbox during installation. Note that you must also select the **Register Syncfusion assemblies in GAC** check box when you select this check box.
    * Select the **Configure Syncfusion Extensions controls in Visual Studio** check box to configure the Syncfusion Extensions in Visual Studio, or clear this check box when you do not want to configure the Syncfusion Extensions in Visual Studio.
    * Check the **Create Desktop Shortcut** check box to add a desktop shortcut for the Syncfusion Control Panel.
    * Check the **Create Start Menu Shortcut** check box to add a shortcut to the start menu for the Syncfusion Control Panel.

5. If any previous versions of the current product are installed, the **Uninstall Previous Version(s)** wizard will open. Select the **Uninstall** check box to uninstall the previous versions, then click the **Proceed** button.

    ![Advanced options](images/Step-by-Step-Installation_img7.png)

    > N> From the 2021 Volume 1 release, Syncfusion has added the option to uninstall previous versions from 18.1 while installing the new version.

    > N> If any version is selected to uninstall, a confirmation screen will appear. If **Continue** is selected, the **Progress** screen will display the uninstall and install progress, respectively. If none of the versions are chosen to be uninstalled, only the installation progress will be displayed.

    **Confirmation Alert**

    ![Confirmation wizard](images/Step-by-Step-Installation_img8.png)

    **Uninstall Progress:**

    ![Uninstalling wizard](images/Step-by-Step-Installation_img9.png)

    **Install Progress**

    ![Installing wizard](images/Step-by-Step-Installation_img5.png)

    > N> The **Completed** screen is displayed once the WPF product is installed. If any version is selected to uninstall, the **Completed** screen will display both install and uninstall status.

    ![Completed wizard](images/Step-by-Step-Installation_img10.png)

6. After installation, click the **Launch Control Panel** link to open the Syncfusion Control Panel.

7. Click the **Finish** button. Your system has now been installed with the Syncfusion Essential Studio WPF product.

## Installing in silent mode

The Syncfusion Essential Studio WPF Installer supports installation and uninstallation via the command line.

### Command Line Installation

To install through the Command Line in Silent mode, follow the steps below.

1. Run the Syncfusion WPF installer by double-clicking it. The Installer Wizard automatically opens and extracts the package.
2. The file `syncfusionessentialwpf_{version}.exe` will be extracted into the Temp directory.
3. Run `%temp%`. The Temp folder will open. The `syncfusionessentialwpf_{version}.exe` file will be located in one of the folders.
4. Copy the extracted `syncfusionessentialwpf_{version}.exe` file to a local drive.
5. Exit the Wizard.
6. Run Command Prompt in administrator mode and enter the following arguments.

    **Arguments:** `"installer file path\SyncfusionEssentialStudio(platform)_{version}.exe" /Install silent /UNLOCKKEY:"(product unlock key)" [/log "{Log file path}"] [/InstallPath:{Location to install}] [/InstallSamples:{true/false}] [/InstallAssemblies:{true/false}] [/UninstallExistAssemblies:{true/false}] [/InstallToolbox:{true/false}]`

    > N> Arguments inside square brackets are optional.

    **Example:** `"D:\Temp\syncfusionessentialwpf_x.x.x.x.exe" /Install silent /UNLOCKKEY:"product unlock key" /log "C:\Temp\EssentialStudio_Platform.log" /InstallPath:C:\Syncfusion\x.x.x.x /InstallSamples:true /InstallAssemblies:true /UninstallExistAssemblies:true /InstallToolbox:true`

7. Essential Studio for WPF is installed.

    > N> `x.x.x.x` should be replaced with the Essential Studio version, and the Product Unlock Key should be replaced with the Unlock Key for that version.

### Command Line Uninstallation

Syncfusion Essential WPF can be uninstalled silently using the Command Line.

1. Run the Syncfusion WPF installer by double-clicking it. The Installer Wizard automatically opens and extracts the package.
2. The file `syncfusionessentialwpf_{version}.exe` will be extracted into the Temp directory.
3. Run `%temp%`. The Temp folder will open. The `syncfusionessentialwpf_{version}.exe` file will be located in one of the folders.
4. Copy the extracted `syncfusionessentialwpf_{version}.exe` file to a local drive.
5. Exit the Wizard.
6. Run Command Prompt in administrator mode and enter the following arguments.

    **Arguments:** `"Copied installer file path\syncfusionessentialwpf_{version}.exe" /uninstall silent`

    **Example:** `"D:\Temp\syncfusionessentialwpf_x.x.x.x.exe" /uninstall silent`

7. Essential Studio for WPF is uninstalled.
   
   
