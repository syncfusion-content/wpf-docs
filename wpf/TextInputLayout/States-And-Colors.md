---
layout: post
title: Syncfusion TextInputLayout States and Colors
description: This section describes how to customize the colors based on its states in Syncfusion TextInputLayout control.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# States and Colors

Based on the text input layout state, the colors will be applied to the hint label, base line, border and assistive labels.

## Focused color

When the input view is focused, the value of the `FocusedForeground` property will be added to the hint label, base line and border.

I> The cursor color of the input view is the same as the `Accent` color of the  application.

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
inputLayout.ErrorText = "User name available";
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Focused color](Images/Focusedcolor.png)

N> The current active color of the text input layout can be obtained from the `ActiveForeground` property.

Since error is not a state, the error color will not be set to `ActiveForeground` when `HasError` property is set to `true`.

## Unfocused color

When the input view is unfocused, the `Foreground` property value will be applied to the hint label, base line and border.

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
inputLayout.ErrorText = "User name available";
inputLayout.InputView = new TextBox() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Unfocused color](Images/Unfocusedcolor.png)

## Error color

When the input layout is set to error state, the `ErrorForeground` property value will be added to the hint label, base line, border and error text.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ErrorForeground="Red"
    ErrorText="Should not contain special characters"
    HasError="true">
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

![Error color](Images/Errorcolor.png)

## Container color
The color of the container can be customized by setting the `ContainerBackground` property. It is applicable when the `ContainerType` property is set to `Filled` and `Outlined`.

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

![Container color](Images/Containercolor.png)

N> Container color is not applicable for `None' type.

## Disabled state

The text input layout is disabled by setting the `IsEnabled` property to `false`. The color of the container and other UI elements will also be changed to the disabled state, but its color cannot be customized.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    IsEnabled="false">
    <TextBox />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.IsEnabled = false;
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![Disabled state](Images/DisabledState.png)