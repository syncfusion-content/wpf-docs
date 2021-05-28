---
layout: post
title: Switch between Skins | SkinStorage | Wpf | Syncfusion
description: Learn here all about Switch between Skins at Run time support in Syncfusion WPF SkinStorage (Classic) control and more.
platform: wpf
control: SkinStorage
documentation: ug
---

# Switch between Skins at Run time in WPF SkinStorage (Classic)

Themes can be dynamically switched.

Example 1:

You can use the Syncfusion Skin Picker Control to switch between the skins. Just add the Skin Picker Control to your application as shown below.


{% tabs %}
{% highlight xaml %}

<syncfusion:SkinPicker Height="60"/>


{% endhighlight %}
{% endtabs %}

![Switch between skins at runtime](Switch-between-Skins-at-Run-time_images/Switch-between-Skins-at-Run-time_img1.png)





Example 2:

You can switch between the skins at run-time by using the ComboBox Selection Changed event. 

Below is the code snippet to explain how to switch between the skins at run-time by using the ComboBox SelectionChanged event.


{% tabs %}
{% highlight xaml %}

<Grid Name="grid">        
<Grid.ColumnDefinitions>
<ColumnDefinition Width="*"/>
<ColumnDefinition Width="*"/>
</Grid.ColumnDefinitions>
<ComboBox Name="themecombobox" Grid.Column="0" SelectionChanged="ComboBox_SelectionChanged" Width="150" Height="30">
<ComboBoxItem> Blend </ComboBoxItem>
<ComboBoxItem> ShinyBlue </ComboBoxItem>
</ComboBox>
<syncfusion:CalendarEdit Name="calendar" Grid.Column="1"></syncfusion:CalendarEdit>        
</Grid>

{% endhighlight %}
{% endtabs %}

On ComboBox SelectionChanged event, particular VisualStyle should be set to the control. 

The following code snippet explains how to set the switch between the skins.

{% tabs %}
{% highlight C# %}

Private void ComboBox_SelectionChanged(object sender, SelectionChangedEventArgs e)
{
    if (themecombobox.SelectedIndex == 0)
    {
        SkinStorage.SetVisualStyle(calendar, "ShinyBlue");
    }
    Else if (themecombobox.SelectedIndex == 1)
    {
        SkinStorage.SetVisualStyle(calendar, "Blend");
    }
}


{% endhighlight %}
{% endtabs %}

The output is displayed as shown below.



![Switch selection at runtime using combobox selection](Switch-between-Skins-at-Run-time_images/Switch-between-Skins-at-Run-time_img2.png)



