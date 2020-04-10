---
layout: post
title: Resizing Dropdown | Split Button Control | WPF | Syncfusion
description: This section explores how to resize the popup using a resizing gripper to increase or decrease the height of the popup.
platform: WPF
control: SplitButtonAdv
documentation: ug
---

# Resizing dropdown in WPF Split Button (SplitButtonAdv)

The dropdown menu group popup height can be increased or decreased using the resizing gripper. One can enable the resizing behavior by setting the [IsResizable](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownMenuGroup~IsResizable.html) property to **true**.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SplitButtonAdv Label="Colors" x:Name="splitbutton" SmallIcon="images\colors.png">
        <syncfusion:DropDownMenuGroup IsResizable=”True”>
            <syncfusion:DropDownMenuItem HorizontalAlignment="Left" Header="Orange">
                <syncfusion:DropDownMenuItem.Icon>
                    <Image Source="images\orange.png"/>
                </syncfusion:DropDownMenuItem.Icon>
            </syncfusion:DropDownMenuItem>
            <syncfusion:DropDownMenuItem HorizontalAlignment="Left" Header="Sky Blue">
                <syncfusion:DropDownMenuItem.Icon>
                    <Image Source="images\skyblue.png"/>
                </syncfusion:DropDownMenuItem.Icon>
            </syncfusion:DropDownMenuItem>
            <syncfusion:DropDownMenuItem HorizontalAlignment="Left" Header="Red">
                <syncfusion:DropDownMenuItem.Icon>
                    <Image Source="images\red.png"/>
                </syncfusion:DropDownMenuItem.Icon>
            </syncfusion:DropDownMenuItem>
        </syncfusion:DropDownMenuGroup>
    </syncfusion:SplitButtonAdv>

{% endhighlight %}
{% highlight c# %}

    SplitButtonAdv splitbutton = new SplitButtonAdv();
    DropDownMenuGroup menu = new DropDownMenuGroup();
    DropDownMenuItem Item1 = new DropDownMenuItem() { Header="Orange", Icon =new BitmapImage(new Uri("images\orange.png")), HorizontalAlignment="Left"};
    DropDownMenuItem Item2 = new DropDownMenuItem() { Header ="Sky Blue", Icon =new BitmapImage(new Uri("images\skyblue.png")), HorizontalAlignment="Left"};
    DropDownMenuItem Item3 = new DropDownMenuItem() { Header ="Red", Icon =new BitmapImage(new Uri("images\red.png")), HorizontalAlignment="Left"};
    menu.Items.Add(Item1);
    menu.Items.Add(Item2);
    menu.Items.Add(Item3);
    menu.IsResizable = true;
    splitbutton.Content = menu;
    splitbutton.Label = "Colors";
    splitbutton.SmallIcon = new BitmapImage(new Uri("images\colors.png"));

{% endhighlight %}
{% endtabs %}

![Resizing](Resizing-Support_images/Resizing-Support_img1.png)



