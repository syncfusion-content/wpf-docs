---
layout: post
title: Guide to run online and offline samples from WPF Studio | Syncfusion
description: Learn how to run the online samples and offline samples of Syncfusion Essential Studio WPF controls and components.
platform: wpf
control: Featured Samples
documentation: ug
---

# Featured Samples for Syncfusion<sup>&reg;</sup> WPF Controls

## Syncfusion<sup>&reg;</sup> WPF Controls Panel

To explore Syncfusion<sup>&reg;</sup> WPF controls and components, Open `Syncfusion<sup>&reg;</sup> WPF Controls Panel` by searching it from start and open. 

![WPF Control Panel Search](Guidetorunthesamples_images/wpf-control-panel-search.png)

In another way, open the Control Panel from the following installed location.

C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion WPF Control Panel.exe

N> In above section, latest Essential Studio<sup>&reg;</sup> version details has been provided. You can refer installed Essential Studio<sup>&reg;</sup> version instead of mentioned version.

![Syncfusion WPF Controls Panel](Guidetorunthesamples_images/syncfusion-wpf-controls-panel.PNG)

## WPF Sample Browser

To explore the locally installed demos, click `Run Local Demos` and select either `.NET Core` or `.NET FrameWork`, which will open `WPF Sample Browser`.

![Syncfusion WPF Sample Browser](Guidetorunthesamples_images/syncfusion-wpf-sample-browser.PNG)

## Offline Samples

The Offline samples are available in the following installed location where you can make changes and further exploration of controls.

C:\Users\Public\Documents\Syncfusion\WPF\{{ site.releaseversion }}\

The offline samples can also be explored directly from the `Syncfusion<sup>&reg;</sup> WPF Sample Browser` and opened in Visual Studio by running the required sample and selecting the `Open source code in visual studio`.

![Exploring Syncfusion WPF Samples from Syncfusion WPF Sample Browser](Guidetorunthesamples_images/Exploring-syncfusion-wpf-Showcase-sample-from-SB.PNG)

### Offline showcase samples

To explore any individual showcase sample from the `Syncfusion<sup>&reg;</sup> WPF Sample Browser`, Click `Explore Demo Source` and navigate to `showcase` folder.

![Exploring Syncfusion WPF Showcase Samples](Guidetorunthesamples_images/Exploring-syncfusion-wpf-Showcase-sample.PNG)

All the sample browser projects are configured as single SDK-style projects that support multiple frameworks: `.NET Framework 4.6.2`, `.NET 8.0`, `.NET 9.0`, and `.NET 10`. 

When you click the `Explore Demo Source` button, the `net10.0-windows` entry will be automatically removed from the targets file if .NET 10 is not installed on your machine, preventing any compilation errors. 

To use the `.NET 10 framework`, install the required SDK and add `net10.0-windows` to the <TargetFrameworks> tag in the `MultiTargeting.targets` file located at the Samples Location: D:\WPF31.2.9\WPF\31.2.9\SampleBrowser\targets\MultiTargeting.targets as shown in the image below. 

![WPF TargetFrameworks](Guidetorunthesamples_images/TargetFrameworks-wpf.jpg)

If you don’t have other frameworks installed and encounter compilation issues as a result, you can remove the unsupported framework from the <TargetFrameworks> tag in the same file and retain only the available ones to resolve the issue. 

N> To run the individual control demos, please refer the instruction from [Running Individual Control Demos](https://github.com/syncfusion/wpf-demos#running-individual-control-demos). 

## Online Samples

* Download and install `.Net Framework` demos from [Microsoft Store](https://www.microsoft.com/en-us/p/syncfusion-wpf-controls-examples/9n99kdhrff6g?activetab=pivot:overviewtab).

## Download demos from online (Clone from github repository)

You can explore Syncfusion<sup>&reg;</sup> WPF controls using [GitHub WPF demos](https://github.com/syncfusion/wpf-demos), where all wpf demos are configured using `NuGet` to run without installing Syncfusion<sup>&reg;</sup> WPF Studio.

### Download showcase demos from online

You can explore showcase demos from [GitHub WPF demos](https://github.com/syncfusion/wpf-demos/tree/master/showcase).
