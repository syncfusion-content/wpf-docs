---
layout: post
title: Configure Chat Client with AI-Powered Components | Syncfusion®
description: Learn how to implement a configure chat client with Syncfusion<sup>&reg;</sup> AI-Powered Components.
platform: wpf
control: SmartComponents
documentation: ug
---

# Configure Chat Client With Smart Components

The Smart Components uses a chat inference service resolved from dependency injection to generate contextual suggestions. Register a compatible chat client and an inference adapter in `App.xaml.cs`.

### Azure OpenAI

For **Azure OpenAI**, first [deploy an Azure OpenAI Service resource and model](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/create-resource), then values for `azureOpenAIKey`, `azureOpenAIEndpoint` and `azureOpenAIModel` will all be provided to you.

* Install the following NuGet packages to your project:

{% tabs %}

{% highlight c# tabtitle="Package Manager" %}

Install-Package Microsoft.Extensions.AI
Install-Package Microsoft.Extensions.AI.OpenAI
Install-Package Azure.AI.OpenAI

{% endhighlight %}

{% endtabs %}

* To configure the AI service, add the following settings to the **App.xaml.cs** file in your application.

{% tabs %}
{% highlight C# tabtitle="App.xaml.cs" %}

using Azure.AI.OpenAI;
using Microsoft.Extensions.AI;
using Microsoft.Extensions.DependencyInjection;
using Syncfusion.UI.Xaml.SmartComponents;
using System;
using System.ClientModel;
using System.Windows;

....

{
    /// <summary>
    /// Interaction logic for App.xaml
    /// </summary>
    public partial class App : Application
    {
        protected override void OnStartup(StartupEventArgs e)
        {
            base.OnStartup(e);

            string azureApiKey = "AZURE_OPENAI_KEY";
            Uri azureEndPoint = "AZURE_OPENAI_ENDPOINT";
            string deploymentName = "AZURE_OPENAI_MODEL";
            AzureOpenAIClient azureClient = new AzureOpenAIClient(azureEndPoint, new ApiKeyCredential(azureApiKey));
            IChatClient azureChatClient = azureClient.GetChatClient(deploymentName).AsIChatClient();
            SyncfusionAIExtension.Services.AddSingleton<IChatClient>(azureChatClient);
            SyncfusionAIExtension.ConfigureSyncfusionAIServices();

        }
    }
}

{% endhighlight %}
{% endtabs %}

### OpenAI

For **OpenAI**, create an API key and place it at `openAIApiKey`. The value for `openAIModel` is the model you wish.

* Install the following NuGet packages to your project:

{% tabs %}

{% highlight c# tabtitle="Package Manager" %}

Install-Package Microsoft.Extensions.AI
Install-Package Microsoft.Extensions.AI.OpenAI

{% endhighlight %}

{% endtabs %}

* To configure the AI service, add the following settings to the **App.xaml.cs** file in your app.

{% tabs %}
{% highlight C# tabtitle="App.xaml.cs" hl_lines="3 23" %}

using Microsoft.Extensions.AI;
using OpenAI;
using Syncfusion.UI.Xaml.SmartComponents;


....

string openAIApikey = "API-KEY";
string openAIModel = "gpt-4o-mini"; // example

var openAIClient = new OpenAIClient(
    new ApiKeyCredential(openAIApikey),
    new OpenAIClientOptions
    {
        // Default OpenAI endpoint; include /v1 if your SDK expects it
        Endpoint = new Uri("https://api.openai.com/v1/")
    });

IChatClient openAIChatClient = openAIClient.GetChatClient(openAIModel).AsIChatClient();
SyncfusionAIExtension.Services.AddChatClient(openAIClient);

SyncfusionAIExtension.ConfigureSyncfusionAIServices();

{% endhighlight %}
{% endtabs %}