---
layout: post
title: WPF Applications using .NET Core and WPF Controls | Syncfusion
description: Learn here about how to creating the WPF Applications using .NET Core and the Syncfusion WPF Controls.
platform: wpf
control: .NET Core
documentation: ug
---

# Getting started with .NET Core

Syncfusion Essential Studio for WPF ships .NET Core assemblies for building WPF .NET Core applications using Syncfusion Controls. This section explains how to create the project in .NET Core application and using syncfusion WPF controls.

N> All Syncfusion WPF controls supports .NET Core except the controls labeled as `classic`.

## Version Compatibility

Below table represents the supported Syncfusion Essential Studio version for .NET Core versions.

<table>
<tr>
<th>Syncfusion Version<br/></th>
<th>.NET Core 3.1<br/></th>
<th>.NET 5.0<br/></th>
<th>.NET 6.0 & above<br/></th>
</tr>

<tr>
<td>Earlier Version<br/></td>
<td>No<br/></td>
<td>No<br/></td>
<td>No<br/></td>
</tr>

<tr>
<td>
From 17.2 (2019 Vol2) <br/></td>
<td>Yes<br/></td>
<td>No<br/></td>
<td>No<br/></td>
</tr>

<tr>
<td>
From 18.4 (2020 Vol4) <br/></td>
<td>Yes<br/></td>
<td>Yes<br/></td>
<td>No<br/></td>
</tr>

<tr>
<td>
From 20.4 (2022 Vol4) <br/></td>
<td>No<br/></td>
<td>No<br/></td>
<td>Yes<br/></td>
</tr>

</table>

N> Dedicated assemblies are not included for .NET 7.0 and higher versions. Instead, .NET 6.0 assemblies can be used.

## Adding Reference

You can add the Syncfusion assembly references in one of the following ways.

* NuGet
* Adding assembly references from installed location

### NuGet

Refer [control dependencies](https://help.syncfusion.com/wpf/control-dependencies) section to know control and its NuGet to use in the application. After that, add the required NuGet as reference and then you can use the control from ToolBox. The ToolBox will show a list of available controls once you have installed the NuGet package.

Refer [NuGet package](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) section to find more details about installing the NuGet package in your application.

### Adding assembly references from installed location

You can also add the Syncfusion WPF (.NET Core) controls assemblies from the `precompiledassemblies` folder in the following location.

<table>
<td>.NET 6 or higher</td>
<td>C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\{{ site.releaseversion }}\precompiledassemblies\net6.0</td>
</tr>
</table>

## Creating the project

To create the .NET Core project by using the following ways.

### Create a .NET Core project

**Step 1**: Open Visual Studio 2019 and click **Create a new project**. Here, select **WPF App (.NET Core)** template and click **Next**.

![Create new project for WPF NET Core](NETcore_WPF_images/wpf-netcore-create-project.png)

**Step 2**: Now, you can see **Configure your new project** dialog. Here, fill the necessary details and click **Create**. 

![Configure the project for WPF NETCore](NETcore_WPF_images/wpf-netcore-configure-project.png)

**Step 3**: Finally, WPF (.NET Core) sample project was created.

![WPF NETCore application](NETcore_WPF_images/wpf-netcore-application.png)

**Step 4**: Now, you can add your controls. To do so, follow the immediate section [Adding controls in WPF application](https://help.syncfusion.com/wpf/dotnet-core-compatibility#adding-controls-in-wpf-net-core-31-or-net-5-application) for more details.

## Adding controls in WPF (.NET Core) application

Let see how to add `ButtonAdv` control in WPF (.NET Core) application using NuGet package or assembly reference.

### Through NuGet Package

In **Solution Explorer**, right-click on **Dependencies** and select **Manage NuGet Packages...**.

![WPF NET Core showing NuGet Packages](NETcore_WPF_images/wpf-netcore-nuget-package.png)

Now, **NuGet Package Manager** window will be opened. Here, select **Browse** and search the required assembly in search box. Select the required assembly and click **Install**.

![WPF NET Core shows NuGet installation](NETcore_WPF_images/wpf-netcore-install-nuget.png)

Now, the required assemblies are added in to the project.

![WPF NET Core showing installed assembly](NETcore_WPF_images/wpf-netcore-assembly.png)

### Through assembly deployment

In **Solution Explorer**, right-click on **Dependencies** and select **Add Reference**.

![NET Core showing assembly](NETcore_WPF_images/NETcore_reference.png)

Now, **Reference Manager** dialog will be opened. Here click **Browse** and can select the needed assemblies from the location mentioned in below note section. On selecting necessary assemblies, click **Add** and then click **OK**. Now, required assemblies are added in to the project, like in the below screenshot.

N> You can get Syncfusion WPF (.NET Core) controls assemblies from `netcoreapp3.1` or `net 5.0` folder in the following location - C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\{{ site.releaseversion }}\precompiledassemblies

![NET Core showing assembly](NETcore_WPF_images/NETcore_assembly.jpeg)

### Adding ButtonAdv control

You can add `ButtonAdv` control either using code behind or through XAML code in your WPF (.NET Core) application.

a.	Following code explains how to create the **ButtonAdv** control through XAML.

{% tabs %}
{% highlight xaml %}

<Window x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        xmlns:sync="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid Name="ROOT_Grid">
        <sync:ButtonAdv Label="Hello World" Height = "35" Width = "150"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

b.	Following code explains how to create the **ButtonAdv** control through code behind.

{% tabs %}
{% highlight c# %}

using Syncfusion.Windows.Tools.Controls;

ButtonAdv button = new ButtonAdv();
button.Height = 35;
button.width = 150;
button.Label = "Hello World!";
ROOT_Grid.Children.Add(button);

{% endhighlight %}
{% endtabs %}

![WPF ButtonAdv](NETcore_WPF_images/NETcore_controloutput.jpeg)
