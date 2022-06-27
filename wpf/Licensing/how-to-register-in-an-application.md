---
layout: post
title: Overview of Syncfusion license registration - Syncfusion
description: Learn here about how to register Syncfusion WPF license key for WPF application for license validation.
platform: WPF
control: Essential Studio
documentation: ug
---

# Register Syncfusion License key in WPF application

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> * Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.
* Syncfusion license validation is done offline during application execution and does not require internet access.  Apps registered with a Syncfusion license key can be deployed on any system that does not have an internet connection.

### WPF 

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