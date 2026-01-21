---
layout: post
title: Assistive Labels in WPF TextInputLayout Control | Syncfusion
description: Learn all about assistive labels support in the Syncfusion WPF TextInputLayout (SfTextInputLayout) control and more.
platform: WPF
control: SfTextInputLayout
documentation: ug
---

# Assistive Labels in WPF TextInputLayout (SfTextInputLayout)

Assistive labels provide additional information about the text entered in the input view control.

## Helper Text

Helper text provides additional guidance on the `Input` field, such as instructions on how to use it. This can be set using the `HelperText` property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
  Hint="Name"
  HelperText="Enter your name">
  <TextBox />
</inputLayout:SfTextInputLayout>   

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HelperText = "Enter your name";
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![Helper text](Images/helpertext.png)

### Helper Text Visibility

The display state of the helper text can be specified using the `HelperTextVisibility` property, which is of type [`Visibility`](https://docs.microsoft.com/en-us/dotnet/api/system.windows.visibility?view=netframework-4.8).

## Error Message

If the text input is not valid, troubleshooting instructions are displayed in the error message. Error messages are shown below the input line until the correct text is entered. They can be set using the `ErrorText` property, and will only appear when the `HasError` property is set to `true`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Email" 
    HelperText="Enter your email address"
    ErrorText="Invalid email"
    HasError="true">
    <TextBox />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Email";
inputLayout.HelperText = "Enter your email address";
inputLayout.ErrorText = "Invalid email";
inputLayout.HasError = true; 
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![Error text](Images/errortext.png)

> **Note:** Error validations should be implemented at the application level.

## Character Counter
A character counter is used when character input needs to be limited. Use the `CharMaxLength` property to set the character limit. The display state of the character count can be specified using the `CharCountVisibility` property, which is of type [`Visibility`](https://docs.microsoft.com/en-us/dotnet/api/system.windows.visibility?view=netframework-4.8).


{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    CharCountVisibility="Visible"
    CharMaxLength="7"
    HelperText="Enter 5 to 7 characters">
    <TextBox />
</inputLayout:SfTextInputLayout> 
  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.CharMaxLength = 7;
inputLayout.CharCountVisibility = Visiblity.Visible;
inputLayout.HelperText = "Enter 5 to 7 characters";
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

![Character count](Images/charactercount.png)

> **Note:** When the number of characters entered in the input view exceeds the `CharMaxLength`, the `ErrorForeground` value will be applied to the hint label, baseline, border, and counter label.
