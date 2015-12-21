---
layout: post
title: 13427-Localization
description: 1.3.4.27 localization
platform: wpf
control: PivotGridControl
documentation: ug
---

# Localization And Globalization

Localization deals with customizing data and resources for specific culture or locale or language. The built-in localization and globalization mechanism in WPF allows you to localize any string resource used by PivotGrid controls. Localization can be done in below ways.

* Localization using Resource file
* Localization using Satellite assembly

## Localization using Resource file

We need to keep the resource files at a separate location and include in the project and can access to the culture specific resources from the current application assembly.

For this first create a resource file for our PivotGrid control and translate the strings to your culture. Once translated you might use the resources in your projects and set corresponding culture for your application. 

Please refer the below code snippet.

{% highlight C# %}

public MainWindow() {
    //  Set the current thread culture to load the localization resource file added .    
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar-AE");
    InitializeComponent();
    if (System.Globalization.CultureInfo.CurrentUICulture.ToString() == "ar-AE") {
        this.FlowDirection = System.Windows.FlowDirection.RightToLeft;
    }
}

{% endhighlight %}

## Localization using Satellite Assembly

Here, the resource file should needs to be embedded in a satellite assembly and can be used in the application for applying localization. 

The following steps illustrating the process of creating Satellite Assembly:

Open the **Visual Studio Command prompt** and navigate the folder which contains the **.resx* file of your project folder and generate the *.resources file which needs to be embedded in the satellite assembly by entering the below command in command prompt. 
                            
**SystemDrive> Resgen MyResource.ar-AE.resx**

After executing the above command, a *.resources file will be generated on the same folder. Then enter the below command in command prompt.

**SystemDrive> AL.exe**
 
Then create the satellite assembly for the your culture by embedding the *.resources file by using the following command

**SystemDrive> al /target:lib /embed:MyResource.ar-AE.resources /culture:ar-AE /out:MyApp.resources.dll**

Now, MyResource.ar-AE.resources is the Resource file embedded in the MyApp.resources.dll.

After executing the above command the satellite assembly will be generated in the same Folder. Finally, place the assembly at the following path:
    
**{Location of Program}\bin\debug\ar-AE(Arabic Culture)\MayAppName.resources.dll**

Note> Make sure that the name of satellite assembly should be in the format *MyAppName.resources.dll* and the name of the *.resx file should be Syncfusion.PivotAnalysis.Wpf.ar-AE.resx* (Arabic). If the name of dll’s differs from your application name Localization will not work.


![](Localization-Images/PivotGrid Shows localization behaviour.png)
	