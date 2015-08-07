---
layout: post
title: ScrollBar-Support
description: scrollbar support
platform: wpf
control: TileView Control
documentation: ug
---

# ScrollBar Support

The ScrollBar will be visible in the bottom of the TileViewControl, when the width of the Minimized TileViewItem increases and also when MinimizedItemsOrientation of the TileViewControl is set to top or bottom. The ScrollBar will be visible in the right side of the TileViewControl, when the height of the Minimized TileViewItem increases and also when MinimizedItemsOrientation of the TileViewControl is set to right or left. 

## Use Case Scenarios

ScrollBar support enables you to see all the minimized TileViewItems, if the total height and width of the minimized TileViewItems increases from the actual control height.

## Adding ScrollBar Support to an Application 

The following code example illustrates how to add the ScrollBar to an application.


{% highlight xml %}
[XAML]



<syncfusion:TileViewControl x:Name="TileView1" Background="White">

       <syncfusion:TileViewItem BorderThickness="2" Header="TileViewItem 1"                                         

               Content="TileViewContent" OnMinimizedHeight="200" 

               OnMinimizedWidth="200" Background="LightGray" 

               HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

       <syncfusion:TileViewItem BorderThickness="2" Header="TileViewItem 2"                                          

               Content="TileViewContent" OnMinimizedHeight="200" 

               OnMinimizedWidth="200" Background="LightGray" 

               HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

       <syncfusion:TileViewItem BorderThickness="2" Header="TileViewItem 3" 

               Content="TileViewContent" OnMinimizedHeight="200" 

               OnMinimizedWidth="200" Background="LightGray" 

               HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

       <syncfusion:TileViewItem BorderThickness="2" Header="TileViewItem 4" 

               Content="TileViewContent" OnMinimizedHeight="200" 

               OnMinimizedWidth="200" Background="LightGray" 

               HeaderBackground="Gray" Margin="2" CornerRadius="3"/>

</syncfusion:TileViewControl>
{% endhighlight %}


![](ScrollBar-Support_images/ScrollBar-Support_img1.png)





![](ScrollBar-Support_images/ScrollBar-Support_img2.png)




## Properties

_Property Table_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }} </td><td>
{{ '**Description**' | markdownify }} </td><td>
{{ '**Type**' | markdownify }} </td><td>
{{ '**Data Type**' | markdownify }} </td><td>
{{ '**Reference links**' | markdownify }} </td></tr>
<tr>
<td>
OnMinimizedHeight</td><td>
Specifies the Height of the MinimizedTileViewItem when the MinimizedItemsOrientation is Right or Left.</td><td>
DependencyProperty</td><td>
0</td><td>
</td></tr>
<tr>
<td>
OnMinimizedWidth</td><td>
Specifies the Width of the MinimizedTileViewItem when the MinimizedItemsOrientation is Top or Bottom.</td><td>
DependencyProperty</td><td>
0</td><td>
</td></tr>
</table>


## Sample Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
2. Select Run Locally Installed Samples in WPF Button.
3. Now expand the DragAndDropManagerDemo tree-view item in the Sample Browser.
4. Choose any one of the samples listed under it to launch. 



