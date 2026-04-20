---
layout: post
title: Getting Started with WPF TextInputLayout Control | Syncfusion
description: Learn how to get started with Syncfusion Essential Studio WPF TextInputLayout (SfTextInputLayout) control, including its elements and more.
platform: WPF
control: SfTextInputLayout
documentation: ug
---

# Getting Started with WPF TextInputLayout (SfTextInputLayout)

This section explains the steps needed to configure the text input layout control.

## Adding TextInputLayout Reference

Refer to this [document](https://help.syncfusion.com/wpf/add-syncfusion-controls) to learn how to add Syncfusion controls in Visual Studio projects through various methods. Refer to this [document](https://help.syncfusion.com/wpf/control-dependencies) to learn about the assemblies required for adding TextInputLayout to your project.

## Initialize TextInputLayout

Import the namespace of the text input layout as shown in the following code snippet.

{% tabs %} 

{% highlight xaml %} 

xmlns:inputLayout="clr-namespace:Syncfusion.UI.Xaml.TextInputLayout;assembly=Syncfusion.SfTextInputLayout.WPF"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.UI.Xaml.TextInputLayout;

{% endhighlight %}

{% endtabs %} 

You can either use the below schema or the above namespace to refer to the TextInputLayout control in XAML.

{% tabs %} 

{% highlight xaml %} 

xmlns:inputLayout="http://schemas.syncfusion.com/wpf"

{% endhighlight %}

{% endtabs %} 

Then, initialize the text input layout as demonstrated in the following code snippet.

{% tabs %} 

{% highlight xaml %} 

 <inputLayout:SfTextInputLayout>
 <TextBox/>
 </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

 SfTextInputLayout inputLayout = new SfTextInputLayout();
 inputLayout.InputView = new TextBox();

{% endhighlight %}

{% endtabs %} 

## Adding Hint

A floating label for the text input layout can be added by setting the `Hint` property. The display state of the hint label can be specified using the `HintVisibility` property, which is of type [`Visibility`](https://docs.microsoft.com/en-us/dotnet/api/system.windows.visibility?view=netframework-4.8).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Name">
   <TextBox />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name"; 
inputLayout.InputView = new TextBox(); 

{% endhighlight %}

{% endtabs %}

When the input view is focused, the hint label will move to the top position; it will return to the original position when unfocused without any value entered.

Run the project and verify the following output to ensure the project is configured properly to add the text input layout control.

![Adding hint](Images/hintlabel.gif)

## Theme

SfTextInputLayout supports various built-in themes. Refer to the following links to apply themes for the SfTextInputLayout:

- [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
- [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF TextInputLayout](Images/Theme.png)
