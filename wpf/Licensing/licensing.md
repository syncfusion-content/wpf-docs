---
layout: post
title: About Essential Studio UWP Licensing | Syncfusion
description: Learn here about Syncfusion Essential Studio UWP license key, how to generate the license key, how to register the license key, and more details.
platform: UWP
control: Essential Studio
documentation: ug
---


# Syncfusion Licensing in UWP

We have introduced a new licensing system starting with version 16.2.0.x release of Essential Studio. These modifications apply to all evaluators and only to paid customers who use NuGet packages from [nuget.org](https://www.nuget.org/). Starting with v16.2.0.x, if you use the evaluation installer or the NuGet feed to reference Syncfusion assemblies, you must also include the corresponding platform and version license key in your projects.

Please note that this license key is different from the installer unlock key that you might have used in the past and needs to be separately generated from Syncfusion website. Refer [this](https://www.syncfusion.com/kb/8950/difference-between-the-unlock-key-and-licensing-key) KB article to know more about difference between the Syncfusion Unlock Key and the Syncfusion License Key.

Following licensing error will be shown if the license key is not registered in your projects, while using assemblies from evaluation installer or from the nuget.org.

<div id="license">

This application was built using a trial version of Syncfusion Essential Studio. Please include a valid license to permanently remove this license validation message. You can also obtain a free 30 day evaluation license to temporarily remove this message during the evaluation period. Please refer to this <a href="/common/essential-studio/licensing/license-key">help topic</a> for more information 

</div>

## License Key Generation

License keys for WPF can be generated from the [License & Downloads](https://syncfusion.com/account/downloads) or [Trail & Downloads](https://www.syncfusion.com/account/manage-trials/downloads) section from your Syncfusion account. 

![Get License Key](licensing-images/generate-license.png)

Syncfusion license keys are **version and platform specific**, kindly follow the [KB](https://www.syncfusion.com/kb/8976/how-to-generate-license-key-for-licensed-products) to generate the license key for required version and platform. Also, refer to the [KB](https://www.syncfusion.com/kb/8951/which-version-syncfusion-license-key-should-i-use-in-my-application) to know which version Syncfusion license key should use in the application.

## License Key Registration

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.

You can register the license key in App constructor of **App.xaml.cs** in C#. If App constructor not available in **App.xaml.cs**, create the "App()" constructor in **App.xaml.cs** and register the license key inside the constructor. In Visual Basic, register the license code in **App.xaml.vb**.

{% tabs %}
{% highlight c# %}
public partial class App : Application
{
	public App()
	{
		//Register Syncfusion license
		Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	}	
} 
{% endhighlight %}

{% highlight vb %}
Private Sub New()
	'Register Syncfusion License
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
End Sub
{% endhighlight %}

{% endtabs %}