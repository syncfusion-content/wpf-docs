---
layout: post
title: Supported input views in the Syncfusion SfTexInputLayout
description: This section describes the supported input views in the Syncfusion SfTextInputLayout control in WPF.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Supported input views

Input views can be added to the text input layout control by setting the [InputView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.SfTextInputLayout.html#Syncfusion_UI_Xaml_TextInputLayout_SfTextInputLayout_InputView) property. To reduce the XAML syntax, the [InputView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.SfTextInputLayout.html#Syncfusion_UI_Xaml_TextInputLayout_SfTextInputLayout_InputView) property is applied with the ContentPropertyAttribute. The [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html) has the following controls as the supported input views.

* TextBox 

* PasswordBox

* ComboBox

* [`ComboBoxAdv`](https://help.syncfusion.com/wpf/combobox/overview)

* [`SfTextBoxExt`](https://help.syncfusion.com/wpf/autocomplete/overview)

## TextBox

You can enter the text as an input by adding the [TextBox](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/controls/textbox-overview?view=netframeworkdesktop-4.8) in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

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

![Image for TextBox](Images/TextBox_Img.PNG)

## PasswordBox

You can enter the password characters as an input by adding the [PasswordBox](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.passwordbox?view=netcore-3.1) in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Password" HelperText="Enter your password">
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

![Image for PasswordBox](Images/PasswordBox_Img.PNG)

## ComboBox

You can use the `ComboBox` control as an input in the [`SfTextInputLayout`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Name">
            <ComboBox x:Name="comboBox" ItemsSource="{Binding MyItems}"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

        SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
        ComboBox comboBox = new ComboBox();
        comboBox.ItemsSource = MyItems;
        sfTextInputLayout.InputView = comboBox;
        this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for ComboBox](Images/ComboBox_Image.PNG)

## ComboBoxAdv

You can use the [`ComboBoxAdv`](https://help.syncfusion.com/wpf/combobox/overview) control as an input in the [`SfTextInputLayout`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Name">
            <inputLayout:ComboBoxAdv x:Name="comboBox" ItemsSource="{Binding MyItems}"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

        SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
        ComboBoxAdv comboBox = new ComboBoxAdv();
        comboBox.ItemsSource = MyItems;
        sfTextInputLayout.InputView = comboBox;
        this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for ComboBoxAdv](Images/ComboBoxAdv_Image.PNG)

## Autocomplete (SfTextBoxExt)

You can use the [`SfTextBoxExt`](https://help.syncfusion.com/wpf/autocomplete/overview) control to enter the text as an input in the [`SfTextInputLayout`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Name">
            <inputLayout:SfTextBoxExt Text="SfTextInputLayout"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

        SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
        SfTextBoxExt sfTextBoxExt = new SfTextBoxExt() { Text = "SfTextInputLayout" };
        sfTextInputLayout.InputView = sfTextBoxExt;
        this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for SfTextBoxExt_Image](Images/ComboBoxAdv_Image.PNG)