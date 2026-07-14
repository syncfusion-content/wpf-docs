---
layout: post
title: Getting started with AI-Powered Text Editor control | Syncfusion®
description: Learn here about getting started with Syncfusion® WPF AI-Powered Text Editor (SfSmartTextEditor) control, its elements and more.
platform: wpf
control: SfSmartTextEditor
documentation: ug
---

# Getting started with WPF Smart Text Editor

This section explains how to add the [WPF SmartTextEditor](https://www.syncfusion.com/wpf-controls/smart-text-editor) control. It covers only the basic features needed to get started with the Syncfusion AI-Powered Text Editor. Follow the steps below to add a WPF AI-Powered Text Editor control to your project.

N> The Smart Text Editor is distributed as part of the `Syncfusion.SfSmartComponents.WPF` package, which provides advanced AI-assisted features to enhance text editing and content management. Ensure your application has the required AI service configuration to enable these features.

## Prerequisites

Before proceeding, ensure the following are set up:

1. Install the **.NET SDK**: [Download .NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0) or later must be installed on your machine.
2. Set up a **WPF development environment** with Visual Studio. Supported Visual Studio versions are listed below. Make sure the **.NET desktop development** workload is installed (this provides the WPF project templates, MSBuild support, and the WPF SDK reference assemblies required by your project):
   - **Visual Studio 2022** (Version 17.13 or later, for example 17.14.7) for **.NET 9** development.
   - **Visual Studio 2026** for **.NET 10** development.
3. **Enable WPF in your project**: for a .NET 9 (or later) console-style or library project, ensure your project file contains `<UseWPF>true</UseWPF>`. The default WPF App template from Visual Studio includes this setting; only add or verify it if you are configuring the project manually. WPF project templates automatically include the necessary WPF targeting pack; if you are building from the command line, install the [Microsoft.WindowsDesktop.App](https://www.nuget.org/packages/Microsoft.WindowsDesktop.App) targeting pack for your target framework. Refer to the official Microsoft WPF setup guide for details specific to your development environment.
4. **Configure an AI service** (required only if you want AI-powered completions; the control also works in offline mode with `UserPhrases`): the example in this walkthrough uses **Azure OpenAI**. Before you begin, create an Azure OpenAI resource in the [Azure portal](https://portal.azure.com/) and note down the following values — you will need them in **Step 5**:
   - **API key** for the Azure OpenAI resource.
   - **Endpoint URL** of the Azure OpenAI resource (for example, `https://<your-resource-name>.openai.azure.com/`).
   - **Deployment name** of the model you intend to use (for example, `gpt-4o-mini` or your custom deployment name). For non-Azure providers (such as OpenAI or other compatible services), use the equivalent endpoint, API key, and model name and refer to that provider's documentation for the corresponding `Microsoft.Extensions.AI` configuration package and parameters.

## Step 1: Create a New WPF Project

1. In Visual Studio, go to **File > New > Project**. In the project template dialog, search for and select the **WPF App** template (C#), *not* "WPF App (.NET Framework)" — the **WPF App** template targets .NET 9 (or later) and is the template required for the `Syncfusion.SfSmartComponents.WPF` package. **WPF App (.NET Framework)** targets the older .NET Framework and is not supported by the SmartComponents WPF package.
2. Name the project and choose a location. Then click **Next**.
3. On the next screen, select **.NET 9.0** (or a later supported version) as the target framework and click **Create**.

## Step 2: Install the Syncfusion<sup>&reg;</sup> WPF SmartComponents NuGet Package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for [Syncfusion.SfSmartComponents.WPF](https://www.nuget.org/packages/Syncfusion.SfSmartComponents.WPF) and install the latest version of the package that supports `SfSmartTextEditor`. The corresponding API reference for the package namespace is available at [Syncfusion.UI.Xaml.SmartComponents](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SmartComponents.html). Refer to the Syncfusion release notes for the version of `Syncfusion.SfSmartComponents.WPF` that first introduced the `SfSmartTextEditor` control.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

N> The NuGet package ID and the assembly name are case-sensitive in some WPF scenarios. After installation, confirm that the `assembly=…` value in your XAML matches the casing of the built assembly under the project's `bin` folder. Refer to the API reference for the exact assembly name.

## Step 3: Adding the control to your application

You can add the `SfSmartTextEditor` control either by dragging it from the Visual Studio **Toolbox** into the Designer, or by declaring it manually in XAML or C#. The required assembly references are added automatically by the Toolbox; for the manual path, you need to add them yourself.

### Option A — Adding the control via the Toolbox (Designer)

1. Build the project after the NuGet package is restored so that `SfSmartTextEditor` appears in the Visual Studio **Toolbox**.
2. Drag the **SfSmartTextEditor** item from the **Toolbox** onto the Designer surface (the **Window** or a containing layout panel such as a `Grid`).
3. The required assembly references and the namespace declaration are added automatically.

### Option B — Adding the control manually in XAML

In order to add the control manually in XAML, do the below steps,

1. Add the below required assembly references to the project,
    * Syncfusion.SfSmartComponents.WPF
2. Import Syncfusion<sup>®</sup> WPF schema **http://schemas.syncfusion.com/wpf** or SfSmartTextEditor control namespace **Syncfusion.UI.Xaml.SmartComponents** in XAML page.
3. Declare SfSmartTextEditor control in XAML page.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        x:Class="WpfApplication1.MainWindow"
        Title="MainWindow" Height="350" Width="525">
    <Grid x:Name="Root_Grid">
        <syncfusion:SfSmartTextEditor  x:Name="smartTextEditor"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

### Adding control manually in C\#

In order to add control manually in C#, do the below steps,

1. Add the below required assembly references to the project,
    * Syncfusion.SfSmartComponents.WPF
2. Import SfSmartTextEditor namespace **Syncfusion.UI.Xaml.SmartComponents** .
3. Create SfSmartTextEditor control instance and add it to the Page.

{% capture codesnippet2 %}
{% tabs %}
{% highlight c# %}
using Syncfusion.UI.Xaml.SmartComponents;
namespace WpfApplication1
{ 
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfSmartTextEditor smartTextEditor = new SfSmartTextEditor();
            Root_Grid.Children.Add(smartTextEditor);
        }
    }
}
{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

## Step 4: Configure user role and phrases for suggestions

Set the writing context and preferred expressions to guide completions:
- **UserRole** (required): Describes who is typing and the intent, shaping the tone and relevance of suggestions.
- **UserPhrases** (optional): A list of reusable statements that reflect your brand or frequent responses. Used for offline suggestions and to bias completions.

{% tabs %}
{% highlight xaml tabtitle="XAML" hl_lines="7 8" %}

<Window
    .....
    xmlns:sys="clr-namespace:System;assembly=mscorlib"
    xmlns:smarttexteditor="clr-namespace:Syncfusion.UI.Xaml.SmartComponents;assembly=Syncfusion.SfSmartComponents.Wpf">

    <smarttexteditor:SfSmartTextEditor
        Placeholder="Type your reply..."
        UserRole="Support engineer responding to customer tickets">
        <smarttexteditor:SfSmartTextEditor.UserPhrases>
            <sys:String>Thanks for reaching out.</sys:String>
            <sys:String>Please share a minimal reproducible sample.</sys:String>
            <sys:String>We’ll update you as soon as we have more details.</sys:String>
        </smarttexteditor:SfSmartTextEditor.UserPhrases>
    </smarttexteditor:SfSmartTextEditor>
</Window>

{% endhighlight %}
{% endtabs %}

N> If no AI inference service is configured, the editor generates offline suggestions from your `UserPhrases`. The `UserRole` and `UserPhrases` properties are part of the control's offline-suggestion API; the supported `UserPhrases` collection type and any default value depend on the installed Syncfusion version. Refer to the API reference for the exact contract.

N> You can complete Steps 1 through 4 to build and run the application with offline suggestions only. To enable AI-powered completions, continue with **Step 5: Register the AI Service** below.

## Step 5: Register the AI Service

To enable AI-powered completions, configure the AI service in the `App.xaml.cs` file. **For production applications, store the API key, endpoint, and deployment name in a secure configuration source (for example, user secrets, environment variables, or Azure Key Vault) and read them at runtime — do not commit them to source control.**

Follow the steps below to set up the AI services:

1.  Open **NuGet Package Manager** and search for the following packages.
2.  Install the **latest versions** of each package that are compatible with the installed `Syncfusion.SfSmartComponents.WPF` version:
    *   **Azure.AI.OpenAI**
    *   **Microsoft.Extensions.AI**
    *   **Microsoft.Extensions.AI.OpenAI**
3.  Open the `App.xaml.cs` file in your project. Configure the AI service inside the `OnStartup` override so that the chat client is registered before the application's main window is shown. Replace the placeholder values for `azureApiKey`, `azureEndpoint`, and `deploymentName` with the values from the Azure OpenAI resource you created in the **Prerequisites** section. For non-Azure providers, use the equivalent `Microsoft.Extensions.AI` provider package and refer to its documentation for the correct configuration parameters.

```csharp
using Azure.AI.OpenAI;
using Microsoft.Extensions.AI;
using Microsoft.Extensions.DependencyInjection;
using Syncfusion.UI.Xaml.SmartComponents;
using System.ClientModel;
using System.Windows;
namespace WpfApplication1
{
    /// <summary>
    /// Interaction logic for App.xaml
    /// </summary>
    public partial class App : Application
    {
        protected override void OnStartup(StartupEventArgs e)
        {
            base.OnStartup(e);
            
            string azureApiKey = "<MENTION-YOUR-KEY>";
            Uri azureEndpoint = new Uri("<MENTION-YOUR-URL>");
            string deploymentName = "<MENTION-YOUR-DEPLOYMENT-NAME>";

            AzureOpenAIClient azureClient = new AzureOpenAIClient(azureEndpoint, new ApiKeyCredential(azureApiKey));
            IChatClient azureChatClient = azureClient.GetChatClient(deploymentName).AsIChatClient();
            SyncfusionAIExtension.Services.AddSingleton<IChatClient>(azureChatClient);
            SyncfusionAIExtension.ConfigureSyncfusionAIServices();
        }
    }
}
```

## Step 6: Running the Application

Press **F5** to build and run the application. Once compiled, the WPF Smart Text Editor will appear, and AI features will be available after configuration.

Here is the result of the previous codes,

![Getting Started in WPF Smart Text Editor.](images/getting-started/wpf-smarttexteditor-getting-started.gif)

N> You can refer to our [WPF Smart Text Editor](https://www.syncfusion.com/wpf-controls/smart-text-editor) feature tour page for its groundbreaking feature representations.

## Troubleshooting

The following are common issues when setting up the WPF Smart Text Editor. Refer to the AI service provider's documentation for full troubleshooting guidance.

- **Suggestions are not generated from the AI service**:
  - Verify that the AI service is reachable from the application (network, firewall, or proxy settings).
  - Confirm that the API key, endpoint, and deployment name are valid and have the correct permissions.
  - Check the application output for AI service errors (401/403 indicate authentication or authorization failures; 429 indicates rate limiting).
  - Ensure the `IChatClient` is registered with `SyncfusionAIExtension.Services` before `ConfigureSyncfusionAIServices()` is called.
- **Offline-only behavior is used unexpectedly**:
  - This indicates that the AI service is not configured, or the registration in `App.xaml.cs` failed silently. Confirm the packages in **Step 5** are installed and the call to `ConfigureSyncfusionAIServices()` runs.
- **The control does not appear or throws a `XamlParseException`**:
  - Verify that the `Syncfusion.SfSmartComponents.WPF` assembly is referenced and the namespace matches the installed assembly's casing.
- **Suggestions are generated but never accepted**:
  - Confirm the focus is on the editor when pressing **Tab** or **Right Arrow**.

For additional troubleshooting, refer to the Syncfusion WPF Smart Text Editor API reference and the release notes for your installed version.

## Next steps

- [Commands in WPF Smart Text Editor](commands.md) — Handle text-change events through the `TextChangedCommand`.
- [Customization in WPF Smart Text Editor](customization.md) — Style the editor and customize the suggestion display.
- [Suggestion display modes](suggestion-display-mode.md) — Switch between inline and popup suggestions.