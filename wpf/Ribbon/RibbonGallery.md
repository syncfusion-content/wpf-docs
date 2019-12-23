---
layout: post
title: RibbonGallery in Syncfusion Ribbon control
description: This section breifly describes the functions of RibbonGallery in Syncfusion's Ribbon control for WPF
platform: wpf
control: Ribbon
documentation: ug
---
# RibbonGallery

RibbonGallery provides `VisualMode` property, that helps to display items in two different ways.


## Ribbon mode

To display items as a normal gallery control in the ribbon, set `VisualMode` property as `InRibbon mode`

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonGallery Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png"/>

{% endhighlight %}

{% endtabs %}

![InRibbon Visual mode of Ribbon Gallery](RibbonGallery_images/RibbonGallery_img1.jpg)


## DropDown mode

To display items as DropDown in the ribbon, set `VisualMode` property as `DropDown mode`

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonGallery VisualMode="DropDown" Label="RibbonGallery" LargeIcon="Word.png" >

{% endhighlight %}

{% endtabs %}

![DropDown Visual mode of Ribbon Gallery](RibbonGallery_images/RibbonGallery_img2.jpg)


## Ribbon gallery item

Ribbon control provides `RibbonGalleryItem` that add as items in RibbonGallery.


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">          
<syncfusion:RibbonTab Caption="HOME" IsChecked="False"/>                
<syncfusion:RibbonTab IsChecked="True" Caption="DESIGN">
<syncfusion:RibbonBar Header="RibbonBar">
<syncfusion:RibbonGallery Name="_ribbonGallery" Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png" >
<syncfusion:RibbonGalleryItem>
<Image Source="OrangeLarge.png"/>
</syncfusion:RibbonGalleryItem>
<syncfusion:RibbonGalleryItem  >
<Image Source="BlueLarge.png"/>
</syncfusion:RibbonGalleryItem>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
/syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Add RibbonGalleryItem in code behind.

{% tabs %}

{% highlight C# %}

Image _image1 = new Image() { Source =new BitmapImage(new Uri(@"OrangeLarge.png", UriKind.RelativeOrAbsolute)) };
Image _image2 = new Image() { Source = new BitmapImage(new Uri(@"BlueLarge.png", UriKind.RelativeOrAbsolute)) };
RibbonGalleryItem _ribbonGalleryItem1 = new RibbonGalleryItem() {Content=_image1};
RibbonGalleryItem _ribbonGalleryItem2 = new RibbonGalleryItem() { Content = _image2 };
_ribbonGallery.Items.Add(_ribbonGalleryItem1);
_ribbonGallery.Items.Add(_ribbonGalleryItem2);

{% endhighlight %}
{% highlight VB %}

Dim _image1 As New Image() With {.Source = New BitmapImage(New Uri("OrangeLarge.png", UriKind.RelativeOrAbsolute))}
Dim _image2 As New Image() With {.Source = New BitmapImage(New Uri("BlueLarge.png", UriKind.RelativeOrAbsolute))}
Dim _ribbonGalleryItem1 As New RibbonGalleryItem() With {.Content=_image1}
Dim _ribbonGalleryItem2 As New RibbonGalleryItem() With {.Content = _image2}
_ribbonGallery.Items.Add(_ribbonGalleryItem1)
_ribbonGallery.Items.Add(_ribbonGalleryItem2)

{% endhighlight %}

{% endtabs %}

![Items in the RibbonGallery](RibbonGallery_images/RibbonGallery_img3.jpg)


## Ribbon gallery group

Ribbon Gallery Group is a collection of Ribbon Gallery Items. The items are grouped in the Ribbon Gallery control based on some classifications.

### Gallery filter

`GalleryGroupFilters` are used to view particular group. The `FilterIndexes` property is used to specify the indexes of the filters.


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME" IsChecked="False"/>
<syncfusion:RibbonTab Caption="DESIGN" IsChecked="True">
<syncfusion:RibbonBar Width="250" Header="RibbonBar">
<syncfusion:RibbonGallery Name="_ribbonGallery" Width="230" VisualMode="DropDown" Label="RibbonGallery">
<syncfusion:RibbonGallery.GalleryFilters>
<syncfusion:RibbonGalleryFilter Label="All"/>
<syncfusion:RibbonGalleryFilter Label="Group 1"/>
<syncfusion:RibbonGalleryFilter Label="Group 2"/>
</syncfusion:RibbonGallery.GalleryFilters>
<syncfusion:RibbonGallery.GalleryGroups>
<syncfusion:RibbonGalleryGroup Name="_ribbonGalleryGroup1" Label="Group 1" syncfusion:RibbonGallery.FilterIndexes="0, 1">
<syncfusion:RibbonGalleryItem Name="_ribbonGalleryItem1" Margin="5">
<Image Source="OrangeLarge.png" Stretch="None" />
</syncfusion:RibbonGalleryItem>
<syncfusion:RibbonGalleryItem Name="_ribbonGalleryItem2" Margin="5" >
<Image Source="BlueLarge.png" Stretch="None"/>
</syncfusion:RibbonGalleryItem>
</syncfusion:RibbonGalleryGroup>
<syncfusion:RibbonGalleryGroup  Name="_ribbonGalleryGroup2"  Label="Group 2" syncfusion:RibbonGallery.FilterIndexes="0, 2">
<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem3"  Margin="5">
<Image Source="GreenLarge.png" Stretch="None"/>
</syncfusion:RibbonGalleryItem>
<syncfusion:RibbonGalleryItem Name="_RibbonGalleryItem4" Margin="5" >
<Image Source="PinkLarge.png" Stretch="None" />
</syncfusion:RibbonGalleryItem>
</syncfusion:RibbonGalleryGroup>
</syncfusion:RibbonGallery.GalleryGroups>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![Groups in the RibbonGallery](RibbonGallery_images/RibbonGallery_img4.jpg)


## Add custom menu items

In the expanded Gallery items (in both the Visual Mode), can add custom menu items to the bottom of the Ribbon Gallery control, using the `MenuItem` property of RibbonGallery.


{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">           
<syncfusion:RibbonTab Caption="HOME" IsChecked="True"/>
<syncfusion:RibbonTab IsChecked="False" Caption="DESIGN">
<syncfusion:RibbonBar Width="250" Header="RibbonBar">
<syncfusion:RibbonGallery Name="_ribbonGallery" Width="230" VisualMode="InRibbon" Label="RibbonGallery" LargeIcon="Word.png" >
<syncfusion:RibbonGalleryItem  Margin="5">
<Image Source="OrangeLarge.png"/>
</syncfusion:RibbonGalleryItem>
<syncfusion:RibbonGalleryItem  Margin="5">
<Image Source="PinkLarge.png"/>
</syncfusion:RibbonGalleryItem>
<syncfusion:RibbonGallery.MenuItems>
<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-1"/>
<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-2"/>
<syncfusion:RibbonButton SizeForm = "Small" Label="Menu Item-3"/>
</syncfusion:RibbonGallery.MenuItems>              
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

Custom Menu items of RibbonGallery added by creating instance of RibbonButton and add it to MenuItems property of RibbonGallery in code behind. SplitButton or MenuButton can also added instead of RibbonButton.

{% tabs %}

{% highlight C# %}

RibbonButton _ribbonButton1 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-1" };
RibbonButton _ribbonButton2 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-2" };
RibbonButton _ribbonButton3 = new RibbonButton() { SizeForm = SizeForm.Small, Label = "Menu Item-3" };
_ribbonGallery.MenuItems.Add(_ribbonButton1);
_ribbonGallery.MenuItems.Add(_ribbonButton2);
_ribbonGallery.MenuItems.Add(_ribbonButton3);

{% endhighlight %}

{% highlight VB %}

Dim _ribbonButton1 As New RibbonButton() With {
	.SizeForm = SizeForm.Small,
	.Label = "Menu Item-1"
}
Dim _ribbonButton2 As New RibbonButton() With {
	.SizeForm = SizeForm.Small,
	.Label = "Menu Item-2"
}
Dim _ribbonButton3 As New RibbonButton() With {
	.SizeForm = SizeForm.Small,
	.Label = "Menu Item-3"
}
_ribbonGallery.MenuItems.Add(_ribbonButton1)
_ribbonGallery.MenuItems.Add(_ribbonButton2)
_ribbonGallery.MenuItems.Add(_ribbonButton3)

{% endhighlight %}

{% endtabs %}

![Custom menu items in RibbonGallery](RibbonGallery_images/RibbonGallery_img5.jpg)

## Add custom context menu

Context menu is a kind of menu that appears when a right-click operation is performed on the target control. `RibbonGallery` and `RibbonGalleryItem`’s allows us to create a set of custom commands or options by setting RibbonContextMenu to its ContextMenu property. This will override the built-in context menu of the RibbonGallery and its items.

{% tabs %}
{% highlight XAML %}
<syncfusion:RibbonWindow.Resources>
    <syncfusion:RibbonContextMenu x:Key="galleryContextMenu" ItemsSource="{Binding}">
        <syncfusion:RibbonMenuItem Header="Apply Style" IconBarEnabled="True"/>
        <syncfusion:RibbonMenuItem Header="Remove from Style Gallery" IconBarEnabled="True"/>
        <Separator />
        <syncfusion:RibbonMenuItem Header="Minimize Ribbon" IconBarEnabled="True" Click="MinimizeRibbonItem_Click" />
    </syncfusion:RibbonContextMenu>
</syncfusion:RibbonWindow.Resources>
<Grid>
    <syncfusion:Ribbon Name="_ribbon" HorizontalAlignment="Stretch" VerticalAlignment="Top">
        <syncfusion:RibbonTab Caption="HOME" IsChecked="False"/>
        <syncfusion:RibbonTab IsChecked="True" Caption="DESIGN">
            <syncfusion:RibbonBar Header="RibbonBar">
                <syncfusion:RibbonGallery x:Name="gallery" ContextMenu="{DynamicResource galleryContextMenu}"
                                          Width="380" SizeForm="Large" Height="67"  ItemHeight="60"  ItemWidth="60" MenuIconBarEnabled="True">
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock TextAlignment="Center" Margin="0,9,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,11,0,0" Text="Normal"/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock TextAlignment="Center" Margin="0,9,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,11,0,0" Text="No Spa.."/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock FontSize="18" Foreground="DarkBlue" TextAlignment="Center" Margin="0,5,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,6,0,0" Text="Heading 1"/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock FontSize="16" Foreground="DarkBlue" TextAlignment="Center" Margin="0,6,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,8,0,0" Text="Heading 2"/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock FontSize="14" Foreground="DarkBlue" TextAlignment="Center" Margin="0,7,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,9,0,0" Text="Heading 3"/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                    <syncfusion:RibbonGalleryItem Margin="2" CheckOnClick="False">
                        <StackPanel>
                            <TextBlock FontSize="15" Foreground="DarkBlue" TextAlignment="Center" Margin="0,7,0,0" Text="AaBbCc"/>
                            <TextBlock TextAlignment="Center" Margin="0,9,0,0" Text="Heading 4"/>
                        </StackPanel>
                    </syncfusion:RibbonGalleryItem>
                </syncfusion:RibbonGallery>
            </syncfusion:RibbonBar>
        </syncfusion:RibbonTab>
    </syncfusion:Ribbon>
</Grid>

{% endhighlight %}
{% endtabs %}

![Separate Ribbon context menu for the Gallery and its items](RibbonGallery_images/RibbonGalleryContextMenu.png)


