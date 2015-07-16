---
layout: post
title: Binding-Support
description: binding support
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Binding Support

Data binding is the process of establishing a connection between the application UI and business logic. Data binding can be unidirectional (source -> target or target &lt;- source) or bidirectional (source &lt;-&gt; target). You can bind the data to the DoubleTextBox through the Value property.

The following example shows a simple binding between the value of the DoubleTextBox and another DoubleTextBox value that reflects the typed value:



XAML



&lt;StackPanel&gt;

    &lt;syncfusion:DoubleTextBox x:Name="doubleTextBox1" Width="150" Margin="10"/&gt;

    <syncfusion:DoubleTextBox x:Name="doubleTextBox2" Width="150" Margin="10" 

                Value="{Binding ElementName=doubleTextBox1,Path=Value,Mode=TwoWay}"/>

&lt;/StackPanel&gt;



{ ![](Binding-Support_images/Binding-Support_img1.png) | markdownify }
{:.image }




The Data Context property provides its value to child elements. So you can set the Data Context on a superior layout container and its value is provided to all child elements. This is very useful if you want to build a form that is bound to multiple properties of the same data object. If you don't explicitly define a source of binding, it takes the data context by default.



XAML



&lt;StackPanel DataContext="{StaticResource myCustomer}"&gt;

    &lt;TextBox Text="{Binding FirstName}"/&gt;

    &lt;TextBox Text ="{Binding LastName}"/&gt;

    &lt;syncfusion:DoubleTextBox Value="{Binding Phone}"/&gt;

    &lt;syncfusion:DoubleTextBox Value="{Binding Income}"/&gt;

&lt;/StackPanel&gt;



If you want to bind values other than double values, you need to use the Value Converter. The following example shows a simple binding between the value of the DoubleTextBox and the Textbox text that reflects the typed value:



XAML



&lt;StackPanel&gt;

    &lt;StackPanel.Resources&gt;

        &lt;c:StringToDoubleConverter x:Key="stringToDoubleConverter"/&gt;

    &lt;/StackPanel.Resources&gt;



    &lt;syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Margin="10"/&gt;

    <TextBox x:Name="textBox" Width="150" Margin="10" Text="{Binding 

             ElementName=doubleTextBox,Path=Value,Mode=TwoWay,

             Converter={StaticResource stringToDoubleConverter}}"/>    

&lt;/StackPanel&gt;



{ ![](Binding-Support_images/Binding-Support_img2.png) | markdownify }
{:.image }


