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

* [IntegerTextBox](https://help.syncfusion.com/wpf/integer-textbox/overview)

* [DoubleTextBox](https://help.syncfusion.com/wpf/double-textbox/overview)

* [PercentTextBox](https://help.syncfusion.com/wpf/percent-textbox/overview)

* [CurrencyTextBox](https://help.syncfusion.com/wpf/currency-textbox/overview)

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

## IntegerTextBox

You can use the [IntegerTextBox](https://help.syncfusion.com/wpf/integer-textbox/overview) control to enter integer values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Age" HelperText="Enter your age" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:IntegerTextBox x:Name="integerTextBox" Width="150" Height="25" MinValue="0" MaxValue="120" Value="25"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Age" };
            sfTextInputLayout.HelperText = "Enter your age";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            IntegerTextBox integerTextBox = new IntegerTextBox();
            integerTextBox.Width = 150;
            integerTextBox.Height = 25;
            integerTextBox.MinValue = 0;
            integerTextBox.MaxValue = 120;
            integerTextBox.Value = 25;
            sfTextInputLayout.InputView = integerTextBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for IntegerTextBox](Images/IntegerTextBox_Img.PNG)

## DoubleTextBox

You can use the [DoubleTextBox](https://help.syncfusion.com/wpf/double-textbox/overview) control to enter double values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Price" HelperText="Enter the price" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25" MinValue="0" MaxValue="10000" Value="99.99"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Price" };
            sfTextInputLayout.HelperText = "Enter the price";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            DoubleTextBox doubleTextBox = new DoubleTextBox();
            doubleTextBox.Width = 150;
            doubleTextBox.Height = 25;
            doubleTextBox.MinValue = 0;
            doubleTextBox.MaxValue = 10000;
            doubleTextBox.Value = 99.99;
            sfTextInputLayout.InputView = doubleTextBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for DoubleTextBox](Images/DoubleTextBox_Img.PNG)

## PercentTextBox

You can use the [PercentTextBox](https://help.syncfusion.com/wpf/percent-textbox/overview) control to enter percentage values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Discount" HelperText="Enter the discount percentage" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:PercentTextBox x:Name="percentTextBox" Width="150" Height="25" MinValue="0" MaxValue="100" PercentValue="10"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Discount" };
            sfTextInputLayout.HelperText = "Enter the discount percentage";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            PercentTextBox percentTextBox = new PercentTextBox();
            percentTextBox.Width = 150;
            percentTextBox.Height = 25;
            percentTextBox.MinValue = 0;
            percentTextBox.MaxValue = 100;
            percentTextBox.PercentValue = 10;
            sfTextInputLayout.InputView = percentTextBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for PercentTextBox](Images/PercentTextBox_Img.PNG)

## CurrencyTextBox

You can use the [CurrencyTextBox](https://help.syncfusion.com/wpf/currency-textbox/overview) control to enter currency values as an input in the [SfTextInputLayout](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TextInputLayout.html).

{% tabs %} 

{% highlight xaml %} 

        <inputLayout:SfTextInputLayout Hint="Amount" HelperText="Enter the amount" VerticalAlignment="Center" HorizontalAlignment="Center">
            <inputLayout:CurrencyTextBox x:Name="currencyTextBox" Width="150" Height="25" MinValue="0" MaxValue="100000" Value="1000"/>
        </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

            SfTextInputLayout sfTextInputLayout = new SfTextInputLayout() { Hint = "Amount" };
            sfTextInputLayout.HelperText = "Enter the amount";
            sfTextInputLayout.HorizontalAlignment = HorizontalAlignment.Center;
            sfTextInputLayout.VerticalAlignment = VerticalAlignment.Center;
            CurrencyTextBox currencyTextBox = new CurrencyTextBox();
            currencyTextBox.Width = 150;
            currencyTextBox.Height = 25;
            currencyTextBox.MinValue = 0;
            currencyTextBox.MaxValue = 100000;
            currencyTextBox.Value = 1000;
            sfTextInputLayout.InputView = currencyTextBox;
            this.Content = sfTextInputLayout;

{% endhighlight %}

{% endtabs %}

![Image for CurrencyTextBox](Images/CurrencyTextBox_Img.PNG)

## Input Views Limitations

The following are the limitations when using [DatePicker](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/datepicker), [SfDatePicker](https://help.syncfusion.com/wpf/datepicker/overview) and [SfTimePicker](https://help.syncfusion.com/wpf/timepicker/overview) as the InputView of SfTextInputLayout.

1. The hint is always displayed in the `AlwaysFloat` state and does not move to the inline position based on the control's focus state or the presence of a selected date/time value.

2. When `CharCountVisibility` is enabled, the character count is always displayed as `0`, regardless of the selected date or time value.
