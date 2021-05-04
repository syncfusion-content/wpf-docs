---
layout: post
title: Images for items in TreeViewAdv in WPF Wizard Control control | Syncfusion
description: Learn here all about Images for items in TreeViewAdv support in Syncfusion WPF TreeViewAdv (Classic) control and more.
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Images for items in TreeViewAdv in WPF TreeViewAdv (Classic)

## Node image

To add images to the left and right corner of the TreeViewItemAdv by using the LeftImageSource and RightImageSource properties of the TreeViewItemAdv class.

* LeftImageSource—this is a dependency property, which gets or sets ImageSource to left image.
* RightImageSource—this is dependency property, which gets or sets RightSource to right image.

{% tabs %}

{% highlight XAML %}
<syncfusion:TreeViewAdv >
<syncfusion:TreeViewItemAdv x:Name="item1" Header="Windows Explorer" LeftImageSource="Folder_Expanded.png"  >
<syncfusion:TreeViewItemAdv Header="My Computer" x:Name="item2" LeftImageSource="Folder_Expanded.png" RightImageSource="Right tick.png" >
<syncfusion:TreeViewItemAdv Header="Music"  />
<syncfusion:TreeViewItemAdv Header="Videos"  />
<syncfusion:TreeViewItemAdv Header="Wallpaper.png"  />
<syncfusion:TreeViewItemAdv Header="Banner.png"  />
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="My Network Places"  >
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//Set image for left
item1.LeftImageSource = new BitmapImage(new Uri("/Folder_Expanded.png", UriKind.RelativeOrAbsolute));

//Set image for right
item2.RightImageSource = new BitmapImage(new Uri("/Right tick.png", UriKind.RelativeOrAbsolute));

{% endhighlight %}

{% highlight VB %}

'Set image for left
item1.LeftImageSource = New BitmapImage(New Uri("/Folder_Expanded.png", UriKind.RelativeOrAbsolute))

'Set image for right
item2.RightImageSource = New BitmapImage(New Uri("/Right tick.png", UriKind.RelativeOrAbsolute))

{% endhighlight %}

{% endtabs %}  


![load images to TreeViewAdv items](Images_for_items_in_TreeViewAdv_images/Images_for_items_in_TreeViewAdv_img1.jpeg)


## Customize image size in TreeViewItemAdv

TreeViewAdv allow user to set the height and width of the TreeViewItemAdv images. The ImageHeight property sets the height of the image and the ImageWidth property sets the width of the images. The default value of the properties is __NaN__. Here is the code for setting these properties.

{% tabs %}

{% highlight XAML %}

<syncfusion:TreeViewAdv >
<syncfusion:TreeViewItemAdv x:Name="item1" ImageHeight="25" ImageWidth="25" Header="Windows Explorer" LeftImageSource="Folder_Expanded.png"  >
<syncfusion:TreeViewItemAdv Header="My Computer" x:Name="item2"  LeftImageSource="Folder_Expanded.png" RightImageSource="Right tick.png" >
<syncfusion:TreeViewItemAdv Header="Music"  />
<syncfusion:TreeViewItemAdv Header="Videos"  />
<syncfusion:TreeViewItemAdv Header="Wallpaper.png"  />
<syncfusion:TreeViewItemAdv Header="Banner.png"  />
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="My Network Places"  >
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewItemAdv>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

//Set image height
item1.ImageHeight = 25;

//Set image width
item1.ImageWidth = 25;

{% endhighlight %}

{% highlight VB %}

'Set image height
item1.ImageHeight = 25

'Set image width
item1.ImageWidth = 25

{% endhighlight %}

{% endtabs %}  

![Customize image size in TreeViewItemAdv](Images_for_items_in_TreeViewAdv_images/Images_for_items_in_TreeViewAdv_img2.jpeg)
