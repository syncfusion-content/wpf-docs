---
layout: post
title: Header and Footer in WPF Navigation Drawer control | Syncfusion
description: Learn here all about Header and Footer support in Syncfusion WPF Navigation Drawer (SfNavigationDrawer) control and more.
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Header and Footer in WPF Navigation Drawer (SfNavigationDrawer)

The Navigation menu's header and footer parts are fully customizable. This section explains the customization of header and footer. 

## Customizing the Toggle button and Header

The Navigation Drawer built-in toggle button and header can be customized using the [ToggleButtonContentTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ToggleButtonContentTemplate), [ToggleButtonIconTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_ToggleButtonIconTemplate), [IsToggleButtonVisible](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_IsToggleButtonVisible) properties.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Expanded">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M32.032381, 16.445429 L25.410999, 23 22.598995, 23 15.853724, 16.561278 3.4150009, 29 44.586115, 29z M2.0000003, 3.3371553 L2.0000003, 27.587 14.406845, 15.180154z M46.000002, 2.6187388 L33.45355, 15.038597 46.000002, 27.585888z M3.4950623, 2.0000003 L23.399998, 21 24.589001, 21 43.782564, 2.0000003z M0, 0 L48.000002, 0 48.000002, 31 0, 31z" ..... />
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.5189972,7.3780194C8.3389893,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M22.133972,14.194015C17.582977,14.194015,13.821991,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.4614787,7.2521966C8.897512,7.2521966 8.3335462,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M42.128046,6.7269681 L18.53705,30.317964 25.278003,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Important">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,18.675001 6.3710022,.../>
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Work">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M16.151009,4.5999908C16.851023,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Personal">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M12.200012,21.899996L13.099976,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M6.9999996,48.353 L19,48.353 19,..../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ToggleButtonIconTemplate>
            <DataTemplate>
                <Image
                    x:Name="image"
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Stretch"
                    VerticalAlignment="Stretch"
                    Source="People.png" />
            </DataTemplate>
        </syncfusion:SfNavigationDrawer.ToggleButtonIconTemplate>
        <syncfusion:SfNavigationDrawer.ToggleButtonContentTemplate>
            <DataTemplate>
                <Label
                    HorizontalAlignment="Left"
                    VerticalAlignment="Center"
                    Content="Johnson Martin" />
            </DataTemplate>
        </syncfusion:SfNavigationDrawer.ToggleButtonContentTemplate>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% endtabs %}

![Header](Header_and_Footer_images/Header.png)

## Customizing the Footer

The Navigation Drawer's Footer can be customized using the [FooterItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_FooterItems) property. `FooterItems` can be loaded with NavigationItem collection. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfNavigationDrawer x:Name="navigationDrawer" DisplayMode="Expanded">
        <syncfusion:NavigationItem Header="Inbox">
            <syncfusion:NavigationItem.Icon>
                <Path
                    Data="M32.032381, 16.445429 L25.410999, 23 22.598995,.../>
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Primary">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Data="M9.5189972,7.3780194C8.3389893,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Social">
                <syncfusion:NavigationItem.Icon>
                    <Path
                        Data="M22.133972,14.194015C17.582977,14.194015,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Promotions">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M9.4614787,7.2521966C8.897512,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Sent mail">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M42.128046,6.7269681 L18.53705,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Important">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M25.085007,5.9780004 L20.577011,.../>
            </syncfusion:NavigationItem.Icon>
            <syncfusion:NavigationItem Header="Work">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M16.151009,4.5999908C16.851023,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
            <syncfusion:NavigationItem Header="Personal">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M12.200012,21.899996L13.099976,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:NavigationItem>
        <syncfusion:NavigationItem Header="Drafts">
            <syncfusion:NavigationItem.Icon>
                <Path Data="M6.9999996,48.353 L19,48.353 19,.../>
            </syncfusion:NavigationItem.Icon>
        </syncfusion:NavigationItem>
        <syncfusion:SfNavigationDrawer.ToggleButtonIconTemplate>
            <DataTemplate>
                <Image
                    x:Name="image"
                    Width="25"
                    Height="25"
                    HorizontalAlignment="Stretch"
                    VerticalAlignment="Stretch"
                    Source="People.png" />
            </DataTemplate>
        </syncfusion:SfNavigationDrawer.ToggleButtonIconTemplate>
        <syncfusion:SfNavigationDrawer.ToggleButtonContentTemplate>
            <DataTemplate>
                <Label 
                    HorizontalAlignment="Left"
                    VerticalAlignment="Center"
                    Content="Johnson Martin"
                    FontWeight="Bold" />
            </DataTemplate>
        </syncfusion:SfNavigationDrawer.ToggleButtonContentTemplate>
        <syncfusion:SfNavigationDrawer.FooterItems>
            <syncfusion:NavigationItem Header="LogOut" SelectionBackground="Transparent">
                <syncfusion:NavigationItem.Icon>
                    <Path Data="M13.999999,3.9500002 L13.999999,.../>
                </syncfusion:NavigationItem.Icon>
            </syncfusion:NavigationItem>
        </syncfusion:SfNavigationDrawer.FooterItems>
        <syncfusion:SfNavigationDrawer.ContentView>
            <Label
                Width="150"
                Height="30"
                HorizontalAlignment="Center"
                VerticalAlignment="Center"
                Content="Content View" />
        </syncfusion:SfNavigationDrawer.ContentView>
    </syncfusion:SfNavigationDrawer>

{% endhighlight %}

{% endtabs %}

![Footer](Header_and_Footer_images/Footer.png)

## Creating a custom header and footer

The header and footer part can also be customized by loading a custom view. This can be achieved in `Default` display mode. Using the [DrawerFooterView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_DrawerHeaderView) and [DrawerFooterView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.NavigationDrawer.SfNavigationDrawer.html#Syncfusion_UI_Xaml_NavigationDrawer_SfNavigationDrawer_DrawerFooterView) properties, custom views can be loaded to the header and footer.

See also [Custom views](https://help.syncfusion.com/wpf/navigation-drawer/custom-views) section for creating a custom navigation menu.


N> View [sample](https://github.com/SyncfusionExamples/wpf-sfnavigationdrawer-samples/tree/main/Header_and_Footer) in GitHub

