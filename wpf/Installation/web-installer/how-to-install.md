---
layout: post
title: Installing Syncfusion WPF web installer - Syncfusion
description: Learn here about how to install Syncfusion WPF web installer after downloading from our Syncfusion website.
platform: wpf
control: Installation and Deployment
documentation: ug
---

# Installing Syncfusion WPF web installer


## Overview

For the Essential Studio WPF product, Syncfusion offers a Web Installer. This installer alleviates the burden of downloading a larger installer. You can simply download and run the online installer, which will be smaller in size and will download and install the Essential Studio products you have chosen. You can get the most recent version of Essential Studio Web Installer [here](https://www.syncfusion.com/downloads/latest-version). 

 
## Installation

The steps below show how to install Essential Studio WPF Web Installer.

1.  Open the Syncfusion Essential Studio WPF Web Installer file from downloaded location by double-clicking it. The Installer Wizard automatically opens and extracts the package.

    ![WPF Installer Extraction Wizard](images/wpf-installer-extract-wizard.png)

    
    N> The installer wizard extracts the syncfusionessentialwpfwebinstaller_{version}.exe dialog, which displays the package's unzip operation.
    
2. 	The Syncfusion WPF Web Installer's welcome wizard will be displayed. Click the Next button.

    ![WPF Installation Welcome wizard](images/wpf-installation-welcome-wizard.png)

  
3.  The Platform Selection Wizard will appear. From the **Available** tab, select the products to be installed. Select the **Install All** checkbox to install all products. 
    
	<em>**Available**</em>
	
	![WPF Platform Selection wizard Available](images/wpf-installation-selection-wizard-available.png)
	
	If you have multiple products installed in the same version, they will be listed under the **Installed** tab. You can also select which products to uninstall from the same version. Click the Next button.
	
	<em>**Installed**</em>
	
    ![WPF Platform Selection wizard Installed](images/wpf-installation-selection-wizard-installed.png)
	
	I> If the required software for the selected product isn't already installed, the **Additional Software Required** alert will appear. You can, however, continue the installation and install the necessary software later.
	
	**Required Software**
	
	![WPF Installation Additional Software Alert](images/wpf-installation-additional-software.png)
		
	
4.	If previous version(s) for the selected products are installed, the Uninstall previous version wizard will be displayed. You can see the list of previously installed versions for the products you've chosen here. To remove all versions, check the **Uninstall All** checkbox. Click the Next button.

	![WPF Existing Version for install](images/wpf-installation-previous-versions.png)
	
	N> From the 2021 Volume 1 release, Syncfusion has provided option to uninstall the previous versions from 18.1 while installing the new version.
	
	
5.	Pop up screen will be displayed to get the confirmation to uninstall selected previous versions.

	![WPF Existing Version for install](images/wpf-installation-existing-versions.png)
	
	
6. 	The Confirmation Wizard will appear with the list of products to be installed/uninstalled. You can view and modify the list of products that will be installed and uninstalled from this page.

    ![WPF Confirmation for install/uninstall](images/wpf-installation-confirmation.png)
	
	N> By clicking the **Download Size and Installation** Size links, you can determine the approximate size of the download and installation
	

7.  The Configuration Wizard will appear. You can change the Download, Install, and Demos locations from here. You can also change the Additional settings on a product-by-product basis. Click Next to install with the default settings.

    ![WPF Install and samples location for install](images/wpf-installation-samples-location.png)
	
	**Additional settings**
	
    * Select the **Install Demos** check box to install Syncfusion samples, or leave the check box unchecked, if you do not want to install Syncfusion samples
	* Select the **Register Syncfusion Assemblies in GAC** check box to install the latest Syncfusion assemblies in GAC, or clear this check box when you do not want to install the latest assemblies in GAC.
    * Select the **Configure Syncfusion controls in Visual Studio** check box to configure the Syncfusion controls in the Visual Studio toolbox, or clear this check box when you do not want to configure the Syncfusion controls in the Visual Studio toolbox during installation. Note that you must also select the Register Syncfusion assemblies in GAC check box when you select this check box.
    * Select the **Configure Syncfusion Extensions controls in Visual Studio** checkbox to configure the Syncfusion Extensions in Visual Studio or clear this check box when you do not want to configure the Syncfusion Extensions in Visual Studio.
    * Check the **Create Desktop Shortcut** checkbox to add a desktop shortcut for Syncfusion Control Panel
    * Check the **Create Start Menu Shortcut** checkbox to add a shortcut to the start menu for Syncfusion Control Panel



8.  After reading the License Terms and Conditions, check the **I agree to the License Terms and Privacy Policy** check box. Click the Next button.

9.  The login wizard will appear. You must enter your Syncfusion email address and password. If you do not already have a Syncfusion account, you can create one by clicking on **Create an Account**. If you have forgotten your password, click **Forgot Password** to create a new one. Click the Install button. 

    ![WPF Login wizard install](images/wpf-installation-loging-wizard.png)
	
	I> The products you have chosen will be installed based on your Syncfusion License (Trial or Licensed).

10. The download and installation\uninstallation progress will be displayed as shown below.

    ![WPF Download and Installation progress install](images/wpf-installation-download-process.png)

11. When the installation is finished, the **Summary** wizard will appear. Here you can see the list of products that have been installed successfully and those that have failed. To close the Summary wizard, click Finish. 

    ![WPF Installation Summary](images/wpf-installation-summary.png)
	
	* To open the Syncfusion Control Panel, click **Launch Control Panel**.

12. After installation, there will be two Syncfusion control panel entries, as shown below. The Essential Studio entry will manage all Syncfusion products installed in the same version, while the Product entry will only uninstall the specific product setup.

    ![WPF Installation Control Panel](images/wpf-installation-control-panel.png)
	
	
	
## Uninstallation

Syncfusion WPF installer can be uninstalled in two ways.

   * Uninstall the WPF using the Syncfusion WPF web installer
   * Uninstall the WPF from Windows Control Panel

Follow either one of the option below to uninstall Syncfusion Essential Studio WPF installer.
  
**Option 1: Uninstall the WPF using the Syncfusion WPF web installer**

Syncfusion provides the option to uninstall products of the same version directly from the Web Installer application. Select the products to be uninstalled from the list, and Web Installer will uninstall them one by one.
	
   ![WPF Platform Selection wizard Installed](images/wpf-installation-selection-wizard-installed.png)
	
**Option 2: Uninstall the WPF from Windows Control Panel**  
	
You can uninstall all the installed products by selecting the **Syncfusion Essential Studio {version}** entry (element 1 in the below screenshot) from the Windows control panel, or you can uninstall WPF alone by selecting the **Syncfusion Essential Studio for WPF {version}** entry (element 2 in the below screenshot) from the Windows control panel.

![WPF Installation Control Panel](images/wpf-installed-products.png)
	
N> If the **Syncfusion Essential Studio for WPF {version}** entry is selected from the Windows control panel, the Syncfusion Essential Studio WPF alone will be removed and the below default MSI uninstallation window will be displayed.	

1. The Syncfusion WPF Web Installer's welcome wizard will be displayed. Click the Next button

    ![WPF Installation Welcome wizard uninstall](images/wpf-installation-loging-wizard.png)

2.  The Platform Selection Wizard will appear. From the **Installed** tab, select the products to be uninstalled. To select all products, check the **Uninstall All** checkbox. Click the Next button.
    
	<em>**Installed**</em>
	
	![WPF Platform Selection wizard Installed](images/wpf-installation-selection-wizard-installed.png)
	
	You can also select the products to be installed from the **Available** tab.Click the Next button.
	
	<em>**Available**</em>
	
	![WPF Platform Selection wizard Available](images/wpf-installation-wizard-available.png)
	
3.  If any other products selected for installation, Uninstall previous version wizard will be displayed with previous version(s) installed for the selected products. Here you can view the list of installed previous versions for the selected products. Select **Uninstall All** checkbox to select all the versions. Click Next.

	![Existing Version for install](images/wpf-uninstall-previous-version.png)
	
4.	Pop up screen will be displayed to get the confirmation to uninstall selected previous versions.

	![Existing Version for install](images/wpf-installation-samples-location.png)	
	
5.  The Confirmation Wizard will appear with the list of products to be installed/uninstalled. Here you can view and modify the list of products that will be installed/uninstalled.

    ![Confirmation for install/uninstall](images/wpf-installation-existing-version.png)
	
	N> By clicking the **Download Size and Installation** Size links, you can determine the approximate size of the download and installation
	
6.	The Configuration Wizard will appear. You can change the Download, Install, and Demos locations from here. You can also change the Additional settings on a product-by-product basis. Click Next to install with the default settings.

    ![Install and samples location install/uninstall](images/wpf-installation-samples.png)
	
7.	After reading the License Terms and Conditions, check the **I agree to the License Terms and Privacy Policy** check box. Click the Next button.

8.	The login wizard will appear. You must enter your Syncfusion email address and password. If you do not already have a Syncfusion account, you can create one by clicking on **Create an Account**. If you have forgotten your password, click **Forgot Password** to create a new one. Click the Install button.

    ![Login wizard install/uninstall](images/wpf-installation-loging-wizard.png)
	
	I> The products you have chosen will be installed based on your Syncfusion License (Trial or Licensed).

9.	The download, installation, and uninstallation progresses will be shown.

    ![Download and Installation progress install/uninstall](images/wpf-installation-progress.png)

10.	When the installation is finished, the **Summary** wizard will appear. Here you can see the list of products that have been successfully and unsuccessfully installed/uninstalled. To close the Summary wizard, click Finish.

    ![WPF Summary install/uninstall](images/wpf-installation-summary-wizard.png)
	
	* To open the Syncfusion Control Panel, click **Launch Control Panel**.

