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



{% highlight xml %}

[XAML]
<ribbon:MiniToolbar x:Key="MiniToolbar">  
<ribbon:RibbonComboBox Width="100" IsEditable="True" >    
<ComboBoxItem>Arial</ComboBoxItem>    
<ComboBoxItem>Tahoma</ComboBoxItem>    
<ComboBoxItem>Verdana</ComboBoxItem>  
</ribbon:RibbonComboBox>  
<ribbon:RibbonComboBox Width="40" >    <
ComboBoxItem>6</ComboBoxItem>    
<ComboBoxItem>7</ComboBoxItem>    
<ComboBoxItem>8</ComboBoxItem>    
<ComboBoxItem>9</ComboBoxItem>    
<ComboBoxItem>10</ComboBoxItem>    
<ComboBoxItem>11</ComboBoxItem>    
<ComboBoxItem>12</ComboBoxItem>    
<ComboBoxItem>14</ComboBoxItem>    
<ComboBoxItem>16</ComboBoxItem>    
<ComboBoxItem>18</ComboBoxItem>    
<ComboBoxItem>20</ComboBoxItem>  
</ribbon:RibbonComboBox>  
<ribbon:RibbonButton Command="EditingCommands.IncreaseFontSize" />  
<ribbon:RibbonButton Command="EditingCommands.DecreaseFontSize" />  
<ribbon:RibbonButton Command="EditingCommands.ToggleBold" /> 
 <ribbon:RibbonButton Command="EditingCommands.ToggleItalic" />  
 <ribbon:RibbonButton Command="EditingCommands.ToggleUnderline" /> 
 <ribbon:RibbonButton SmallIcon="/SampleImages/Strike.png" Click="OnStrikeThrough"/>  
 <ribbon:RibbonButton Command="EditingCommands.ToggleSubscript" />  
 <ribbon:RibbonButton Command="EditingCommands.ToggleSuperscript" />  
 <ribbon:RibbonButton SmallIcon="/SampleImages/FontColor.png"/>  
 <ribbon:RibbonButton SmallIcon="/SampleImages/TextHighlight.png"/>
 </ribbon:MiniToolbar>
{% endhighlight %}

{% highlight C# %}

[C#]
private MiniToolbar toolBar;
toolBar = FindResource("MiniToolbar") as MiniToolbar;
toolBar.PlacementTarget = Editor;
private void Editor_MouseUp( object sender, MouseButtonEventArgs e )
{
Debug.WriteLine( "MouseUP" );
if ( !Editor.Selection.IsEmpty ) 			
toolBar.Show();else    		
toolBar.Hide();
}
{% endhighlight %}


![](MiniToolbar_images/MiniToolbar_img1.jpeg)




