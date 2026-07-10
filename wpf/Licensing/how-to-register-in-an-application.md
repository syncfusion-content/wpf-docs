---
layout: post
title: Overview of Syncfusion license registration - Syncfusion
description: Learn how to register the Syncfusion license key in a WPF application for license validation.
platform: wpf
control: Essential Studio
documentation: ug
---

# Register Syncfusion license key in a WPF application

To generate or obtain a license key, see [License key generation](https://www.syncfusion.com/account/licensing).

N> **Prerequisites:** Install the Syncfusion WPF NuGet package (for example, `Syncfusion.Licensing.Wpf`, or the platform-specific control package that depends on it) from the Syncfusion NuGet feed, and ensure `Syncfusion.Licensing.dll` is referenced in your project. Licensing support is available in Syncfusion Essential Studio version 16.1.0.24 and later.

The generated license key is a string that must be registered before any Syncfusion control is initialized. The `Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense` method takes the license-key string as its only parameter and returns `void`. The following code registers the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes. Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered (see the package name in the Prerequisites note above).
* Syncfusion license validation is done offline during application execution and does not require internet access. Apps registered with a Syncfusion license key can be deployed on any system that does not have an internet connection.
* If the license key is missing or invalid at runtime, a license dialog or warning will appear. For troubleshooting common registration failures, refer to the [Licensing FAQ](https://help.syncfusion.com/wpf/licensing/licensing-faq).

I> Syncfusion license keys can be validated during the Continuous Integration (CI) processes to ensure proper licensing and prevent licensing errors during deployment. Refer to the [CI License Validation](https://help.syncfusion.com/wpf/licensing/licensing-faq/ci-license-validation) section for detailed instructions on how to implement it.

### Register in the App constructor

You can register the license key in the **App** constructor in **App.xaml.cs** (C#). If an **App** constructor is not available in **App.xaml.cs**, create an `App()` constructor in **App.xaml.cs** and register the license key inside it. In Visual Basic, register the license key in **App.xaml.vb**.

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
	'Register Syncfusion license key
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
End Sub
{% endhighlight %}

{% endtabs %}