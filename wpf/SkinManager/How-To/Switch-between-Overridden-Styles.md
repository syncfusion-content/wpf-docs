---
layout: post
title: Switch-between-Overridden-Styles
description: switch between overridden styles
platform: wpf
control: SkinManager
documentation: ug
---

### Switch between Overridden Styles

Switching between the overridden styles should be done manually. The overridden styles should be merged into the Resource Dictionary. 

The following steps explain how to switch between the overridden styles.

1. Add the corresponding Resource Dictionaries in the sample.



[XAML]

&lt;ResourceDictionary&gt;

            &lt;ResourceDictionary.MergedDictionaries&gt;

                &lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;Component/Controls/Calendar/themes/ShinyRedStyle.xaml"/&gt;

                &lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;Component/Controls/Calendar/themes/BlendStyle.xaml"/&gt;

            &lt;/ResourceDictionary.MergedDictionaries&gt;

        &lt;/ResourceDictionary&gt;





2. Define the new styles using the BasedOn property. 



The following code snippet explains how to override the Syncfusion style for the Calendar Control.



[XAML]

&lt;Grid Name="grid"&gt;

        &lt;Grid.Resources&gt;

            &lt;Style x:Key="ShinyRedStyle" TargetType="syncfusion:CalendarEdit" BasedOn="{StaticResource ShinyRedCalendarEditStyle}" &gt;

                &lt;Setter Property="Background" Value="PaleGoldenRod"/&gt;

            &lt;/Style&gt;

            &lt;Style x:Key="BlendStyle" TargetType="syncfusion:CalendarEdit" BasedOn="{StaticResource BlendCalendarEditStyle}" &gt;

                &lt;Setter Property=" Background" Value="Green"/&gt;

            &lt;/Style&gt;

        &lt;/Grid.Resources&gt;

        &lt;Grid.ColumnDefinitions&gt;

            &lt;ColumnDefinition Width="*"/&gt;

            &lt;ColumnDefinition Width="*"/&gt;

        &lt;/Grid.ColumnDefinitions&gt;

        &lt;ComboBox Name="themecombobox" Grid.Column="0" SelectionChanged="ComboBox_SelectionChanged"&gt;

            <ComboBoxItem>ShinyRed</ComboBoxItem>

            <ComboBoxItem>Blend</ComboBoxItem>

        &lt;/ComboBox&gt;

        &lt;syncfusion:CalendarEdit Name="calendar" Grid.Column="1"&gt;&lt;/syncfusion:CalendarEdit&gt;        

&lt;/Grid&gt;



3. On ComboBox SelectionChanged event, particular overridden style should be set to the control depending on the current visual style. 



The following code snippet explains how to set the overridden styles to the controls.



[C#]



Private void ComboBox_SelectionChanged(object sender, SelectionChangedEventArgs e)

        {

            if (themecombobox.SelectedIndex == 0)

            {

                SkinStorage.SetVisualStyle(this, "ShinyRed");

                System.Windows.Style style = grid.Resources["ShinyRedStyle"] as Style;

                calendar.Style = style;

            }

            else

            {

                SkinStorage.SetVisualStyle(this, "Blend");

                System.Windows.Style style = grid.Resources["BlendStyle"] as Style;

                calendar.Style = style;

            }



        }





The output is displayed as shown below.

![](Switch-between-Overridden-Styles_images/Switch-between-Overridden-Styles_img1.png)
{:.image }




