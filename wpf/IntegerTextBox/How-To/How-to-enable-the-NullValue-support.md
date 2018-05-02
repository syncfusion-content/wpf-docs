---
layout: post
title: How to enable the NullValue support | IntegerTextBox | wpf | Syncfusion
description: How to enable the NullValue support     
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# How to Enable the NullValue Support

IntegerTextBox accepts null values. To enable the null option you have to set the UseNullOption property to true. You can also set the NullValue property for the integer textbox. When you set the null value to the Value property, by default the value of the NullValue (Default value is null) property will be assigned to the Value property.

{%tabs%}
{%highlight xaml%}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"  
                           UseNullOption="True" NullValue="1"/>

{%endhighlight%}

{%highlight c#%}

Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.UseNullOption = true;
integerTextBox.NullValue = 1;

{%endhighlight%}

{%endtabs%}

In this sample, the NullValue (NullValue = 1) is set to the Value property of the IntegerTextBox because the default value of the Value property is null.

![](images/Concepts_img1.png) 

IntegerTextBox

{:.caption}

{%tabs%}
{%highlight xaml%}

<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"  
                           UseNullOption="True" NullValue="{x:Null}"/>

{%endhighlight%}
						   
{%highlight c#%}

Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();
integerTextBox.Width = 150;
integerTextBox.Height = 25;
integerTextBox.UseNullOption = true;
integerTextBox.NullValue = null;

{%endhighlight%}

{%endtabs%}
 

In this sample, the NullValue (NullValue = null) is set to the Value property of the IntegerTextBox because the default value of the Value property is null.

![](images/Concepts_img2.png) 

IntegerTextBox
{:.caption}

{%seealso%}

Setting Value

Maximum and Minimum Value

{%endseealso%}

