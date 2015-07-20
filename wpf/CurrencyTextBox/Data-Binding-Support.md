---
layout: post
title: Data-Binding-Support
description: data binding support
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Data Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target &lt;- source) or bidirectional (source &lt;-&gt; target). You can bind the data to the CurrencyTextBox through the Value property.

The following example shows a simple binding between the value of the CurrencyTextBox and another CurrencyTextBox value that reflects the typed value:



XAML



&lt;StackPanel&gt;

    &lt;syncfusion:CurrencyTextBox x:Name="currencyTextBox1" Width="150" Margin="10"/&gt;

    <syncfusion:CurrencyTextBox x:Name="currencyTextBox2" Width="150" Margin="10" 

            Value="{Binding ElementName=currencyTextBox1,Path=Value,Mode=TwoWay}"/>

&lt;/StackPanel&gt;



{ ![](Data-Binding-Support_images/Data-Binding-Support_img1.png) | markdownify }
{:.image }


The Data Context property provides its value to child elements. So you can set the Data Context on a superior layout container and its value is provided to all child elements. This is very useful if you want to build a form that is bound to multiple properties of the same data object. If you don't explicitly define a source of binding, it takes the data context by default.



XAML



&lt;StackPanel DataContext="{StaticResource myCustomer}"&gt;

    &lt;TextBox Text="{Binding FirstName}"/&gt;

    &lt;TextBox Text ="{Binding LastName}"/&gt;

    &lt;syncfusion:CurrencyTextBox Value="{Binding Phone}"/&gt;

    &lt;syncfusion:CurrencyTextBox Value="{Binding Income}"/&gt;

&lt;/StackPanel&gt;



If you want to bind values other than decimal values, then you need to use the Value Converter. The following example shows a simple binding between the value of the CurrencyTextBox and the Textbox text that reflects the typed value:



XAML



&lt;StackPanel&gt;

    &lt;StackPanel.Resources&gt;

        &lt;c:StringToDecimalConverter x:Key="stringToDecimalConverter"/&gt;

    &lt;/StackPanel.Resources&gt;



&lt;syncfusion:CurrencyTextBox x:Name="currencyTextBox" Width="150" Margin="10"/&gt;

<TextBox x:Name="textBox" Width="150" Margin="10" Text="{Binding 

        ElementName=currencyTextBox,Path=Value,Mode=TwoWay,Converter={StaticResource 

        stringToDecimalConverter}}"/>

&lt;/StackPanel&gt;





{ ![](Data-Binding-Support_images/Data-Binding-Support_img2.png) | markdownify }
{:.image }


