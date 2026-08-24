---
layout: post
title: Setting Header in WPF DocumentContainer | Syncfusion®
description: Set or customize the header text of documents in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control for clear identification.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Setting Header in WPF DocumentContainer

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

## Setting header programmatically

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


