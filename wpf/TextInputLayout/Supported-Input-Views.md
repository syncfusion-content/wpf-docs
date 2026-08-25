---
layout: post
title: Supported Input Views in WPF TextInputLayout | Syncfusion®
description: Supported Input Views in SfTextInputLayout enable hosting controls such as TextBox, PasswordBox, ComboBox, and autocomplete inputs.
platform: wpf
control: SfTextInputLayout
documentation: ug
---

# Supported Input Views in WPF TextInputLayout (SfTextInputLayout)

Input views can be added to the text input layout control by setting the [InputView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.SfTextInputLayout.html#Syncfusion_UI_Xaml_TextInputLayout_SfTextInputLayout_InputView) property. To reduce the XAML syntax, the [InputView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.SfTextInputLayout.html#Syncfusion_UI_Xaml_TextInputLayout_SfTextInputLayout_InputView) property is applied with the ContentPropertyAttribute. The [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html) has the following controls as the supported input views.

* [TextBox](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/textbox) 

* [PasswordBox](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/passwordbox)

* [ComboBox](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/combobox)

* [ComboBoxAdv](https://help.syncfusion.com/wpf/combobox/overview)

* [SfTextBoxExt](https://help.syncfusion.com/wpf/autocomplete/overview)

* [DatePicker](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/datepicker)

* [SfDatePicker](https://help.syncfusion.com/wpf/datepicker/overview)

* [SfTimePicker](https://help.syncfusion.com/wpf/timepicker/overview)

* [UpDown](https://help.syncfusion.com/wpf/numericupdown/overview)

* [SfMaskedEdit](https://help.syncfusion.com/wpf/maskedtextbox/overview)

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

You can use the [ComboBox](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/controls/combobox?view=netframeworkdesktop-4.8) control as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Name" VerticalAlignment="Center" HorizontalAlignment="Center">
            <ComboBox x:Name="comboBox" Width="150" Height="10"  ItemsSource="{Binding Countries}"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            ComboBox comboBox = new ComboBox();
            comboBox.Width = 150;
            comboBox.Height = 10;
            comboBox.ItemsSource = viewModel.Countries;
            sfTextInputLayout.InputView = comboBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for ComboBox](Images/ComboBox_Image.PNG)

## ComboBoxAdv

You can use the [ComboBoxAdv](https://help.syncfusion.com/wpf/combobox/overview) control as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Name" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:ComboBoxAdv x:Name="comboBox" ItemsSource="{Binding Countries}" Width="150" Height="10"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            ComboBoxAdv comboBox = new ComboBoxAdv();
            comboBox.Width = 150;
            comboBox.Height = 10;
            comboBox.ItemsSource = viewModel.Countries;
            sfTextInputLayout.InputView = comboBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for ComboBoxAdv](Images/ComboBoxAdv_Image.PNG)

## Autocomplete (SfTextBoxExt)

You can use the [SfTextBoxExt](https://help.syncfusion.com/wpf/autocomplete/overview) control to enter the text as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

       <inputLayout:SfTextInputLayout Hint="Name" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:SfTextBoxExt AutoCompleteMode="Suggest" Width="250" 
                                      AutoCompleteSource="{Binding Countries}">

            </inputLayout:SfTextBoxExt>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

       SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Name" };
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;

            SfTextBoxExt sfTextBoxExt = new SfTextBoxExt();
            sfTextBoxExt.AutoCompleteMode = AutoCompleteMode.Suggest;
            sfTextBoxExt.Width = 250;
            sfTextBoxExt.AutoCompleteSource = viewModel.Countries;
            sfTextInputLayout.InputView = sfTextBoxExt;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for Autocomplete](Images/SfTextboxExt.PNG)

## DatePicker

You can use the standard WPF [DatePicker](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/datepicker) control to enter or select date values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Date" HelperText="Select your date of birth" VerticalAlignment="Center" HorizontalAlignment="Center">
            <DatePicker x:Name="datePicker" Width="150"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Date" };
            sfTextInputLayout.HelperText = "Select your date of birth";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            DatePicker datePicker = new DatePicker();
            datePicker.Width = 150;
            sfTextInputLayout.InputView = datePicker;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for DatePicker](Images/DatePicker_Img.PNG)

## SfDatePicker

You can use the [SfDatePicker](https://help.syncfusion.com/wpf/datepicker/overview) control to enter or select date values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Date" HelperText="Select your date of birth" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:SfDatePicker Width="150"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Date" };
            sfTextInputLayout.HelperText = "Select your date of birth";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            SfDatePicker sfDatePicker = new SfDatePicker();
            sfDatePicker.Width = 150;
            sfTextInputLayout.InputView = sfDatePicker;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for SfDatePicker](Images/SfDatePicker_Img.PNG)

## SfTimePicker

You can use the [SfTimePicker](https://help.syncfusion.com/wpf/timepicker/overview) control to enter or select time values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Time" HelperText="Select appointment time" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:SfTimePicker Width="150"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Time" };
            sfTextInputLayout.HelperText = "Select appointment time";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            SfTimePicker sfTimePicker = new SfTimePicker();
            sfTimePicker.Width = 150;
            sfTextInputLayout.InputView = sfTimePicker;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for SfTimePicker](Images/SfTimePicker_Img.PNG)

## UpDown

You can use the [UpDown](https://help.syncfusion.com/wpf/numericupdown/overview) control to enter numeric values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Quantity" HelperText="Enter quantity" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:UpDown Width="150" Height="25" MinValue="0" MaxValue="100" Value="1"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Quantity" };
            sfTextInputLayout.HelperText = "Enter quantity";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            UpDown upDown = new UpDown();
            upDown.Width = 150;
            upDown.Height = 25;
            upDown.MinValue = 0;
            upDown.MaxValue = 100;
            upDown.Value = 1;
            sfTextInputLayout.InputView = upDown;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for UpDown](Images/UpDown_Img.PNG)

## SfMaskedEdit

You can use the [MaskedTextBox](https://help.syncfusion.com/wpf/maskedtextbox/overview) (SfMaskedEdit) control to enter masked text as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Phone Number" HelperText="Enter your phone number" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:SfMaskedEdit x:Name="sfMaskedEdit" Width="150" Height="25" MaskType="Simple" Mask="(###) ###-####"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Phone Number" };
            sfTextInputLayout.HelperText = "Enter your phone number";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            SfMaskedEdit sfMaskedEdit = new SfMaskedEdit();
            sfMaskedEdit.Width = 150;
            sfMaskedEdit.Height = 25;
            sfMaskedEdit.MaskType = MaskType.Simple;
            sfMaskedEdit.Mask = "(###) ###-####";
            sfTextInputLayout.InputView = sfMaskedEdit;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for SfMaskedEdit](Images/SfMaskedEdit_Img.PNG)
