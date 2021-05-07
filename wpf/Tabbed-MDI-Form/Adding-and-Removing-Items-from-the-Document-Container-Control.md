---
layout: post
title: Adding and Removing Items in WPF Tabbed MDI Form control | Syncfusion
description: Learn here all about Adding and Removing Items from the Document Container Control support in Syncfusion WPF Tabbed MDI Form control and more.
platform: wpf
control: Tabbed MDI Form
documentation: ug
---

# Adding and Removing Items in WPF Tabbed MDI Form control

This page explains Adding and Removing Items from the Document Container Control in WPF Tabbed MDI Form (DocumentContainer) and more details.

## Adding and Removing Items from the Document Container Control in WPF Tabbed MDI Form (DocumentContainer)

This topic illustrates how to add and remove items from Document Container control.

## Adding items

Document Container allows the user to add new elements to its container(such as button, text block), using Items.Add method. Use the following code snippet, for calling this method.



{% tabs %}
{% highlight xaml %}
<syncfusion:DocumentContainer Name="DocContainer">
<Button ></Button></syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
Button a = new Button();
DocContainer.Items.Add(a);
{% endhighlight %}
{% endtabs %}


## Remove item

You can remove all the items in the Document Container using Items.Clear method. To remove all the items in the Document Container, use the following code snippet.



{% highlight C# %}



DocContainer.Items.Clear();

{% endhighlight %}

