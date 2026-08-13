---
layout: post
title: Adding and Removing Items from the WPF Tabbed MDI Form | Syncfusion®
description: Learn here all about Adding and Removing Items from the Document Container Control support in Syncfusion® WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: WPF
control: DocumentContainer
documentation: ug
---

# Adding and Removing Items from the WPF Tabbed MDI Form control

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

This topic illustrates how to add and remove items from the DocumentContainer control.

## Adding Items

The DocumentContainer allows you to add new elements (such as a `Button` or `TextBlock`) to its container by using the `Items.Add` method. Use the following code snippet to add an item.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="TDI">
    <Button Content="Click Me" />
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
Button a = new Button() { Content = "Click Me" };
DocContainer.Items.Add(a);
{% endhighlight %}
{% endtabs %}

## Removing Items

You can remove a specific item from the DocumentContainer by using the `Items.Remove` method, or remove all items at once with the `Items.Clear` method.

{% tabs %}
{% highlight C# %}
// Remove a specific item
DocContainer.Items.Remove(a);

// Remove all items
DocContainer.Items.Clear();
{% endhighlight %}
{% endtabs %}

## See Also

* [Getting Started](Getting-Started.md)
* [Setting Mode for Document Container](Setting-Mode-for-Document-Container.md)
* [Setting Header of the DocumentContainer](Setting-Header-of-the-Document-container.md)
* [State Persistence](State-Persistence.md)

