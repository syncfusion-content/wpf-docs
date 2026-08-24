---
layout: post
title: Adding and Removing Items in WPF DocumentContainer | Syncfusion®
description: This section explains how to add and remove documents or items from the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control at runtime.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Adding and Removing Items in WPF DocumentContainer

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
