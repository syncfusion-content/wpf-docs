---
layout: post
title: Expand/Collapse Images in WPF Wizard Control control | Syncfusion
description: Learn here all about Expand/Collapse Images support in Syncfusion WPF TreeViewAdv (Classic) control and more.
platform: wpf
control: TreeViewAdv
 documentation: ug
---
# Expand/Collapse Images in WPF TreeViewAdv (Classic)

The tree nodes in TreeViewAdv control can have sub nodes or items. On clicking the parent node, it expands to show child nodes. Hence, the nodes switch between collapsed and expanded states, on mouse-click. TreeViewAdv control lets you specify separate images for the expanded and collapsed nodes. You can add images to the TreeViewItemAdv to indicate the state of an item by using the ExpandedImageSource and CollapsedImageSource properties. Images are displayed based on the state of the item.

The following are the two possible states for any item:

* Expanded
* Collapsed

The Expanded state is identified by setting the ExpandedImageSource property and the Collapsed state is identified by setting the CollapsedImageSource property as follows.

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv >
<syncfusion:TreeViewItemAdv Header="My Computer" x:Name="item1" CollapsedImageSource="folder.png">
<syncfusion:TreeViewItemAdv Header="Music" />
<syncfusion:TreeViewItemAdv Header="Videos"  />
<syncfusion:TreeViewItemAdv Header="Wallpaper.png" />
<syncfusion:TreeViewItemAdv Header="Banner.png"  />
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="My Network Places" x:Name="item2" ExpandedImageSource="Folder_Expanded.png" >
<syncfusion:TreeViewItemAdv Header="Sever"  />
<syncfusion:TreeViewItemAdv Header="My Folders" />
<syncfusion:TreeViewItemAdv Header="Image1.png" />
<syncfusion:TreeViewItemAdv Header="Image2.png" />
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

// Set image for collapsed button
item1.CollapsedImageSource = new BitmapImage(new Uri("/folder.png", UriKind.Relative));

// Set image for expand button
item2.ExpandedImageSource = new BitmapImage(new Uri("/Folder_Expanded.png", UriKind.Relative));

{% endhighlight %}

{% highlight VB %}

' Set image for collapsed button
item1.CollapsedImageSource = New BitmapImage(New Uri("/folder.png", UriKind.Relative))

' Set image for expand button
item2.ExpandedImageSource = New BitmapImage(New Uri("/Folder_Expanded.png", UriKind.Relative))

{% endhighlight %}

{% endtabs %}  

![setting image for expand and collapse button](Expand_Collapse_images_images/Expand_Collapse_images_img1.jpeg)
