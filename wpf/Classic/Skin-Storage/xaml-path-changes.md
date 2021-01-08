---
layout: post
title: SkinStorage theme xaml path changes | SkinStorage | WPF | Syncfusion
description: Changes of SkinStorage based theme xaml path moved from shared and tools project to classic shared and tools project.
platform: wpf
control: SkinStorage
documentation: ug
---

# SkinStorage theme xaml path changes

The SkinStorage based theme xaml files has been moved from `Syncfusion.Shared.WPF` and `Syncfusion.Tools.WPF` to `Syncfusion.Shared.WPF.Classic` and `Syncfusion.Tools.WPF.Classic` assemblies respectively.

Hence need to change the resource dictionary path based on usage of SkinStorage theme xaml files as shown below.

<table>
<tr>
<th>Actual xaml path</th>
<th>Classic xaml path</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/<b>Syncfusion.Shared.WPF</b>;component/SkinManager/BlendStyle.xaml</td>
<td>&lt;ResourceDictionary Source="/<b>Syncfusion.Shared.WPF.Classic</b>;component/SkinManager/BlendStyle.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/<b>Syncfusion.Tools.WPF</b>;component/Framework/DockingManager/Themes/BlendStyle.xaml</td>
<td>&lt;ResourceDictionary Source="/<b>Syncfusion.Tools.WPF.Classic</b>;component/Framework/DockingManager/Themes/BlendStyle.xaml</td>
</tr>
</table>

Please find the complete list of controls with their xaml path and current status after v18.4.0.30.

<table>
<tr>
<th>After v18.4.0.30 Status</th>
<th>Description</th>
</tr>
<tr>
<td>Not Changed</td>
<td>The xaml file path is not changed from current assembly project</td>
</tr>
<tr>
<td>Moved to Shared.WPF.Classic</td>
<td>The xaml file path is moved from <b>Shared.WPF</b> assembly to <b>Shared.WPF.Classic</b> assembly.</td>
</tr>
<tr>
<td>Moved to Tools.WPF.Classic</td>
<td>The xaml file path is moved from <b>Tools.WPF</b> assembly to <b>Tools.WPF.Classic</b> assembly.</td>
</tr>
</table>

## SkinManager

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>SkinManager/DefaultStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>SkinManager/MetroThemeBrushes.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>SkinManager/SkinManager.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>SkinManager/BlendStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/MetroStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2003Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2007BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2007BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2007SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2010BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2010BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2010SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/Office2013Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/ShinyBlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/ShinyRedStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/TransparentStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>SkinManager/VS2010Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
</table>

## ChromelessWindow

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Brushes.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/MetroStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Skins.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/BlendStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2003Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2007BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2007BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2007SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2010BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2010BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2010SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/Office2013Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/ShinyBlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/ShinyRedStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/SyncOrangeStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/TransparentStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ChromelessWindow/Themes/VS2010Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
</table>

## Busy Indicator

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/BlendStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/MetroStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2007BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2007BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2007SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2010BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2010BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/BusyIndicator/Themes/Office2010SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/BusyIndicator/Themes/TransparentStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/BusyIndicator/Themes/VS2010Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
</table>

## Button

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/ButtonAdv.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/BlendStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/MetroStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2007BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2007BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2007SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2010BlackStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2010BlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td>
</tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/Office2010SilverStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/ShinyBlueStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/ShinyRedStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/TransparentStyle.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
<tr>
<td>Controls/ButtonControls/Button/Themes/VS2010Style.xaml</td>
<td>Moved to Shared.WPF.Classic</td></tr>
</table>

## DropDownButton

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ButtonControls/DropDownButton/Themes/DropDownButton.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/DropDownButton/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## SplitButton

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ButtonControls/SplitButton/Themes/SplitButton.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ButtonControls/SplitButton/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## CalendarEdit

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/CalendarEdit/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/CalendarEdit/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/CalendarEdit/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## Carousel

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/Carousel/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
</table>

## Clock

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/Clock/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/Clock/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Clock/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## ColorBar

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ColorBar/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ColorBar/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/MainTemplate.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorBar/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## ColorPicker

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ColorPicker/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ColorPicker/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Brushes.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/MainTemplate.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPicker/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## ColorPickerPalette

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ColorPickerPalette/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ColorPickerPalette/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/ColorPickerPalette.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ColorPickerPalette/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## ComboBoxAdv

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/ComboBoxAdv/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ComboBoxAdv/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ComboBoxAdv/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## DateTimeEdit

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/DateTimeEdit/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/DateTimeEdit/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Brushes.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/BaseStyles.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/CalendarResources.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/DateTimeEdit/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## Editors

Editors applicable for below controls

* IntegerTextBox
* DoubleTextBox
* CurrencyTextBox
* PercentTextBox
* MaskedTextBox

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/Editors/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/Editors/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/Editors/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## MenuAdv

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/MenuAdv/Themes/MenuAdvResources.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/MenuAdv/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/MenuAdv/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## PinnableListBox

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/PinnableListBox/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/PinnableListBox/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/PinnableListBox/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## Tile View

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/TileView/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TileView/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TileView/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## TimeSpanEdit

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/TimeSpanEdit/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TimeSpanEdit/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/TimeSpanEdit/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## ToolBarAdv

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>

</tr>
<tr>
<td>Controls/ToolBarAdv/Themes/Default/DefaultStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/ToolBarAdv/Themes/Blend/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Metro/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2007Black/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2007Blue/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2007Silver/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2010Black/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2010Blue/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Office2010Silver/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/Transparent/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/VS2010/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/ToolBarAdv/Themes/ToolBarResources.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## UpDown

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/UpDown/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/UpDown/Themes/BlendStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/MetroStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2003Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2007BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2007BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2007SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2010BlackStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2010BlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2010SilverStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/Office2013Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/ShinyBlueStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/ShinyRedStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/SyncOrangeStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/TransparentStyle.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
<tr><td>Controls/UpDown/Themes/VS2010Style.xaml</td><td>Moved to Shared.WPF.Classic</td></tr>
</table>

## AutoComplete

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/AutoComplete/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/AutoComplete/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/AutoComplete/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## CardView

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/CardView/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/CardView/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CardView/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## CheckListBox

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Controls/CheckListBox/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/CheckListBox/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/CheckListBox/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## DockingManager

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Framework/DockingManager/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Framework/DockingManager/Themes/vista.aero.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Framework/DockingManager/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DockingManager/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## DocumentContainer

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Framework/DocumentContainer/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Framework/DocumentContainer/Themes/vista.aero.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Framework/DocumentContainer/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/DocumentContainer/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## Ribbon

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Framework/Ribbon/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Framework/Ribbon/Themes/Windows8Style.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>Framework/Ribbon/Themes/Office2007BlueStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Framework/Ribbon/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Framework/Ribbon/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## FontComboBox

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>FontComboBox/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/FontComboBox/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontComboBox/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## FontListBox

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>FontListBox/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/FontListBox/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/FontListBox/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## Gallery

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>Gallery/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/Gallery/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/Gallery/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## GroupBar

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>GroupBar/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>GroupBar/Themes/DefaultStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/GroupBar/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/GroupBar/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## HierarchyNavigator

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>HierarchyNavigator/Themes/HierarchyResources.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/HierarchyNavigator/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/HierarchyNavigator/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## NotifyIcon

NotifyIcon control moved to `Syncfusion.Tools.WPF.Classic` assembly.

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr><td>Controls/NotifyIcon/Themes/generic.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/NotifyIcon/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## RangeSlider

RangeSlider control moved to `Syncfusion.Tools.WPF.Classic` assembly.

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr><td>Controls/RangeSlider/Themes/Generic.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/RangeSlider/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## TabControlExt

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>TabControlExt/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>TabControlExt/Themes/Brushes.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>TabControlExt/Themes/aero.normalcolor.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>TabControlExt/Themes/ExcelBlackStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>TabControlExt/Themes/ExcelBlueStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr>
<td>TabControlExt/Themes/ExcelSilverStyle.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TabControlExt/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabControlExt/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## TabNavigationControl

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>TabNavigationControl/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr><tr>
<td>TabNavigationControl/Themes/TransitionEffects.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TabNavigationControl/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabNavigationControl/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## TabSplitter

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>TabSplitter/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TabSplitter/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TabSplitter/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## TaskBar

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>TaskBar/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TaskBar/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TaskBar/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## TreeViewAdv

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>
</tr>
<tr>
<td>TreeViewAdv/Themes/generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/TreeViewAdv/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/TreeViewAdv/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>

## WizardControl

<table>
<tr>
<th>Xaml path</th>
<th>After v18.4.0.30 status</th>

</tr>
<tr>
<td>WizardControl/Themes/Generic.xaml</td>
<td>Not changed</td>
</tr>
<tr><td>Controls/WizardControl/Themes/BlendStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/MetroStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2003Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2007BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2007BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2007SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2010BlackStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2010BlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2010SilverStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/Office2013Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/ShinyBlueStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/ShinyRedStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/SyncOrangeStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/TransparentStyle.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
<tr><td>Controls/WizardControl/Themes/VS2010Style.xaml</td><td>Moved to Tools.WPF.Classic</td></tr>
</table>