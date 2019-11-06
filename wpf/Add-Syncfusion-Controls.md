---
layout: post
title: Steps to add Syncfusion Essential WPF controls
description: Learn about the different ways to add Syncfusion Essential WPF controls to the Visual Studio project.
platform: wpf
control: common
documentation: ug
---
# Add Syncfusion Controls

The Syncfusion WPF controls can be added in a Visual Studio projects by using either of the following ways,

* Through Designer
* Through Code-Behind
* Through Project Template

## Through Designer

Syncfusion UI for WPF are added automatically to the Visual Studio Toolbox during installation. The following steps helps to add required Essential WPF control through drag and drop from Toolbox. For example: **SfTextBoxExt**

1) Create a WPF project in Visual Studio.

2) Find **SfTextBoxExt** by typing the name of the "SfTextBoxExt" in the search box.

![Drag and drop from toolbox](ThroughDragndDrop_images/AddSyncfusionControls_img1.jpeg)

3) Drag **SfTextBoxExt** and drop it in the designer.

![WPF TextBoxExt control](ThroughDragndDrop_images/AddSyncfusionControls_img2.jpeg)

### Through XAML

The following steps helps to add a required Essential WPF Control through XAML Code, for example: **SfTextBoxExt**.

1) Create a WPF project in Visual Studio and refer the following assemblies.

* Syncfusion.SfInput.WPF.dll
* Syncfusion.SfShared.WPF.dll

2) Include an XML namespace for the above assemblies to the Main window.

{% tabs %}

{% highlight XAML %}

<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf" />

{% endhighlight %}

{% endtabs %}

3) Now, Add the SfTextBoxExt control with a required optimal name, using the included namespace.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfTextBoxExt HorizontalAlignment="Center" Name="textBoxExt1" Margin="10" Height ="20" Width="120" Text="SfTextBoxExt" VerticalAlignment="Center"/>

{% endhighlight %}

{% endtabs %}

## Through Code-Behind

Syncfusion UI for WPF can added at runtime using C# / VB. The following steps helps to add required Essential WPF control through code. For example: **SfTextBoxExt**.

1) Create a WPF project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.WPF.dll
* Syncfusion.SfShared.WPF.dll

2) Create an instance of **SfTextBoxExt** using it namespace

{% tabs %}

{% highlight C# %}

Syncfusion.Windows.Controls.Input.SfTextBoxExt textBoxExt1 = new Syncfusion.Windows.Controls.Input.SfTextBoxExt();

{% endhighlight %}

{% highlight VB %}

Dim textBoxExt1 As New Syncfusion.Windows.Controls.Input.SfTextBoxExt()

{% endhighlight %}

{% endtabs %}

3) Set Size and Alignment of the control with require value.
 
{% tabs %}

{% highlight C# %}

textBoxExt1.Height = 20;
textBoxExt1.Width = 120;
textBoxExt1.Margin = new Thickness(10, 10, 10, 10);
textBoxExt1.VerticalAlignment = VerticalAlignment.Center;
textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center;

{% endhighlight %}

{% highlight VB %}

textBoxExt1.Height = 20
textBoxExt1.Width = 120
textBoxExt1.Margin = New Thickness(10, 10, 10, 10)
textBoxExt1.VerticalAlignment = VerticalAlignment.Center
textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center

{% endhighlight %}

{% endtabs %}

4) Add the created instance to the parent window (or the needed layout panels).

{% tabs %}

{% highlight C# %}

// Here this denotes parent Window
this.Content = textBoxExt1; 

{% endhighlight %}

{% highlight VB %}

' Here this denotes parent Window
Me.Content = textBoxExt1

{% endhighlight %}

{% endtabs %}

![WPF TextBoxExt control](ThroughDragndDrop_images/AddSyncfusionControls_img3.jpeg)

## Through Project Template

Syncfusion provides the Visual Studio Project Templates for the Syncfusion WPF platform to create Syncfusion WPF Application. 

I> The Syncfusion WPF templates are available from v16.1.0.24. 

### Create Syncfusion WPF Project 

The following steps direct you to create the Syncfusion WPF project through the Visual Studio Project Template. 

1) To create a Syncfusion WPF project, choose New Project-> Syncfusion->Windows->Syncfusion WPF Application from Visual Studio

![Create WPF application](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-1.png)

2) Name the Project, choose the destination location when required and set the Framework of the project, then click OK.  

N> Minimum target Framework is 4.0 for Syncfusion WPF project templates. 

3) Choose the options to configure the Syncfusion WPF Application by using the following Project Configuration Wizard.  
  
![WPF Project configuration wizard](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-2.png)
                                                     
### Project configurations: 

**Language:** Select the language, either C# or VB. 

![Different language shows in WPF project](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-3.png)

**Choose Theme:** Choose the required theme. 

![Visual studio theme of WPF](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-4.png)

**Assemblies From:** Choose the assembly location from where it is going to be added to the project. 

![Choosing assembly location for WPF project](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-5.png)

**Select Control:** Choose the control based on your need. 

![Select the WPF Control](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-6.png)
      
4) Once the Project Configuration Wizard is done, the Syncfusion WPF project is created with required references and XAML. 

![Added assemblies for WPF control](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-7.png)

![Shows project folder for added control](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-8.png)

5) Then, Syncfusion licensing registration required message box will be shown as follow, if you are installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Please navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key) which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.

![Shows syncfusion license registration message](Add-Syncfusion-Control_images\Syncfusion-Project-Template-Gallery-9.png)