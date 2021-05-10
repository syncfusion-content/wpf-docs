---
layout: post
title: Container Type in WPF TextInputLayout control | Syncfusion
description: Learn here all about Container Type support in Syncfusion WPF TextInputLayout (SfTextInputLayout) control and more.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Container Type in WPF TextInputLayout (SfTextInputLayout)

Containers enhance the discoverability of the input view by creating a contrast between the input view and the assistive elements.

N> The default value of the `ContainerType` is `Outlined`.

## Outlined

The container will be covered with a rounded border.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Outlined">
    <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Outlined type](Images/outlined.png)

## Filled

The background of the input view will be filled with container color, and the base line stroke and thickness will be changed based on the state of the input view.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Filled">
    <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Filled;
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Filled type](Images/Filled.png)

## None

The container will have an empty background and enough space.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="None">
    <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.None;
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![None type](Images/none.png)


