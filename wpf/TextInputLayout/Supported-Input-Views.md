---
layout: post
title: Supported input views in the SfTexInputLayout
description: This section describes what are the supported input views in Syncfusion SfTextInputLayout control in WPF.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Supported input views

[SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html) has only the following controls as the supported input views.

* TextBox 

* PasswordBox

## TextBox

You can enter text as input by adding the [TextBox](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/controls/textbox-overview?view=netframeworkdesktop-4.8) in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

         <inputLayout:SfTextInputLayout Hint="Name" HelperText="Enter your name">
            <TextBox/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

         SfTextInputLayout inputLayout = new SfTextInputLayout();
         inputLayout.Hint = "Name";
         inputLayout.HelperText = "Enter your name";
         inputLayout.InputView = new TextBox();
         this.Content = inputLayout;
			
{% endhighlight %}

{% endtabs %}

![Image for TextBox](Images/TextBox_Img.png)

## PasswordBox

You can enter the password characters as input by adding the [PasswordBox](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.passwordbox?view=netcore-3.1) in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Password" HelperText="Enter password">
            <PasswordBox/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

         SfTextInputLayout inputLayout = new SfTextInputLayout();
         inputLayout.Hint = "Password";
         inputLayout.HelperText = "Enter your password";
         inputLayout.InputView = new PasswordBox();
         this.Content = inputLayout;

{% endhighlight %}

{% endtabs %}

![Image for PasswordBox](Images/PasswordBox_Img.png)
