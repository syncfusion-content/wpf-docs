---
layout: post
title: WPF Applications using .NET Core and WPF Controls | Syncfusion
description: Learn here about how to creating the WPF Applications using .NET Core and the Syncfusion WPF Controls.
platform: wpf
control: .NET Core
documentation: ug
---

# WPF Applications using .NET Core and Syncfusion WPF Controls

Syncfusion Essential Studio for WPF ships .NET core and .NET 5.0 assemblies for building WPF .NET Core applications using Syncfusion Controls. This section explains how to create the project in .NET Core application and using syncfusion WPF controls.

N> All Syncfusion WPF controls supports .NET Core and .NET 5.0 Framework except the controls labeled as `classic`.

## Adding Reference

you can add the Syncfusion assembly references in one of the following ways.

* NuGet
* Adding assembly references from installed location

### NuGet

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies) section to find out what NuGet assemblies to use a particular control in your application. After that, add the required NuGet as reference and then you can use the control from ToolBox. The ToolBox will show a list of available controls once you have installed the NuGet package.

[Click here](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) to find more details about installing the NuGet package in your application.

### Adding assembly references from installed location

You can also add the Syncfusion WPF (.NET Core and .NET 5.0) controls assemblies from `precompiledassemblies` folder in the following location.

<table>
<tr>
<td>.NET Core 3.1</td>
<td>C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\x.x.x.x\precompiledassemblies\netcoreapp3.1</td>
</tr>
<tr>
<td>.NET 5.0</td>
<td>C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\x.x.x.x\precompiledassemblies\net5.0</td>
</tr>
</table>

## Creating the project

You can create the .NET Core or .NET 5.0 project by using the following ways.

### Create a .NET Core project

**Step 1**: Open Visual Studio 2019 and click **Create a new project**. Here, select **WPF App (.NET Core)** template and click **Next**.

![Create new project for WPF NET Core](NETcore_WPF_images/wpf-netcore-create-project.png)

**Step 2**: Now, you can see **Configure your new project** dialog. Here, fill the necessary details and click **Create**. 

![Configure the project for WPF NETCore](NETcore_WPF_images/wpf-netcore-configure-project.png)

**Step 3**: Finally, WPF (.NET Core) sample project is created.

![WPF NETCore application](NETcore_WPF_images/wpf-netcore-application.png)

**Step 4**: Now, you can add your controls. To do so, follow the immediate section [Adding controls in WPF (.NET Core) application](https://help.syncfusion.com/wpf/dotnet-core-compatibility#adding-controls-in-wpf-net-core-application) for more details. 

### Create a .NET 5.0 project

**Step 1**: Repeat the first three steps of Create a .NET Core project section.

**Step 2**: In Solution Explorer, right-click on project and select `Properties`. Now, the project window dialog will be opened.

**Step 3**: Select the **.NET 5.0** in Target Framework.

![Change the target framework for WPF NET 5.0](NETcore_WPF_images/wpf-netcore-framework.png)

**Step 4**: Now, the .NET 5.0 application was created.

**Step 5**: Now, you can add your controls. To do so, follow the immediate section [Adding controls in WPF (.NET 5.0) application](https://help.syncfusion.com/wpf/dotnet-core-compatibility#adding-controls-in-wpf-net-core-application) for more details. 

## Adding controls in WPF (.NET Core or .NET 5.0) application

The below section explains how to add controls in WPF (.NET Core or .NET 5.0) application.

### Through assembly deployment

In **Solution Explorer**, right-click on **Dependencies** and select **Add Reference**.

![NETcore showing assembly](NETcore_WPF_images/NETcore_reference.png)

Now, **Reference Manager** dialog will be opened. Here click **Browse** and can select the needed assemblies from the location mentioned in below note section. On selecting necessary assemblies, click **Add** and then click **OK**. Now, required assemblies are added in to the project, like in the below screenshot.

N> You can get Syncfusion WPF (.NET Core or .NET 5.0) controls assemblies from `netcoreapp3.1` or `net 5.0` folder in the following location - C:\Program Files (x86)\Syncfusion\Essential Studio\WPF\x.x.x.x\precompiledassemblies

![NETcore showing assembly](NETcore_WPF_images/NETcore_assembly.jpeg)

### Through NuGet Package

[Click here](https://help.syncfusion.com/wpf/nuget-packages) to find more details regarding how to install the NuGet packages in WPF application.


### Example: Adding ButtonAdv control

We are now going to see a demo on how to add **ButtonAdv** control in WPF (.NET Core or .NET 5.0) application.

**Step 1**:	Add the following dependent assembly for the inclusion of **ButtonAdv** control.

•	Syncfusion.Shared.WPF

**Step 2**:	We can add button either using code behind or through XAML code. Both methods are explained below.

a.	Following code explains how to declare the **ButtonAdv** control through XAML.

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

b.	Following code explains how to declare the **ButtonAdv** control through code.

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

**Step 3**: Run the application.

![NETcore showing control output](NETcore_WPF_images/NETcore_controloutput.jpeg)