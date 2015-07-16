---
layout: post
title: MiniToolbar
description: minitoolbar
platform: wpf
control: Ribbon
documentation: ug
---

# MiniToolbar

Ribbon instance now ships with built-in MiniToolbar. The MiniToolbar facilitates the users to perform most of the formatting operations easily. The toolbar gets displayed automatically, whenever some text is selected in the ribbon window.

The following lines of code can be used to add a MiniToolbar to a ribbon instance.



<table>
<tr>
<td>
[XAML]&lt;ribbon:MiniToolbar x:Key="MiniToolbar"&gt;  &lt;ribbon:RibbonComboBox Width="100" IsEditable="True" &gt;    <ComboBoxItem>Arial</ComboBoxItem>    <ComboBoxItem>Tahoma</ComboBoxItem>    <ComboBoxItem>Verdana</ComboBoxItem>  &lt;/ribbon:RibbonComboBox&gt;  &lt;ribbon:RibbonComboBox Width="40" &gt;    <ComboBoxItem>6</ComboBoxItem>    <ComboBoxItem>7</ComboBoxItem>    <ComboBoxItem>8</ComboBoxItem>    <ComboBoxItem>9</ComboBoxItem>    <ComboBoxItem>10</ComboBoxItem>    <ComboBoxItem>11</ComboBoxItem>    <ComboBoxItem>12</ComboBoxItem>    <ComboBoxItem>14</ComboBoxItem>    <ComboBoxItem>16</ComboBoxItem>    <ComboBoxItem>18</ComboBoxItem>    <ComboBoxItem>20</ComboBoxItem>  &lt;/ribbon:RibbonComboBox&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.IncreaseFontSize" /&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.DecreaseFontSize" /&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.ToggleBold" /&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.ToggleItalic" /&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.ToggleUnderline" /&gt;  &lt;ribbon:RibbonButton SmallIcon="/SampleImages/Strike.png" Click="OnStrikeThrough"/&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.ToggleSubscript" /&gt;  &lt;ribbon:RibbonButton Command="EditingCommands.ToggleSuperscript" /&gt;  &lt;ribbon:RibbonButton SmallIcon="/SampleImages/FontColor.png"/&gt;  &lt;ribbon:RibbonButton SmallIcon="/SampleImages/TextHighlight.png"/&gt;&lt;/ribbon:MiniToolbar&gt;</td></tr>
<tr>
<td>
[C#]private MiniToolbar toolBar;toolBar = FindResource("MiniToolbar") as MiniToolbar;toolBar.PlacementTarget = Editor;private void Editor_MouseUp( object sender, MouseButtonEventArgs e ){Debug.WriteLine( "MouseUP" );if ( !Editor.Selection.IsEmpty ) 			toolBar.Show();else    		toolBar.Hide();}</td></tr>
</table>


{ ![](MiniToolbar_images/MiniToolbar_img1.jpeg) | markdownify }
{:.image }




