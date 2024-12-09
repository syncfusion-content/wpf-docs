---
layout: post
title: Context menu support for stencil in WPF Diagram control | Syncfusion
description: Learn here all about context menu support for stencil in Syncfusion WPF Diagram (SfDiagram) control ports.
platform: wpf
control: SfDiagram
documentation: ug
---

# Context menu support for Stencil in WPF Diagram (SfDiagram)

Stencil includes some default context menu items to make it easier to execute some frequently used stencil symbol commands.

## Default context menu

Context menu items can be enabled or disabled by adding or removing the `ContextMenu` constraint from
[`StencilConstraints`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.StencilConstraints.html) property. By default, context menu items will be displayed with Cut, Copy, and Paste menu items.

{% highlight C# %}

//Enables the the symbols reordering.
stencil.StencilConstraints |= StencilConstraints.ContextMenu;

//Disables the symbols reordering.
stencil.StencilConstraints &= ~StencilConstraints.ContextMenu;

{% endhighlight %}

![Symbol ContextMenu](Stencil_images/SymbolsContextmenu.png)

## Custom context menu

You can define some additional menu items to the stencil symbols by using [`Menu`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_Menu) property of `Stencil` class. Those additional menu items must be defined and added to [MenuItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Controls.DiagramMenu.html#Syncfusion_UI_Xaml_Diagram_Controls_DiagramMenu_MenuItems) collection.

The following properties should be added to custom context menu items of stencil symbols.

* `Content` - allows you to set Content for the context menu item.
* `Icon` - allows you to set icon for the context menu item.
* `Command` - allows you to define command for context menu item.
* `CommandParameter` - allows you to define command parameter value to execute command for the context menu item.
* `IsSeparator` - allows you to define the horizontal lines that separate the menu items from icon position.

{% highlight C# %}

SfDiagram diagram = new SfDiagram();
Stencil BasicStencil = new Stencil() { ShowDisplayModeToggleButton = false, ShowSearchTextBox = false, ExpandMode = ExpandMode.All, Constraints = StencilConstraints.Default | StencilConstraints.AllowDragDrop };

BasicStencil.SymbolGroups = new SymbolGroups()
{
    new SymbolGroupProvider()
    {
        MappingName = "Key",
    },
};

BasicStencil.Menu = new DiagramMenu()
{
    MenuItems = new ObservableCollection<DiagramMenuItem>()
    {
        new DiagramMenuItem()
        {
            Content = "Cut",
            IsSeparator = true,
            Command = StencilCommands.Cut,
            Icon = @"pack://application:,,,/Icons/Cut.png",
        },

        new DiagramMenuItem()
        {
            Content = "Copy",
            IsSeparator = true,
            Command = StencilCommands.Copy,
            Icon = @"pack://application:,,,/Icons/Copy.png"
        },

        new DiagramMenuItem()
        {
            Content = "Paste",
            IsSeparator = true,
            Command = StencilCommands.Paste,
            CommandParameter = this,
            Icon = @"pack://application:,,,/Icons/Paste.png"
        },

        new DiagramMenuItem()
        {
            Content = "Delete",
            IsSeparator = true,
            Command = StencilCommands.Delete,
            Icon = @"pack://application:,,,/Icons/Delete.png"            
        },

        new DiagramMenuItem()
        {
            Content = "Rename",
            IsSeparator = true,
            Command = RenameCommand,
            Icon = @"pack://application:,,,/Icons/Rename.png",
        },
    },
};

BasicStencil.SymbolSource = new SymbolCollection()
{
    new NodeViewModel()
    {
        UnitWidth = 100,
        UnitHeight = 100,
        Shape = this.Resources["Ellipse"],
        Key = "Basic Shapes",
    },
                      
   new SymbolViewModel()
   {
        Symbol = "Diamond",
        Key = "Basic Shapes",
        SymbolTemplate = this.Resources["Diamond"] as DataTemplate,
    },
};

{% endhighlight %}

![Symbol Custom ContextMenu](Stencil_images/CustomContextMenu.gif)

## Menu for symbols

You can define specific menu items to each stencil symbols by using the `Menu` property of symbols.

{% highlight C# %}

BasicStencil.SymbolSource = new SymbolCollection()
{
    new NodeViewModel()
    {
        UnitWidth = 100,
        UnitHeight = 100,
        Shape = this.Resources["Ellipse"],
        Key = "Basic Shapes",
        Menu = new DiagramMenu()
        {
            MenuItems = new ObservableCollection<DiagramMenuItem>()
            {
                new DiagramMenuItem()
                {
                    Content = "Cut",
                    Command = StencilCommands.Cut,
                    CommandParameter = this,
                    Icon = @"pack://application:,,,/Icons/Cut.png",
                },
            },
        },
    },
                      
    new SymbolViewModel()
    {
        Symbol = "Diamond",
        Key = "Basic Shapes",
        SymbolTemplate = this.Resources["Diamond"] as DataTemplate,
        Menu = new DiagramMenu()
        {
            MenuItems = new ObservableCollection<DiagramMenuItem>()
            {
                new DiagramMenuItem()
                {
                    Content = "Delete",
                    Command = StencilCommands.Delete,
                    CommandParameter = this,
                    Icon = @"pack://application:,,,/Icons/Delete.png",
                },
            },
        },
    },

    new NodeViewModel()
    {
        UnitWidth = 100,
        UnitHeight = 100,
        Shape = this.Resources["Rectangle"],
        Key = "Basic Shapes",
    },
};

{% endhighlight %}

![Symbol Custom ContextMenu](Stencil_images/SymbolsContextMenuItems.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/StencilContextMenu)

## Context menu for SymbolGroup in Stencil

You can use the [Menu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolGroupViewModel_Menu) property in the [SymbolGroupViewModel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroupViewModel.html#Syncfusion_UI_Xaml_Diagram_Stencil_SymbolGroupViewModel_Symbols) class to specify menu for each [SymbolGroup](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.SymbolGroup.html) or use the [SymbolGroupMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Diagram.Stencil.Stencil.html#Syncfusion_UI_Xaml_Diagram_Stencil_Stencil_SymbolGroupMenu) property in the `Stencil` for use the same menu for all `SymbolGroups`.

{% highlight xaml %}

<syncfusion:Stencil x:Name="stencil11"  Grid.Column="0" Grid.Row="1"  ExpandMode="ZeroOrMore" BorderBrush="#dfdfdf" BorderThickness="1">
    <syncfusion:Stencil.SymbolGroups>
        <syncfusion:SymbolGroups>
            <syncfusion:SymbolGroupViewModel Name="Basic Shapes" CategorySource="{StaticResource BasicShapes}">
                <syncfusion:SymbolGroupViewModel.Menu>
                    <syncfusion:DiagramMenu>
                        <syncfusion:DiagramMenu.MenuItems>
                            <local:DiagramMenuItems>
                                <syncfusion:DiagramMenuItem Content="Delete" Icon="pack://application:,,,/Images/Delete.png"/>
                            </local:DiagramMenuItems>
                        </syncfusion:DiagramMenu.MenuItems>
                    </syncfusion:DiagramMenu>
                </syncfusion:SymbolGroupViewModel.Menu>
            </syncfusion:SymbolGroupViewModel>
            <syncfusion:SymbolGroupViewModel Name="Flow Shapes" CategorySource="{StaticResource FlowShapes}"/>
            <syncfusion:SymbolGroupViewModel Name="Arrow Shapes" CategorySource="{StaticResource ArrowShapes}"/>
            <syncfusion:SymbolGroupViewModel Name="DataFlow Shapes" CategorySource="{StaticResource DataFlowShapes}"/>
        </syncfusion:SymbolGroups>
    </syncfusion:Stencil.SymbolGroups>
    <syncfusion:Stencil.SymbolGroupMenu>
        <syncfusion:DiagramMenu>
            <syncfusion:DiagramMenu.MenuItems>
                <local:DiagramMenuItems>
                    <syncfusion:DiagramMenuItem Content="Move Up" Icon="pack://application:,,,/Images/Arrow Up -03.png"  ></syncfusion:DiagramMenuItem>
                    <syncfusion:DiagramMenuItem Content="Move Down" Icon="pack://application:,,,/Images/Road-Backward.png"  ></syncfusion:DiagramMenuItem>
                </local:DiagramMenuItems>
            </syncfusion:DiagramMenu.MenuItems>
        </syncfusion:DiagramMenu>
    </syncfusion:Stencil.SymbolGroupMenu>
</syncfusion:Stencil>    

{% endhighlight %}

![SymbolGroupMenu and Menu](Stencil_images/MenuandSymbolGroupMenu.gif)

[View Sample in GitHub](https://github.com/SyncfusionExamples/WPF-Diagram-Examples/tree/master/Samples/Stencil/SymbolGroupViewModel/SymbolGroupsWithContextMenu)