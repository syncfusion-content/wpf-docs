---
layout: post
title: How to register license in WPF | SynSyncfusion®cfusion
description: Learn how to register Syncfusion® WPF license keys in your WPF applications for proper license validation and control initialization.
platform: wpf
control: Essential Studio
documentation: ug
---

# How to register license in WPF

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

**Registering a single license key**

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

**Registering multiple license keys**

You can register multiple license keys using either a comma (,) or a semicolon (;) as the separator between keys.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY_1,YOUR LICENSE KEY_2,...");
{% endhighlight %}
{% endtabs %}

or

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY_1;YOUR LICENSE KEY_2;...");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes. Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered (see the package name in the Prerequisites note above).
* Syncfusion license validation is done offline during application execution and does not require internet access. Apps registered with a Syncfusion license key can be deployed on any system that does not have an internet connection.

I> Syncfusion license keys can be validated during the Continuous Integration (CI) processes to ensure proper licensing and prevent licensing errors during deployment. Refer to the [CI License Validation](https://help.syncfusion.com/wpf/licensing/licensing-faq/ci-license-validation) section for detailed instructions on how to implement it.

## WPF

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