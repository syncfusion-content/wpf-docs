---
layout: post
title: Getting Started| PercentTextBox  | Wpf | Syncfusion
description: getting started
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Getting Started

## Control Structure

![](Getting-Started_images/Getting-Started_img1.png)


![](Getting-Started_images/Getting-Started_img2.png)


## PercentTextBox Members

PercentTextBox exposes the following members:

### Properties


<table>
<tr>
<th>
Name</th><th>
Type</th><th>
Value it Accepts</th><th>
Description</th><th>
Default Value</th><th>
Reference Link</th></tr>
<tr>
<td>
ApplyNegativeForeground</td><td>
Dependency Property</td><td>
Bool</td><td>
Gets or sets the value that determines whether to apply the NegativeForeground in the Percent text box.</td><td>
True</td><td>
ApplyNegativeForeground</td></tr>
<tr>
<td>
ApplyZeroColor</td><td>
Dependency Property</td><td>
Bool</td><td>
Gets or sets the value that determines whether to apply the ZeroColor in the Percent text box.</td><td>
True</td><td>
ApplyZeroColor</td></tr>
<tr>
<td>
CornerRadius</td><td>
Dependency Property</td><td>
CornerRadius</td><td>
Gets or sets a value that represents the degree to which the corners of the Percent text box are rounded.</td><td>
No default value.</td><td>
CornerRadius</td></tr>
<tr>
<td>
Culture</td><td>
Dependency Property</td><td>
CultureInfo</td><td>
Gets or sets the Culture information associated with the PercentTextBox.</td><td>
</td><td>
Culture</td></tr>
<tr>
<td>
EnterToMoveNext</td><td>
Dependency Property</td><td>
Bool</td><td>
If this is set to true then the Enter key is used to change the focus from one field to another.</td><td>
true</td><td>
EnterToMoveNext</td></tr>
<tr>
<td>
IsReadOnly</td><td>
Dependency Property</td><td>
Bool</td><td>
Gets or sets the value that determines if the user can change the PercentValue in the Percent text box.</td><td>
true</td><td>
IsReadOnly</td></tr>
<tr>
<td>
IsScrollingOnCircle</td><td>
Dependency Property</td><td>
Bool</td><td>
The spin behavior in the PercentTextBox can be enabled or disabled by setting the IsScrollingOnCircle property.</td><td>
True</td><td>
IsScrollingOnCircle</td></tr>
<tr>
<td>
NegativeForeground</td><td>
Dependency Property</td><td>
Brush</td><td>
Gets or sets the NegativeForeground property.</td><td>
</td><td>
NegativeForeground</td></tr>
<tr>
<td>
NullValue</td><td>
Dependency Property</td><td>
double?</td><td>
Gets or sets the NullValue property. </td><td>
Null</td><td>
NullValue</td></tr>
<tr>
<td>
NumberFormat</td><td>
Dependency Property</td><td>
NumberFormatInfo</td><td>
A NumberFormat that defines the culturally appropriate format of displaying numbers, currency, and percentage.</td><td>
</td><td>
NumberFormat</td></tr>
<tr>
<td>
MaxValue</td><td>
Dependency Property</td><td>
Double</td><td>
Gets or sets the maximum value for the PercentTextBox.</td><td>
1.7976931348623157E+308</td><td>
MaxValue</td></tr>
<tr>
<td>
MaxValidation</td><td>
Dependency Property</td><td>
Enum of type MaxValidation</td><td>
Represents the Maximum value Validation constraint for the PercentTextBox.</td><td>
MaxValidation.OnKeyPress</td><td>
MaxValidation</td></tr>
<tr>
<td>
MaxValueOnExceedMaxDigit</td><td>
Dependency Property</td><td>
Bool</td><td>
Represents the behavior when the PercentValue exceeds the MaxValue.</td><td>
True</td><td>
MaxValueOnExceedMaxDigit</td></tr>
<tr>
<td>
MinValue</td><td>
Dependency Property</td><td>
Double</td><td>
Gets or sets the minimum allowed value for the PercentTextBox.</td><td>
negative 1.7976931348623157E+308..</td><td>
MinValue</td></tr>
<tr>
<td>
MinValueOnExceedMinDigit</td><td>
Dependency Property</td><td>
Bool</td><td>
Represents the behavior when the PercentValue exceeds the MinValue.</td><td>
True</td><td>
MinValueOnExceedMinDigit</td></tr>
<tr>
<td>
MinValidation</td><td>
Dependency Property</td><td>
Enum of type MinValidation</td><td>
Represents the Minimum value Validation constraint for the PercentTextBox.</td><td>
MinValidation.OnKeyPress</td><td>
MinValidation</td></tr>
<tr>
<td>
PercentDecimalDigits</td><td>
Dependency Property</td><td>
Int</td><td>
Gets or sets the number of decimal places to use in the PercentValue.</td><td>
2</td><td>
PercentDecimalDigits</td></tr>
<tr>
<td>
PercentDecimalSeparator</td><td>
Dependency Property</td><td>
string</td><td>
Gets or sets the string to use as the decimal separator in the PercentValue.</td><td>
.</td><td>
PercentDecimalSeparator</td></tr>
<tr>
<td>
PercentGroupSeparator</td><td>
Dependency Property</td><td>
String</td><td>
Gets or sets the string that separates groups of digits in the PercentValue.</td><td>
,</td><td>
PercentGroupSeparator</td></tr>
<tr>
<td>
PercentGroupSizes</td><td>
Dependency Property </td><td>
Int32Collection</td><td>
Gets or sets the number of digits in each group to the left of the decimal in the value.</td><td>
</td><td>
PercentGroupSizes</td></tr>
<tr>
<td>
PercentNegativePattern</td><td>
Dependency Property</td><td>
Int</td><td>
Gets or sets the format pattern for the negative Percent values.</td><td>
0</td><td>
PercentNegativePattern</td></tr>
<tr>
<td>
PercentPositivePattern</td><td>
Dependency Property</td><td>
Int</td><td>
Gets or sets the format pattern for the positive Percent values.</td><td>
0</td><td>
PercentPositivePattern</td></tr>
<tr>
<td>
PositiveForeground</td><td>
Dependency Property</td><td>
Brush</td><td>
Gets or sets the Foreground for the PercentTextBox.</td><td>
Black</td><td>
</td></tr>
<tr>
<td>
PercentEditMode</td><td>
Dependency Property</td><td>
Enum of type PercentEditMode</td><td>
Gets or sets the PercentEditMode property.</td><td>
PercentEditMode. DoubleMode</td><td>
</td></tr>
<tr>
<td>
SelectedText</td><td>
Dependency Property</td><td>
String</td><td>
Gets or sets the current selection in the textbox.</td><td>
Empty String.</td><td>
</td></tr>
<tr>
<td>
SelectionStart</td><td>
Dependency Property</td><td>
Int</td><td>
Gets or sets a character index for the beginning of the current selection.</td><td>
</td><td>
</td></tr>
<tr>
<td>
SelectionLength</td><td>
Dependency Property</td><td>
Int</td><td>
Gets or sets a value indicating the number of characters in the current selection in the percent text box.</td><td>
0</td><td>
</td></tr>
<tr>
<td>
TextSelectionOnFocus</td><td>
Dependency Property</td><td>
Bool</td><td>
If this property is set to true, then it will select all the text in the PercentTextBox when it gets focused.</td><td>
true</td><td>
</td></tr>
<tr>
<td>
UseNullOption</td><td>
Dependency Property</td><td>
Bool</td><td>
Disable or enable the NullValue support in the PercentTextBox.</td><td>
False</td><td>
UseNullOption</td></tr>
<tr>
<td>
PercentValue</td><td>
Dependency Property</td><td>
Double?</td><td>
Gets or sets the value for the PercentTextBox.</td><td>
0</td><td>
Value</td></tr>
<tr>
<td>
WatermarkOpacity</td><td>
Dependency Property</td><td>
Double</td><td>
Gets or sets the opacity of the WatermarkText in the PercentTextBox.</td><td>
0.5</td><td>
WatermarkOpacity</td></tr>
<tr>
<td>
WatermarkTemplate</td><td>
Dependency Property</td><td>
DateTemplate</td><td>
Gets or sets the DataTemplate for the WatermarkText.</td><td>
</td><td>
WatermarkTemplate</td></tr>
<tr>
<td>
WatermarkText</td><td>
Dependency Property</td><td>
String</td><td>
Gets or sets the WatermarkTextProperty.</td><td>
Empty String</td><td>
WatermarkText</td></tr>
<tr>
<td>
WatermarkTextForeground</td><td>
Dependency Property</td><td>
Brush</td><td>
Gets or sets the Foreground for the WatermarkText.</td><td>
</td><td>
WatermarkTextForeground</td></tr>
<tr>
<td>
WatermarkTextIsVisible</td><td>
Dependency Property</td><td>
Bool</td><td>
Gets or sets the value that determines the visibility of the WatermarkText in the Percent text box.</td><td>
False</td><td>
WatermarkTextIsVisible</td></tr>
<tr>
<td>
ZeroColor</td><td>
Dependency Property</td><td>
Brush</td><td>
Gets or sets the ZeroColor property.</td><td>
</td><td>
ZeroColor</td></tr>
</table>

### Methods



<table>
<tr>
<th>
Name</th><th>
Description</th><th>
Return Type</th><th>
Overloads</th></tr>
<tr>
<td>
Copy()</td><td>
Copies the current selection of the PercentTextBox to the Clipboard.</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
Select()</td><td>
Selects a range of text in the Percent text box.</td><td>
Void</td><td>
(+2) Overloads.</td></tr>
<tr>
<td>
SelectAll()</td><td>
Selects all the content of the Percent text box.</td><td>
Void</td><td>
</td></tr>
</table>

### Events



<table>
<tr>
<th>
Name</th><th>
Event Type</th><th>
Event Args Parameter</th><th>
Description</th><th>
Reference Link</th></tr>
<tr>
<td>
PercentValueChanged</td><td>
PropertyChangedCallback</td><td>
DependencyPropertyChangedEventArgs</td><td>
Occurs after the PercentValue of the PercentTextBox has changed.</td><td>
PercentValueChanged</td></tr>
<tr>
<td>
TextChanged</td><td>
TextChangedEventHandler</td><td>
TextChangedEventArgs</td><td>
Occurs when the text changes in the PercentTextBox.</td><td>
TextChanged</td></tr>
<tr>
<td>
CultureChanged</td><td>
PropertyChangedCallback</td><td>
DependencyPropertyChangedEventArgs</td><td>
Occurs after the Culture of the PercentTextBox has changed.</td><td>
CultureChanged</td></tr>
<tr>
<td>
MaxValueChanged</td><td>
PropertyChangedCallback</td><td>
DependencyPropertyChangedEventArgs</td><td>
Occurs after the MaxValue of the PercentTextBox has changed.</td><td>
MaxValueChanged</td></tr>
<tr>
<td>
MinValueChanged</td><td>
PropertyChangedCallback</td><td>
DependencyPropertyChangedEventArgs</td><td>
Occurs after the MinValue of the PercentTextBox has changed.</td><td>
MinValueChanged</td></tr>
<tr>
<td>
SelectionChanged</td><td>
RoutedEventHandler</td><td>
RoutedEventArgs</td><td>
Occurs when the text selection has changed.</td><td>
SelectionChanged</td></tr>
</table>

## Creating a PercentTextBox Control

PercentTextBox can be added to the application by using Visual Studio and Microsoft Expression Blend.

### Creating a PercentTextBox by using C#

The steps to create a PercentTextBox by using Visual Studio in C# are as follows:

1. Open Visual Studio.
2. On the File menu, select New -> Project. This opens the New Project Dialog box.



   ![C:/Documents and Settings/labuser/My Documents/WPF Tools correct Image.png](Getting-Started_images/Getting-Started_img3.png)


3. On the Project Dialog window, select WPF Application, in the name field, type the name of the project, and then click OK.

   ![](Getting-Started_images/Getting-Started_img4.png)


4. Add the following reference with the sample project:

1. Syncfusion.Shared.WPF.dll

   ![](Getting-Started_images/Getting-Started_img5.png)


2. Click the C# file, to open the C# file and add the PercentTextBox to the application. 


 
   ~~~csharp   

		public partial class MainWindow : Window

		{

		public MainWindow()

		{

		InitializeComponent();

		Syncfusion.Windows.Shared.PercentTextBox percentTextBox = new Syncfusion.Windows.Shared.PercentTextBox();

		percentTextBox.Width = 150;

		percentTextBox.Height = 25;

		this.LayoutRoot.Children.Add(percentTextBox);

		}

		}



   ~~~





![](Getting-Started_images/Getting-Started_img6.png)


N> If you do not set any PercentValue to the PercentTextBox then the default value will be as follows: If the UseNullOption is set to true then, Value of the NullValue property will be the default value. Otherwise Zero will be the default value (based on the MinValue and MaxValue the default value will change).


## Creating a PercentTextBox by using XAML

The steps to create a PercentTextBox by using Visual Studio in XAML are as follows:

1. Create a new application in Visual Studio.
2. In the Visual Studio Toolbox, click the Syncfusion WPF Toolbox tab and select PercentTextBox.
3. Drag and drop the PercentTextBox to Design View, to add the PercentTextBox to the application.



   ![](Getting-Started_images/Getting-Started_img7.png)


4. On the Properties window, customize the properties of the CurrencyTextBox.

   ~~~xaml

    

		<Window x:Class="WpfApp.MainWindow"

		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

		Title="PercentTextBox Demo" Height="367" Width="492" xmlns:syncfusion="http://schemas.syncfusion.com/wpf">



		<Grid x:Name="LayoutRoot">

		<syncfusion:PercentTextBox Height="23" HorizontalAlignment="Left" Margin="92,134,0,0" Name="percentTextBox1" VerticalAlignment="Top" Width="120" />

		</Grid>

		</Window>


   ~~~





![](Getting-Started_images/Getting-Started_img8.png)



## Creating a PercentTextBox by using Expression Blend

The steps to create a PercentTextBox in the application by using Expression Blend are as follows:

1. Open Expression Blend. 
2. On the File menu, select New Project. This opens the New Project dialog box.



   ![](Getting-Started_images/Getting-Started_img9.png)


3. In the Project types panel, select WPF Application and then click OK.

   ![](Getting-Started_images/Getting-Started_img10.png)


4. Add the following reference with the sample project:
   1. Syncfusion.Shared.WPF.dll
   2. On the Window menu, select Assets. This opens the Assets Library dialog box.
5. In the Search box, type PercentTextBox. This displays the search results.



   ![](Getting-Started_images/Getting-Started_img11.png)


6. Drag the PercentTextBox control to Design View.

   ![](Getting-Started_images/Getting-Started_img12.png)



    
   ~~~xaml


		<Window x:Class="WpfApp.MainWindow"

		xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

		xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

		Title="PercentTextBox Demo" Height="367" Width="492" xmlns:syncfusion="http://schemas.syncfusion.com/wpf">



		<Grid x:Name="LayoutRoot">

		<syncfusion:PercentTextBox Height="23" HorizontalAlignment="Left" Margin="92,134,0,0" Name="percentTextBox1" VerticalAlignment="Top" Width="120" />

		</Grid>

		</Window>

   ~~~





![](Getting-Started_images/Getting-Started_img13.png)


## Setting Value

You have to use the PercentValue property to set value for the PercentTextBox.

N> Do not use the Text property to set the value for the PercentTextBox. Use only the PercentValue property.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150"    
PercentValue="100"/>
{% endhighlight %}

{% highlight c# %}
percentTextBox.PercentValue = 100;
{% endhighlight %}
{% endtabs %}



![](Getting-Started_images/Getting-Started_img14.png)



## Setting Minimum and Maximum Value

You can set the Minimum and Maximum value by using the MinVal and MaxVal properties of the PercentTextBox.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Width="100" Height="25" 
PercentValue="100" MinValue="-999.99" MaxValue="999.99"/>
{% endhighlight %}

{% highlight c# %}
percentTextBox.MinValue = -999.99;percentTextBox.MaxValue = 999.99;
{% endhighlight %}
{% endtabs %}


![](Getting-Started_images/Getting-Started_img15.png)


## Setting Watermark

You can set the Watermark for the PercentTextBox by using the WatermarkText property. To enable Watermark, you have to set the WatermarkTextIsVisible property to true.

N> WatermarkText is visible only when the value is null.

{% tabs %}
{% highlight xaml %}
<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="100"        
    PercentValue="{x:Null}" MinValue="-999" MaxValue="999"       
	UseNullOption="True"          
	WatermarkText="Type Here" WatermarkTextIsVisible="True"/>
	{% endhighlight %}
	
{% highlight c# %}
percentTextBox.UseNullOption = true;
percentTextBox.NullValue = null;
percentTextBox.WatermarkText = "Type Here";
percentTextBox.WatermarkTextIsVisible = true;
{% endhighlight %}
{% endtabs %}


![](Getting-Started_images/Getting-Started_img16.png)


