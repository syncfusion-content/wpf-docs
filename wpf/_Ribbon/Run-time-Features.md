---
layout: post
title: Run time Features | Ribbon | WPF | Syncfusion
description: run time features
platform: wpf
control: Ribbon
documentation: ug
---

# Run-time Features

This section illustrates the following run-time feature of Ribbon control. 

# Setting the ToolTip for the Split Button of the Ribbon Instance

Ribbon instance now provides support to set the ToolTip for the Split Button. It provides the following ToolTip options.

* Setting the ToolTip for the Entire Split Button
* Setting the ToolTip for the Upper and Lower Half of the Split Button





## Setting the ToolTip for the Entire Split Button

You can set the tooltip for the entire Split Button by using the ToolTip property of the Split Button. Use the following code for setting the tooltip feature.



<table>
<tr>
{% highlight xml %}
<syncfusion:SplitButton Label="Paste" SizeForm="Large" >
<syncfusion:SplitButton.ToolTip>
<syncfusion:ScreenTip Description="Split Button Tooltip" VerticalOffset="32">
<TextBlock Text="I am a Tool Tip" />
</syncfusion:ScreenTip>
</syncfusion:SplitButton.ToolTip>
</syncfusion:SplitButton>
{% endhighlight %}
</tr>
<tr>
{% highlight C# %}
ScreenTip screentip = new ScreenTip();
TextBlock text = new TextBlock();
text.Text = "I am a Tool Tip";
screentip.Content = text;
splitbutton.ToolTip = screentip; 
splitbutton = new SplitButton();
splitbutton.Label = "Split 1";
SplitButton splitbutton 1= new SplitButton();
splitbutton1.Label = "Split 2";
{% endhighlight %}
</tr>
</table>


![](Run-time-Features_images/Run-time-Features_img1.jpeg)



## Setting the ToolTip for the Upper and Lower Half of the Split Button

You can set the tooltip for the upper and lower half of the Split Button.

The ToolTip property is used to set the tooltip for the upper half of the Split Button, while the ToggleButtonToolTip property is used to set the tooltip for the drop-down in the lower half of the split button. Here is the code snippet for setting these properties.



<table>
<tr>
{% highlight xml %}
<syncfusion:SplitButton Label="Paste" SizeForm="Large" >
<syncfusion:SplitButton.ToolTip>
<syncfusion:ScreenTip Description="Split Button Tooltip" VerticalOffset="32"><TextBlock Text="Top Tool Tip" />
</syncfusion:ScreenTip>
</syncfusion:SplitButton.ToolTip>
<syncfusion:SplitButton.ToggleButtonToolTip>
<syncfusion:ScreenTip Description="Toggle Button Tooltip" VerticalOffset="29">
<TextBlock Text="Bottom Tool Tip" />
</syncfusion:ScreenTip>
</syncfusion:SplitButton.ToggleButtonToolTip>
</syncfusion:SplitButton>
{% endhighlight %}
</tr>
<tr>
{% highlight C# %}
ScreenTip screentip = new ScreenTip();
TextBlock text = new TextBlock();
text.Text = "Top Tool Tip";
screentip.Content = text;
// Setting the tooltip for the upper half of the split button.splitbutton.ToolTip = screentip;
ScreenTip screentip1 = new ScreenTip();
TextBlock text1 = new TextBlock();
text1.Text = "Bottom Tool Tip";
screentip1.Content = text;
// Setting the tooltip for the drop-down in the lower half of the split button.splitbutton.ToggleButtonToolTip = screentip1; 
screentip = new ScreenTip();TextBlock text = new TextBlock();
text.Text = "I am a Tool Tip";
screentip.Content = text;
splitbutton.ToolTip = screentip; 
splitbutton = new SplitButton();
splitbutton.Label = "Split 1";
SplitButton splitbutton 1= new SplitButton();splitbutton1.Label = "Split 2";
{% endhighlight %}
</tr>
</table>


![](Run-time-Features_images/Run-time-Features_img2.jpeg)




![](Run-time-Features_images/Run-time-Features_img3.jpeg)




# Options for Inserting Help Text in ScreenTip

Essential Tool WPF is enhanced with HelpText option. Users can add help text in ScreenTip. A line separator separates the Screen tip information from help text. 

N> When no HelpText is set the HelpText area and line separator get automatically hidden.



## Inserting Help Text in ScreenTip

Insert HelpText in ScreenTip, by using the following code.



<table>
<tr>
{% highlight xml %}
<syncfusion:ScreenTip Name="screenTip" HelpText="Help Text" Description="Insert Chart" ImageSource="{StaticResource Shapes}">    
<TextBlock Width="150" TextWrapping="Wrap" Text="Insert a Chart illustration" />
</syncfusion:ScreenTip>
{% endhighlight %}
</tr>
<tr>
{% highlight C# %}
screenTip.HelpText = "Display Help Text";
{% endhighlight %}
</tr>
</table>


![](Run-time-Features_images/Run-time-Features_img4.jpeg)




