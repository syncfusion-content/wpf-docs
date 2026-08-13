---
layout: post
title: Setting Header of the DocumentContainer in WPF Tabbed MDI Form | Syncfusion®
description: Learn here all about Setting Header of the DocumentContainer support in Syncfusion® WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: WPF
control: DocumentContainer
documentation: ug
---

# Setting Header of the DocumentContainer in WPF Tabbed MDI Form

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

Using the `Header` attached property, the user can set the header for each DocumentContainer child element. The `Header` accepts any `object`, so the header text can be customized using a `HeaderTemplate`. Use the following code snippet to set the header for a DocumentContainer element.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer x:Name="flow" syncfusion:DocumentContainer.Header="Features" />
    <!-- additional child windows -->
</syncfusion:DocumentContainer>
{% endhighlight %}
{% endtabs %}

![DocumentContainer with a custom header on its child window](Setting-Header-of-the-Document-container_images/Setting-Header-of-the-Document-container_img1.jpeg)

## Setting the Header Programmatically

The header of a DocumentContainer element can be set by the `SetHeader` static method.

{% tabs %}
{% highlight C# %}
FlowDocumentScrollViewer flow = new FlowDocumentScrollViewer();
DocumentContainer.SetHeader(flow, "Features");
DocContainer.Items.Add(flow);
{% endhighlight %}
{% endtabs %}

## See Also

* [Getting Started](Getting-Started.md)
* [Setting Mode for Document Container](Setting-Mode-for-Document-Container.md)
* [Adding and Removing Items](Adding-and-Removing-Items-from-the-Document-Container-Control.md)


