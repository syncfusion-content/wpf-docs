--
layout: post
title: Installation and Deployment
description: common supports
platform: wpf
control: Installation and Deployment
documentation: ug
---
## Deployment

### Local Copy

Local copy is supported by the Syncfusion assembly reference in the Solution Explorer. It can be achieved by setting its Copy Local property of the reference to True, so that Syncfusion assemblies are copied to the Release/Bin, Debug/Bin folders. And this deployment consists of copying the exe, dlls, xmls files to the client machines that are similar to manual copy.

![](Deployment_images/Deployment_img1.jpeg)


### GAC

Through Syncfusion installer, Syncfusion assemblies are installed in the GAC of the the developer machines. Also Syncfusion [Assembly Manager](C:\Users\Selvaganapathy\Desktop\assembly manager# "") helps you Add or Remove the Syncfusion assemblies to or from GAC.

### Clickonce Deployment

While processing [ClickOnce](https://msdn.microsoft.com/en-us/library/ms996413.aspx# "") the deployment for publishing an application with Syncfusion WPF component, change the Publish Status option of the Syncfusion Assemblies as “Include”.

![](Deployment_images/Deployment_img2.jpeg)


__Selecting__ __Application__ __Files__ __for__ __changing__ __the__ __status__

![](Deployment_images/Deployment_img3.jpeg)


__Publish__ __Status__ __option__ __changed__ __as__ __Include__

#### ClickOnce signing process

Before publishing a ClickOnce application, ensure whether it is fully trusted, so that you can authenticate the information. The following steps are used for signing a ClickOnce application.

Signing ClickOnce involves two steps,

* Signing the application manifest
* Signing application executable
##### Signing the manifest


Navigate to project properties and select Signing tab. In the tab check “Sign the ClickOnce manifests” and select “Select From File” option and sign the application with the attached .pfx file.

![](Deployment_images/Deployment_img4.jpeg)


##### ClickOnce signing

In the Publish tab, click “Options” and in the publish options dialog check “Use application manifest for trust information” under Manifest as in the following screenshot.

![](Deployment_images/Deployment_img5.jpeg)


##### Publish options dialog box

Note: Before publishing, install the attached certificate in your machine and also follow step 2. Follow the following steps for installing certificate in your machine.

1. __Press__ __Windows__ __+__ __R__ __and__ __type__ __“____certmgr____.____msc____”__ __and__ __press__ __enter__ __that__ __opens__ __certificate__ __manager____.__
2. __Right__ __click__ __the__ __“____Trusted__ __Root__ __certification__ __Authorities____”__ __and__ __navigate__ __to__ __All__ __Tasks__ __->__ __Import____.__ __Now__ __import__ __the__ .pfx __to__ __“____Trusted__ __Root__ __certification__ __Authorities____”.__ __It__ __displays__ __a__ __warning__ __for__ __first__ __time____.__ __Press__ __Yes__ __to__ __continue__ __the__ __importing____.__
#### Signing exe


The above process signs only deployment manifest. To sign the application executable, refer to the following steps.

You can sign the application executable by using the Post-build command and use the signtool.exe as in the following command.

"C:\Program Files (x86)\Microsoft SDKs\Windows\v7.1A\Bin\signtool.exe" sign /f "$(ProjectDir)syncfusion.pfx" /p Coolcomp299 /v "$(ProjectDir)obj\x86\$(ConfigurationName)\DataGridSampleBrowser.exe"

Note: Now, sign the exe inside obj folder and Syncfusion.pfx file placed inside Project directory.

