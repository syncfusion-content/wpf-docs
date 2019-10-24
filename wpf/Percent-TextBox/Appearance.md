---
layout: post
title: Appearance| PercentTextBox  | Wpf | Syncfusion
description: appearance 
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Appearance 

## Setting VisualStyle for PercentTextBox

The appearance of the PercentTextBox control can be customized by using the VisualStyle property. The following are the various built-in visual styles for PercentTextBox control.

* Blend
* Office2003
* Office2007Blue
* Office2007Black
* Office2007Silver
* ShinyBlue
* ShinyRed
* SyncOrange
* VS2010
* Metro
* Transparent

## Blendability

You can edit the PercentTextBox Template to give a nice look and feel by using Expression Blend.

The steps to edit the PercentTextBox Template by using Expression Blend are as follows:

1. Create a simple WPF application in Expression Blend.
2. Drag and drop the PercentTextBox into the application from the Assets tab.

   ![](Appearance_images/Appearance_img1.png)

3. After creating the PercentTextBox, select the PercentTextBox and navigate to Object -> Edit Style -> Edit a Copy, to edit the Template of the PercentTextBox.

   ![](Appearance_images/Appearance_img2.png)

   Another way to edit the Template is as follows:

4. In Object and Timeline, right-click the PercentTextBox control and select the Edit Template option, as displayed below.

   ![](Appearance_images/Appearance_img3.png)


   This will open a dialog (below) where you can give your style a name and define exactly where you’d like to store it.

   ![](Appearance_images/Appearance_img4.png)

The result of these steps is an XAML, which is placed within your application. This XAML represents the default style for the PercentTextBox.

{% tabs %}
{% highlight xaml %}

<syncfusion:PercentTextBox x:Name="percentTextBox" Height="25" Width="150" 
                            CornerRadius="2" Style="{StaticResource 
                            PercentTextBoxStyle1}"/>

{% endhighlight %}
{% endtabs %}

All template items can now be found in the Objects and Timeline window.

![](Appearance_images/Appearance_img5.png)

Now you can replace the existing Template setter and Triggers with your own creation. In the Triggers tab you can select the Trigger and customize it as you want.

![](Appearance_images/Appearance_img6.png)

Here is a simple example to customize the UnFocused state of the PercentTextBox: 

When the control loses its focus, the Background color is set to LightGray. Similarly, you can customize every state and property in Expression Blend.

![](Appearance_images/Appearance_img7.png)

![](Appearance_images/Appearance_img8.png)
