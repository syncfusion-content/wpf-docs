---
layout: post
title: MinimizedHeaderTemplate--MaximizedHeaderTemplate
description: minimizedheadertemplate / maximizedheadertemplate
platform: wpf
control: TileView Control
documentation: ug
---

# MinimizedHeaderTemplate / MaximizedHeaderTemplate

The MinimizedHeaderTemplate and MaximizedHeaderTemplate feature in the TileViewControl enables you to set the different templates for header in the TileViewItem maximized state and TileViewItem minimized state. The HeaderTemplate property will be used to set the template for header in the TileViewItem Normal state. If you set the MinimizedHeaderTemplate, then the value in HeaderTemplate property will be displayed in maximized state and vice versa.

Use Case Scenarios

This feature will be very useful when you want to show two different DataTemplates for header in minimized state and maximized state.

Adding MinimizedHeaderTemplate / MaximizedHeaderTemplate to an Application 

The MinimizedHeaderTemplate and MaximizedHeaderTemplate can be added to an application by either using XAML or C# code.

The following code example illustrates how to add the MinimizedHeaderTemplate and MaximizedHeaderTemplate to an application through XAML.



[XAML]



&lt;DataTemplate x:Name="NormalHeader"&gt;

     &lt;StackPanel Orientation="Horizontal"&gt;

          &lt;Image Source="Images/messages.png"/&gt;

          <TextBlock Text="{Binding Name}" FontFamily="Verdana" 

                     FontSize="18" Foreground="Blue"/>                      

     &lt;/StackPanel&gt;

&lt;/DataTemplate&gt;

&lt;DataTemplate x:Name="MinHeader"&gt;

     &lt;StackPanel Orientation="Horizontal"&gt;

           &lt;Image Source="Images/Email.png"/&gt;

           <TextBlock Text="{Binding Name}" FontFamily="Verdana" 

                      FontSize="18" Foreground="Green" 

                      TextTrimming="WordEllipsis"/>                                        

     &lt;/StackPanel&gt;

&lt;/DataTemplate&gt;

&lt;DataTemplate x:Name="MaxHeader"&gt;

     &lt;StackPanel Orientation="Horizontal"&gt;

           &lt;Image Source="Images/phonelist.png"/&gt;

           <TextBlock Text="{Binding Dept}" FontFamily="Verdana" 

                      FontSize="18" Foreground="White"/>                    

     &lt;/StackPanel&gt;

&lt;/DataTemplate&gt;



<syncfusion:TileViewControl x:Name="TileView1" Width="600" Height="400"

     ItemsSource="{Binding TileViewItemData, ElementName=Tile}"

     MinimizedHeaderTemplate="{Binding Source={StaticResource MinHeader}}"                          

     MaximizedHeaderTemplate="{Binding Source={StaticResource MaxHeader}}" 

     HeaderTemplate="{Binding Source={StaticResource NormalHeader}}">  

&lt;/syncfusion:TileViewControl&gt;





{ ![](MinimizedHeaderTemplate--MaximizedHeaderTemplate_images/MinimizedHeaderTemplate--MaximizedHeaderTemplate_img1.png) | markdownify }
{:.image }




{ ![](MinimizedHeaderTemplate--MaximizedHeaderTemplate_images/MinimizedHeaderTemplate--MaximizedHeaderTemplate_img2.png) | markdownify }
{:.image }




Properties

_MinimizedHeaderTemplate / MaximizedHeaderTemplate Properties Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
MinimizedHeaderTemplate</td><td>
Specifies the template for header that can be used to set when the TileViewItem is in Minimized state.</td><td>
DependencyProperty</td><td>
DataTemplate</td><td>
</td></tr>
<tr>
<td>
MaximizedHeaderTemplate</td><td>
Specifies the template for header that can be used to set when the TileViewItem is in Maximized state.</td><td>
DependencyProperty</td><td>
DataTemplate</td><td>
</td></tr>
</table>


Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



