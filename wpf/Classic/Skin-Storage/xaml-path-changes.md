---
layout: post
title: SkinStorage based theme xaml path changes | SkinStorage | WPF | Syncfusion
description: Changes of SkinStorage based theme xaml path moved from shared and tools project to classic shared and tools project.
platform: wpf
control: SkinStorage
documentation: ug
---

# Xaml Path Changes

Changes of SkinStorage based theme xaml path moved from `Syncfusion.Shared.WPF` and `Syncfusion.Tools.WPF` project to classic projects `Syncfusion.Shared.WPF.Classic` and `Syncfusion.Tools.WPF.Classic`.

## SkinManager

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/DefaultStyle.xaml"/&gt;</td>
<td>Not changed</td>
<td>DefaultStyle.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/MetroThemeBrushes.xaml"/&gt;</td>
<td>Not changed</td>
<td>MetroThemeBrushes.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/SkinManager.xaml"/&gt;</td>
<td>Not changed</td>
<td>SkinManager.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/SkinManager/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/SkinManager/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ChromelessWindow

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ChromelessWindow/Themes/Brushes.xaml"/&gt;</td>
<td>Not changed</td>
<td>Brushes.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ChromelessWindow/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ChromelessWindow/Themes/MetroStyle.xaml"/&gt;</td>
<td>Not changed</td>
<td>MetroStyle.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ChromelessWindow/Themes/Skins.xaml"/&gt;</td>
<td>Not changed</td>
<td>Skins.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ChromelessWindow/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ChromelessWindow/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Busy Indicator

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/BusyIndicator/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/BusyIndicator/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/BusyIndicator/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Button

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/Button/Themes/ButtonAdv.xaml"/&gt;</td>
<td>Not changed</td>
<td>ButtonAdv.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/Button/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ButtonControls/Button/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## DropDownButton

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/DropDownButton/Themes/DropDownButton.xaml"/&gt;</td>
<td>Not changed</td>
<td>DropDownButton.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/DropDownButton/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ButtonControls/DropDownButton/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## SplitButton

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/SplitButton/Themes/SplitButton.xaml"/&gt;</td>
<td>Not changed</td>
<td>SplitButton.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ButtonControls/SplitButton/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ButtonControls/SplitButton/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## CalendarEdit

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/CalendarEdit/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/CalendarEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/CalendarEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Carousel

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/Carousel/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
</table>

## Clock

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/Clock/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/Clock/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/Clock/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ColorBar

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorBar/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ColorBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MainTemplate.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ColorPicker

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorPicker/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorPicker/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ColorPicker/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Brushes.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MainTemplate.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ColorPickerPalette

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorPickerPalette/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ColorPickerPalette/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ColorPickerPalette/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ColorPickerPalette.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ComboBoxAdv

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ComboBoxAdv/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ComboBoxAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ComboBoxAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## DateTimeEdit

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/DateTimeEdit/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/DateTimeEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/DateTimeEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Brushes.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}BaseStyles.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}CalendarResources.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
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
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/Editors/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/Editors/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/Editors/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## MenuAdv

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/MenuAdv/Themes/MenuAdvResources.xaml"/&gt;</td>
<td>Not changed</td>
<td>MenuAdvResources.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/MenuAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/MenuAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## PinnableListBox

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/PinnableListBox/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/PinnableListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/PinnableListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Tile View

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/TileView/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/TileView/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/TileView/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TimeSpanEdit

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/TimeSpanEdit/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/TimeSpanEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/TimeSpanEdit/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## ToolBarAdv

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ToolBarAdv/Themes/Default/DefaultStyle.xaml"/&gt;</td>
<td>Not changed</td>
<td>DefaultStyle.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/ToolBarAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/ToolBarAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}Blend/BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Metro/MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007Black/Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007Blue/Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007Silver/Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010Black/Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010Blue/Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010Silver/Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Transparent/TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010/VS2010Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ToolBarResources.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## UpDown

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/UpDown/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF;component/Controls/UpDown/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Shared.WPF.Classic;component/Controls/UpDown/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## AutoComplete

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/AutoComplete/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/AutoComplete/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Controls/AutoComplete/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## CardView

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CardView/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CardView/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Controls/CardView/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## CheckListBox

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CheckListBox/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CheckListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Controls/CheckListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## CheckListBox

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CheckListBox/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Controls/CheckListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Controls/CheckListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## DockingManager

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/DockingManager/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}vista.aero.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/DockingManager/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Framework/DockingManager/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## DocumentContainer

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/DocumentContainer/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}Generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}vista.aero.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/DocumentContainer/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Framework/DocumentContainer/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Ribbon

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}Generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Windows8Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Framework/Ribbon/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Framework/Ribbon/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## FontComboBox

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/FontComboBox/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/FontComboBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/FontComboBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## FontListBox

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/FontListBox/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/FontListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/FontListBox/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## Gallery

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Gallery/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/Gallery/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/Gallery/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## GroupBar

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/GroupBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}Generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}DefaultStyle.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/GroupBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/GroupBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## HierarchyNavigator

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/HierarchyNavigator/Themes/HierarchyResources.xaml"/&gt;</td>
<td>Not changed</td>
<td>
HierarchyResources.xaml
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/HierarchyNavigator/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/HierarchyNavigator/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## NotifyIcon

NotifyIcon control moved to `Syncfusion.Tools.WPF.Classic` assembly.

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/NotifyIcon/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/NotifyIcon/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## RangeSlider

RangeSlider control moved to `Syncfusion.Tools.WPF.Classic` assembly.

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/RangeSlider/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/RangeSlider/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TabControlExt

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabControlExt/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Brushes.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}aero.normalcolor.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ExcelBlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ExcelBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ExcelSilverStyle.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabControlExt/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/TabControlExt/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TabNavigationControl

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabNavigationControl/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>Not changed</td>
<td>
{::no-markdown }<li>{:/}Generic.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransitionEffects.xaml{::no-markdown }</li>{:/}
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabNavigationControl/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/TabNavigationControl/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TabSplitter

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabSplitter/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TabSplitter/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/TabSplitter/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TaskBar

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TaskBar/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TaskBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/TaskBar/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## TreeViewAdv

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TreeViewAdv/Themes/generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>generic.xaml
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/TreeViewAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/TreeViewAdv/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>

## WizardControl

<table>
<tr>
<th>Before v18.4.0.30</th>
<th>After v18.4.0.30</th>
<th>Xaml names</th>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/WizardControl/Themes/Generic.xaml"/&gt;</td>
<td>Not changed</td>
<td>Generic.xaml
</td>
</tr>
<tr>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF;component/WizardControl/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>&lt;ResourceDictionary Source="/Syncfusion.Tools.WPF.Classic;component/WizardControl/Themes/&lt;Refer xaml name column&gt;"/&gt;</td>
<td>
{::no-markdown }<li>{:/}BlendStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}MetroStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2003Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2007SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlackStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010BlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2010SilverStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}Office2013Style.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyBlueStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}ShinyRedStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}SyncOrangeStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}TransparentStyle.xaml{::no-markdown }</li>{:/}
{::no-markdown }<li>{:/}VS2010Style.xaml{::no-markdown }</li>{:/}
</td>
</tr>
</table>