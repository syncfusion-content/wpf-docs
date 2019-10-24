---
layout: post
title: Layout Related Features| DoubleTextBox  | Wpf | Syncfusion
description: layout and behavior related features
platform: wpf
control: DoubleTextBox 
documentation: ug
---

# Layout and Behavior Related Features

## IsReadOnly

If the DoubleTextBox is read-only, then no user input or edits are allowed but programmatic changes can be made. The user can still select text and the cursor still appears.

## CornerRadius

The Corner Radius describes the degree to which corners are rounded. This property has no default value.



![Corner radius](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img1.png)



## Negative Foreground

The [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Control_Foreground) of the DoubleTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. When a Negative value is assigned to a Value property, then automatically a NegativeForeground value is assigned to the Foreground property.

N> The [NegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~NegativeForeground.html) in the DoubleTextBox can be enabled by setting the [ApplyNegativeForeground](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyNegativeForeground.html) property to true.


{% highlight xaml %}



<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25" Value="-123" 

ApplyNegativeForeground="True" NegativeForeground="Red"/>

{% endhighlight %}

![Negative foreground](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img2.png)



## Zero Color

The [Foreground](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.control.foreground?redirectedfrom=MSDN&view=netframework-4.7.2#System_Windows_Controls_Control_Foreground) of the DoubleTextBox can be customized based on the [Value](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.DoubleTextBox~Value.html) property. When zero is assigned as a value to a Value property, then automatically the [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) is set to the Foreground property.

Note: The [ZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ZeroColor.html) in the DoubleTextBox can be enabled by setting the [ApplyZeroColor](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~ApplyZeroColor.html) property to true.
 

{% highlight xaml %}

<syncfusion:DoubleTextBox x:Name="doubleTextBox" Width="150" Height="25" Value ="0"

ApplyZeroColor="True" ZeroColor="Magenta"/>

{% endhighlight %}

![Zero color](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img3.png)



## EnterToMoveNext

If you press the Enter key in the DoubleTextBox then the Focus moves to the next element in the application. To enable this feature you have to set the [EnterToMoveNext](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~EnterToMoveNext.html) property to true.

## TextSelectionOnFocus

The [TextSelectionOnFocus](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.EditorBase~TextSelectionOnFocus.html) property allows the DoubleTextBox to act like standard text boxes when the cursor hovers over. 



![Text selection on focus](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img4.png)





![Text selection on focus](Layout-and-Behavior-Related-Features_images/Layout-and-Behavior-Related-Features_img5.png)



