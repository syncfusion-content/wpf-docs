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

N> The Smart Text Editor is distributed as part of the `Syncfusion.SfSmartComponents.WPF` package provides advanced AI-assisted features to enhance text editing and content management. Ensure your application has the required AI service configuration to enable these features.

## Prerequisites

Before proceeding, ensure the following are set up:
1. Install .NET SDK
  - [.NET 9 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0) or later must be installed.
2. Set up a WPF Environment with Visual Studio. Supported Visual Studio Versions:
  - Visual Studio 2022: Version 17.13 or later (e.g., 17.14.7) for .NET 9 development.
  - Visual Studio 2026: Required for .NET 10 development.

## Step 1: Create a New WPF Project

1. Go to **File > New > Project** and choose the **WPF App** template.
2. Name the project and choose a location. Then click **Next**.
3. Select the .NET framework version and click **Create**.

## Step 2: Install the Syncfusion<sup>&reg;</sup> WPF SmartComponents NuGet Package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for [Syncfusion.SfSmartComponents.WPF](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.SmartComponents.html) and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

## Step 3: Adding control via Designer

SfSmartTextEditor control can be added to the application by dragging it from Toolbox and dropping it in Designer view. The required assembly references will be added automatically.

### Adding control manually in XAML

In order to add control manually in XAML, do the below steps,

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
    <Grid>
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

N> If no AI inference service is configured, the editor generates offline suggestions from your UserPhrases.

## Step 5: Register the AI Service

To configure the AI services, you must provide the **`azureApiKey`** in the **`App.xaml.cs`** file.

Follow the steps below to set up the AI services:

1.  Open **NuGet Package Manager** and search for the following packages.
2.  Install the **latest versions** of each package:
    *   **Azure.AI.OpenAI**
    *   **Microsoft.Extensions.AI**
    *   **Microsoft.Extensions.AI.OpenAI**

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

Press **F5** to build and run the application. Once compiled, the smart text editor will be displayed with the data provided, and AI features will be available after configuration.

Here is the result of the previous codes,

![Getting Started in WPF Smart Text Editor.](images/getting-started/wpf-smarttexteditor-getting-started.gif)

N> You can refer to our [WPF Smart Text Editor](https://www.syncfusion.com/wpf-controls/smart-text-editor) feature tour page for its groundbreaking feature representations.