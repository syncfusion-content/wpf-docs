---
layout: post
title: Getting Started with WPF Wizard Control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF Wizard control, its elements and more.
platform: wpf
control: Wizard
documentation: ug
---

# Getting Started with WPF Wizard Control

This section gives a quick overview for working with the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html).

## Highlighting features

You can find some important features of [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) below.

* WizardControl contains the [WizardPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardPage.html), which is used to add multiple pages.
* Each wizard page provides Next, Back, Finish, Cancel, and Help buttons for navigation between the wizard pages.
* Supports customization of the appearance of both WizardControl and WizardPage.

## Assembly deployment
Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#wizard) section to get the list of assemblies or the NuGet package that need to be added as a reference to use the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) control in any application.

**NuGet package:** `Syncfusion.Tools.Wpf`

You can find more details about installing the NuGet package in a WPF application in the following link:
[How to install nuget packages](https://help.syncfusion.com/wpf/installation/install-nuget-packages)

## Creating Application with WizardControl
In this walkthrough, you will create a WPF application that contains the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) control.
1. [Creating project](https://help.syncfusion.com/wpf/wizard-control/getting-started#creating-project)
2. [Adding control via designer](https://help.syncfusion.com/wpf/wizard-control/getting-started#adding-control-via-designer)
3. [Adding control manually in XAML](https://help.syncfusion.com/wpf/wizard-control/getting-started#adding-control-manually-in-xaml)
4. [Adding control manually in C#](https://help.syncfusion.com/wpf/wizard-control/getting-started#adding-control-manually-in-c)
5. [Adding multiple pages](https://help.syncfusion.com/wpf/wizard-control/getting-started#adding-multiple-pages)

## Creating project
The following section provides detailed information to create a new WPF project in Visual Studio to display the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html).

## Adding control via designer
The [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) control can be added to the application by dragging it from the Toolbox and dropping it into the designer. The required [assemblies](https://help.syncfusion.com/wpf/control-dependencies#wizard) will be added automatically.

![WPF Wizard Adding control via designer](getting-started_images/wpf-wizard-adding-control-via-designer.png)

## Adding control manually in XAML
To add the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) control manually in XAML, follow these steps:

1. Add the required assembly references to the project:

   * Syncfusion.Shared.WPF
   * Syncfusion.Tools.WPF

2. Import the Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.

3. Declare the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) in the XAML page.

{% capture codesnippet1 %}
{% tabs %}

{% highlight xaml %}

<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WizardControl"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="WizardControl.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:WizardControl Name="wizardControl"/>
    </Grid>
</Window>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

## Adding control manually in C#
To add the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) control manually in C#, follow these steps:

1. Add the required assembly references to the project:

   * Syncfusion.Shared.WPF
   * Syncfusion.Tools.WPF

2. Import the WizardControl namespace **Syncfusion.Windows.Tools.Controls**.

3. Create a WizardControl instance and add it to the page.

{% capture codesnippet2 %}
{% tabs %}

{% highlight c# %}

using System.Windows;
using System.Windows.Controls;
using Syncfusion.Windows.Tools.Controls;
namespace WizardControl
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            WizardControl wizardControl = new WizardControl();
            this.Content = wizardControl;
        }
    }
}
{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

![WPF Wizard Adding Control Manually](getting-started_images/wpf-wizard-adding-control-manually.jpeg)

## Adding multiple pages

You can add multiple pages in the [WizardControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardControl.html) using the [WizardPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.WizardPage.html) control. The Cancel, Back, Next, and Finish buttons are enabled and disabled automatically based on the current visible wizard page.

{% tabs %}

{% highlight xaml %}

<syncfusion:WizardControl Name="wizardControl">
    <syncfusion:WizardPage Name="wizardPage1"/>
    <syncfusion:WizardPage Name="wizardPage2"/>
    <syncfusion:WizardPage Name="wizardPage3"/>
</syncfusion:WizardControl>

{% endhighlight %}

{% highlight c# %}

WizardControl wizardControl = new WizardControl();
WizardPage wizardPage1 = new WizardPage();
WizardPage wizardPage2 = new WizardPage();
WizardPage wizardPage3 = new WizardPage();

wizardControl.Items.Add(wizardPage1);
wizardControl.Items.Add(wizardPage2);
wizardControl.Items.Add(wizardPage3);

{% endhighlight %}

{% endtabs %}

![WPF Wizard Control Adding Multiple Pages](getting-started_images/wpf-wizard-adding-multiple-pages.png)

## Theme

The WizardControl supports various built-in themes. Refer to the following links to apply themes to the WizardControl:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)

  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

   ![Setting theme to WPF Wizard Control](getting-started_images/wpf-wizard-control-theme.png)