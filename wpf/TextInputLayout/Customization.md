---
layout: post
title: Customization in WPF TextInputLayout Control | Syncfusion
description: Learn about customization support in the Syncfusion WPF TextInputLayout (SfTextInputLayout) control and more.
platform: WPF
control: SfTextInputLayout
documentation: ug
---

# Customization in WPF TextInputLayout (SfTextInputLayout)

Based on the text input layout state, colors are applied to the hint label, baseline, border, and assistive labels.

## Focused Color

When the input view is focused, the `FocusedForeground` property value is applied to the hint label, baseline, and border.

> **Important:** The cursor color of the input view matches the `Accent` color of the application.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="User name" 
    FocusedForeground="Green"
    HelperText="Enter your name"
 <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "User name";
inputLayout.FocusedForeground = Brushes.Green;
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Focused color](Images/Focusedcolor.png)

> **Note:** The current active color of the text input layout can be obtained from the `ActiveForeground` property. Since error is not a state, the error color will not be set to `ActiveForeground` when the `HasError` property is set to `true`.
## Unfocused Color

When the input view is unfocused, the `Foreground` property value is applied to the hint label, baseline, and border.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="User name" 
    Foreground="Gray"
    HelperText="Enter your name"
 <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "User name";
inputLayout.Foreground = Brushes.Gray;
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Unfocused color](Images/Unfocusedcolor.png)

## Error Color

When the input layout is set to an error state, the `ErrorForeground` property value is applied to the hint label, baseline, border, and error text.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ErrorForeground="Red"
    ErrorText="Should not contain special characters"
    HasError="True">
    <TextBox Text="John/" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ErrorForeground = Brushes.Red;
inputLayout.ErrorText = "Should not contain special characters";
inputLayout.HasError = true;
inputLayout.InputView = new TextBox() { Text = "John/" }; 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Error color](Images/Errorcolor.png)

## Container Color
The color of the container can be customized by setting the `ContainerBackground` property. It is applicable when the `ContainerType` property is set to `Filled` or `Outlined`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedForeground="Blue"
    ContainerType="Outlined"
    ContainerBackground="LightBlue">
    <TextBox Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.FocusedColor = Brushes.Blue;
inputLayout.ContainerBackground = Brushes.LightBlue;
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.InputView = new Entry() { TextBox = "John" }; 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Container color](Images/Containercolor.png)

> **Note:** Container color is not applicable for the `None` type.

## Outline Corner Radius

The corner radius of the outlined border can be customized by setting the `OutlineCornerRadius` property.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Outlined"
    OutlineCornerRadius="8">
    <TextBox />
</inputLayout:SfTextInputLayout>  
			
{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.OutlineCornerRadius = 8;
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![WPF TextInputLayout Outline radius](Images/outlineradius.png)

> **Note:** It is only applicable to the `Outlined` type of container.
