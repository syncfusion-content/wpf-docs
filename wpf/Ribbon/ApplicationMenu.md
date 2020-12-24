---
layout: post
title: ApplicationMenu | WindowsForms | Syncfusion
description: This section briefly describes the functionalities of Application Menu support in Syncfusion Ribbon control for WPF.
platform: wpf
control: Ribbon
documentation: ug
---

# Application Menu in WPF Ribbon

The [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html) can be added by using [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html#Syncfusion_Windows_Tools_Controls_Ribbon_ApplicationMenu) property of Ribbon. To show the [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html), click the **FILE** button in Ribbon like in Microsoft Outlook.

The [`IsPopupOpen`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_IsPopupOpen) boolean property is used to show the [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html) while launching itself.

N> The [`BackStage`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.Ribbon.html#Syncfusion_Windows_Tools_Controls_Ribbon_BackStage) is not applicable when the ApplicationMenu is needed.

## Adding MenuItems in ApplicationMenu

[`MenuItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_MenuItems) are displayed in right of the [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html). Different [`MenuItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_MenuItems) are added to an application menu using its [`MenuItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_MenuItems) property.

## Adding ApplicationItems in ApplicationMenu

[`ApplicationItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_ApplicationItems) are displayed in bottom of the [`ApplicationMenu`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html). Different [`ApplicationItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_ApplicationItems) are added to an application menu using its [`ApplicationItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.ApplicationMenu.html#Syncfusion_Windows_Tools_Controls_ApplicationMenu_ApplicationItems) property.

 {% tabs %}

 {% highlight XAML %}

<syncfusion:Ribbon.ApplicationMenu>
    <syncfusion:ApplicationMenu
        Name="_applicationMenu"
        Width="38"
        Height="38"
        IsBelowAppButton="True"
        syncfusion:Ribbon.KeyTip="F"
        ApplicationButtonImage="/ApplicationMenu;component/Assets/Ribbon/App.ico"
        IsPopupOpen="False">
        <syncfusion:RibbonButton
            Width="200"
            Height="30"
            Label="New"
            SizeForm="Small"
            Command="local:RibbonCommand.ButtonCommand"
            IconTemplate="{StaticResource New}"/>
        <syncfusion:RibbonButton
            Width="200"
            Height="30"
            Command="local:RibbonCommand.OpenCommand"
            Label="Open"
            SizeForm="Small" 
            SmallIcon="/ApplicationMenu;component/Assets/Ribbon/Open32.png"/>
        <syncfusion:SplitMenuButton
            Width="200"
            Height="30"
            Label="Save As"
            Icon="/ApplicationMenu;component/Assets/Ribbon/Save_20.png">
            <syncfusion:ApplicationMenuGroup Header="Save in another format" IconBarEnabled="False">
                <syncfusion:RibbonButton
                    Height="30"
                    Label="DOC Files"
                    SizeForm="Small"
                    Command="local:RibbonCommand.SaveAsCommand"
                    IconTemplate="{StaticResource DOC}"/>
                <syncfusion:RibbonButton
                    Height="30"
                    Label="PDF Files"
                    SizeForm="Small"
                    Command="local:RibbonCommand.SaveAsCommand"
                    IconTemplate="{StaticResource PDF}"/>
                <syncfusion:RibbonButton
                    Height="30"
                    Label="XLS Files"
                    SizeForm="Small"
                    Command="local:RibbonCommand.SaveAsCommand"
                    IconTemplate="{StaticResource XLS}"/>
                <syncfusion:RibbonButton
                    Height="30"
                    Label="ZIP Files"
                    SizeForm="Small"
                    Command="local:RibbonCommand.SaveAsCommand"
                    IconTemplate="{StaticResource ZIP}"/>
            </syncfusion:ApplicationMenuGroup>
        </syncfusion:SplitMenuButton>
        <syncfusion:RibbonButton
            Width="200"
            Height="30"
            Label="Security"
            SizeForm="Small"
            Command="local:RibbonCommand.ButtonCommand"
            IconTemplate="{StaticResource Security}"/>
        <Separator />
        <syncfusion:RibbonButton
            Width="200"
            Height="30"
            Label="Share"
            Command="local:RibbonCommand.ButtonCommand"
            SizeForm="Small"
            IconTemplate="{StaticResource Sharing}"/>
        <syncfusion:ApplicationMenu.MenuItems>
            <TextBlock MinWidth="300" FontWeight="Bold">Create New Outlook Item</TextBlock>
            <Separator />
            <syncfusion:SimpleMenuButton Label="Recent Document lists" Command="local:RibbonCommand.ButtonCommand" IconTemplate="{StaticResource Copy}"/>
            <syncfusion:SimpleMenuButton Label="Document lists" Command="local:RibbonCommand.ButtonCommand" IconTemplate="{StaticResource OnePage}"/>
        </syncfusion:ApplicationMenu.MenuItems>
        <syncfusion:ApplicationMenu.ApplicationItems>
            <syncfusion:ButtonAdv
                Background="Transparent"
                Label="Options"
                SizeMode="Normal"
                Command="local:RibbonCommand.ButtonCommand"
                SmallIcon="/ApplicationMenu;component/Assets/Ribbon/Display.png"/>
            <syncfusion:ButtonAdv
                Background="Transparent"
                Label="Close"
                SizeMode="Normal"
                Command="{Binding ApplicationMenuCommand}"
                IconTemplate="{StaticResource CloseTab}"/>
        </syncfusion:ApplicationMenu.ApplicationItems>
    </syncfusion:ApplicationMenu>
</syncfusion:Ribbon.ApplicationMenu>

 {% endhighlight %}

 {% endtabs %}

![Application menu in WPF Ribbon](ApplicationMenu-images/ApplicationMenu.png)

N> View [sample](https://github.com/SyncfusionExamples/How-to-set-application-menu-in-Ribbon) in GitHub.