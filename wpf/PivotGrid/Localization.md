---
layout: post
title: Localization of string resource
description: Localization of string resource
platform: wpf
control: Pivot grid
documentation: ug
---

# Localization of String Resource

Localization deals with customizing data and resources for specific culture or language. The built-in localization and globalization mechanism in WPF allows you to localize any string resource used by PivotGrid controls. Localization can be done in below ways.

* Localization using Resource File
* Localization using Satellite Assembly

## Localization using Resource File

We need to create and place the resource files in a separate location inside in the user application. Then we can access to the culture specific resources from the current application assembly.

For this, first create a resource file for our PivotGrid control and translate the strings to your culture. Once it is translated, you might use the resources in your projects by setting corresponding culture in your application.

Please refer the below code sample.

{% highlight C# %}

public MainWindow() {
    //Set the current thread culture to load the localization resource file.
    System.Threading.Thread.CurrentThread.CurrentUICulture = new System.Globalization.CultureInfo("ar-AE");
    InitializeComponent();
    if (System.Globalization.CultureInfo.CurrentUICulture.ToString() == "ar-AE") {
        this.FlowDirection = System.Windows.FlowDirection.RightToLeft;
    }
}

{% endhighlight %}

## Localization using Satellite Assembly

Here, the resource file should be embedded in a satellite assembly and can be used in the application for applying localization.

The following steps illustrates the process of creating Satellite Assembly:

Open the **Visual Studio Command prompt** and navigate to the folder which contains the **.resx* file in your application and generate the **.resources* file which needs to be embedded in the satellite assembly by entering the below command in command prompt.

**system drive> Resgen MyResource.ar-AE.resx**

After executing the above command, a **.resources* file will be generated on the same folder. Then enter the below command in command prompt.

**system drive> AL.exe**

Then create the satellite assembly for your culture by embedding the **.resources* file by using the following command.

**system drive> al /target:lib /embed:MyResource.ar-AE.resources /culture:ar-AE /out:MyApp.resources.dll**

Now, MyResource.ar-AE.resources is the resource file embedded in the MyApp.resources.dll.

After executing the above command, the satellite assembly will be generated in the same Folder. Finally, place the assembly in the following path:
**{Location of the application}\bin\debug\ar-AE\MayAppName.resources.dll**

N> Make sure that the name of satellite assembly should be in the format *MyAppName.resources.dll* and the name of the **.resx* file should be like Syncfusion.PivotAnalysis.Wpf.ar-AE.resx (Arabic). If the name of dll’s differs from your application name, then localization won't work.

![](Localization-Images/PivotGrid Shows localization behaviour.png)