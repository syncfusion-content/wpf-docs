---
layout: post
title: ContextMenu with WPF TreeView control | Syncfusion
description: Learn about context menu support and its customization with Syncfusion WPF TreeView (SfTreeView) control and more details.
platform: wpf
control: SfTreeView
documentation: ug
---

# ContextMenu in WPF TreeView (SfTreeView)

This section explains how to show ContextMenu and using built-in commands in the TreeView.

## ContextMenu for Nodes

TreeView provides an entirely customizable context menu to expose the functionality on user interface. You can create context menu for nodes in an efficient manner.

## Built-in Commands

SfTreeView provides support for the following built-in commands

* [Edit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewCommands.html#Syncfusion_UI_Xaml_TreeView_TreeViewCommands_Edit) - Command to start the editing of the node.
* [DeleteNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewCommands.html#Syncfusion_UI_Xaml_TreeView_TreeViewCommands_DeleteNode) - Command to delete the node.
* [DeleteSelectedNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewCommands.html#Syncfusion_UI_Xaml_TreeView_TreeViewCommands_DeleteSelectedNodes) - Command to delete all the selected nodes.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView"
				ItemsSource="{Binding Folders}"
				ChildPropertyName="SubFiles"
                AllowEditing="True"
                SelectionMode="Multiple">
    <syncfusion:SfTreeView.ItemContextMenu>
        <ContextMenu>
            <MenuItem Command="{x:Static syncfusion:TreeViewCommands.Edit}" CommandParameter="{Binding }"></MenuItem>
            <MenuItem Command="{x:Static syncfusion:TreeViewCommands.DeleteNode}" CommandParameter="{Binding }" ></MenuItem>
            <MenuItem Command="{x:Static syncfusion:TreeViewCommands.DeleteSelectedNodes}" CommandParameter="{Binding }" ></MenuItem>
        </ContextMenu>
    </syncfusion:SfTreeView.ItemContextMenu>
</syncfusion:SfTreeView>
{% endhighlight %}
{% endtabs %}

[WPF TreeView with ContextMenu using built-in commands](ContextMenu_images/ContextMenu_image1.png)

## Custom Commands

SfTreeView provides support to show ContextMenu using custom commands when built-in commands does not meet your requirement.

For an example, custom command is used to expand the nodes using context menu in the following example

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView"
				ItemsSource="{Binding Folders}"
				ChildPropertyName="SubFiles"
                AllowEditing="True"
                SelectionMode="Multiple">
    <syncfusion:SfTreeView.ItemContextMenu>
        <ContextMenu>
            <MenuItem Command="{Binding Path=TreeView.DataContext.ExpandCommand}" CommandParameter="{Binding }"  Header="Expand"/>
        </ContextMenu>
    </syncfusion:SfTreeView.ItemContextMenu>
</syncfusion:SfTreeView>
{% endhighlight %}
{% highlight c# %}
public class BaseCommand : ICommand
{

    #region Fields
    readonly Action<object> _execute;
    readonly Predicate<object> _canExecute;
    #endregion

    #region Constructors
    /// <summary>
    /// Creates a new command that can always execute.
    /// </summary>
    /// <param name="execute">The execution logic.</param>

    public BaseCommand(Action<object> execute)
        : this(execute, null)
    {
    }

    /// <summary>
    /// Creates a new command.
    /// </summary>
    /// <param name="execute">The execution logic.</param>
    /// <param name="canExecute">The execution status logic.</param>

    public BaseCommand(Action<object> execute, Predicate<object> canExecute)
    {

        if (execute == null)
        throw new ArgumentNullException("execute");
        _execute = execute;
        _canExecute = canExecute;
    }
    #endregion
    
    #region ICommand Members

    public bool CanExecute(object parameter)
    {
        return _canExecute == null ? true : _canExecute(parameter);
    }
    
    public event EventHandler CanExecuteChanged
    {
        add { CommandManager.RequerySuggested += value; }
        remove { CommandManager.RequerySuggested -= value; }
    }

    public void Execute(object parameter)
    {
        _execute(parameter);
    }
    
    #endregion
}

public class FileManagerViewModel
{
    public FileManagerViewModel()
    {
        ExpandCommand = new BaseCommand(ExecuteExpandCommand, CanExecuteExpandCommand);
    }
    
    public BaseCommand ExpandCommand { get; set; }
    
    private bool CanExecuteExpandCommand(object obj)
    {
            if (obj == null)
                return false;
            var treeViewContextMenuInfo = obj as TreeViewItemContextMenuInfo;
            if(treeViewContextMenuInfo.Node.HasChildNodes)
                return true;
            return false;
        }

    private static void ExecuteExpandCommand(object obj)
    {
            if (obj == null)
                return;
            var treeViewContextMenuInfo = obj as TreeViewItemContextMenuInfo;
            treeViewContextMenuInfo.TreeView.ExpandNode(treeViewContextMenuInfo.Node);
    }
}
{% endhighlight %}
{% endtabs %}

[WPF TreeView with ContextMenu using custom commands](ContextMenu_images/ContextMenu_image2.png)

## Events

### ItemContextMenuOpening Event

[ItemContextMenuOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemContextMenuOpening) event occurs while opening the context menu in SfTreeView.

[ItemContextMenuOpeningEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemContextMenuOpeningEventArgs.html) has the following members which provides the information about `ItemContextMenuOpening` event

* [MenuInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemContextMenuOpeningEventArgs.html#Syncfusion_UI_Xaml_TreeView_ItemContextMenuOpeningEventArgs_MenuInfo) - Gets an instance of [TreeViewContextMenuInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemContextMenuInfo.html) that contains information about treeview and treeview node.
* [ContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemContextMenuOpeningEventArgs.html#Syncfusion_UI_Xaml_TreeView_ItemContextMenuOpeningEventArgs_ContextMenu) - Gets or sets the context menu getting opened. 

You can cancel showing [ItemContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemContextMenuOpening) for certain nodes using custom logic within this event by setting `ItemContextMenuOpeningEventArgs.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemContextMenuOpening += TreeView_ItemContextMenuOpening;

private void TreeView_ItemContextMenuOpening(object sender, Syncfusion.UI.Xaml.TreeView.ItemContextMenuOpeningEventArgs e)
{
    if (e.MenuInfo.Node.Level == 2)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}




