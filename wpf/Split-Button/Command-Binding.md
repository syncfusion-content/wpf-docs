---
layout: post
title: Command Binding in WPF Split Button control | Syncfusion
description: Learn about Command Binding support in Syncfusion Essential Studio WPF Split Button control, its elements and more.
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Command Binding in WPF Split Button

The command and command parameter properties allow to execute any action on clicking either the button or the dropdown menu items.

* **Command** - The [Command](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.command?view=netframework-4.8) property accept all commands derived from interface [ICommand](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8). 
* **CommandParameter** - The [CommandParameter](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.commandparameter?view=netframework-4.8) property allows the user to provide additional data required in the command handler in-order to perform any operation. 

{% tabs %}
{% highlight xaml %}

<Window x:Class="Split_Button_Command_Binding.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Button_Sample"
        xmlns:Syncfusion="http://schemas.microsoft.com/netfx/2009/xaml/presentation"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        Title="MainWindow" Height="450" Width="800">
    <Window.DataContext>
        <local:SplitViewModel/>
    </Window.DataContext>
    <Grid VerticalAlignment="Center" HorizontalAlignment="Left">
        <Grid.RowDefinitions>
            <RowDefinition Height="30"/>
            <RowDefinition Height="30"/>
            <RowDefinition Height="*"/>
        </Grid.RowDefinitions>
        <CheckBox IsChecked="{Binding CanPerformAction}" Grid.Row="0" Content="Can perform action in split button"/>
        <CheckBox IsChecked="{Binding CanPerformActionItem}" Grid.Row="1" Content="Can perform action in drop down items"/>
        <syncfusion:SplitButtonAdv Label="Country" SizeMode="Large" LargeIcon="Images\flaglarge.png" Command="{Binding ClickCommand}" CommandParameter="Action completed" Grid.Row="2" Height="72" Width="122">
            <syncfusion:DropDownMenuGroup>
                <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="India" Command="{Binding DropDownCommand}" CommandParameter="India">
                    <syncfusion:DropDownMenuItem.Icon>
                        <Image Source="Images/india.png"/>
                    </syncfusion:DropDownMenuItem.Icon>
                </syncfusion:DropDownMenuItem>
                <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="France" Command="{Binding DropDownCommand}" CommandParameter="France" >
                    <syncfusion:DropDownMenuItem.Icon>
                        <Image Source="Images/france.png"/>
                    </syncfusion:DropDownMenuItem.Icon>
                </syncfusion:DropDownMenuItem>
                <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="Germany" Command="{Binding DropDownCommand}" CommandParameter="Germany" >
                    <syncfusion:DropDownMenuItem.Icon>
                        <Image Source="Images/germany.png"/>
                    </syncfusion:DropDownMenuItem.Icon>
                </syncfusion:DropDownMenuItem>
                <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="Canada" Command="{Binding DropDownCommand}" CommandParameter="Canada" >
                    <syncfusion:DropDownMenuItem.Icon>
                        <Image Source="Images/Canada.png"/>
                    </syncfusion:DropDownMenuItem.Icon>
                </syncfusion:DropDownMenuItem>
                <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="China" Command="{Binding DropDownCommand}" CommandParameter="China" >
                    <syncfusion:DropDownMenuItem.Icon>
                        <Image Source="Images/china.png"/>
                    </syncfusion:DropDownMenuItem.Icon>
                </syncfusion:DropDownMenuItem>
            </syncfusion:DropDownMenuGroup >
        </syncfusion:SplitButtonAdv>
    </Grid>
</window>

{% endhighlight %}
{% highlight c# %}

public class DelegateCommand<T> : ICommand
{
    private Predicate<T> _canExecute;
    private Action<T> _method;
    bool _canExecuteCache = true;

    /// <summary>
    /// Initializes a new instance of the <see cref="DelegateCommand"/> class.
    /// </summary>
    /// <param name="method">The method.</param>
    public DelegateCommand(Action<T> method)
        : this(method, null)
    {
    }

    /// <summary>
    /// Initializes a new instance of the <see cref="DelegateCommand"/> class.
    /// </summary>
    /// <param name="method">The method.</param>
    /// <param name="canExecute">The can execute.</param>
    public DelegateCommand(Action<T> method, Predicate<T> canExecute)
    {
        _method = method;
        _canExecute = canExecute;
    }

    /// <summary>
    /// Defines the method that determines whether the command can execute in its current state.
    /// </summary>
    /// <param name="parameter">Data used by the command.  If the command does not require data to be passed, this object can be set to null.</param>
    /// <returns>
    /// true if this command can be executed; otherwise, false.
    /// </returns>
    public bool CanExecute(object parameter)
    {
        if (_canExecute != null)
        {
            bool tempCanExecute = _canExecute((T)parameter);

            if (_canExecuteCache != tempCanExecute)
            {
                _canExecuteCache = tempCanExecute;
                this.RaiseCanExecuteChanged();
            }
        }

        return _canExecuteCache;
    }

    /// <summary>
    /// Raises CanExecuteChanged event to notify changes in command status.
    /// </summary>
    public void RaiseCanExecuteChanged()
    {
        if (CanExecuteChanged != null)
        {
            CanExecuteChanged(this, new EventArgs());
        }
    }

    /// <summary>
    /// Defines the method to be called when the command is invoked.
    /// </summary>
    /// <param name="parameter">Data used by the command.  If the command does not require data to be passed, this object can be set to null.</param>
    public void Execute(object parameter)
    {
        if (_method != null)
            _method.Invoke((T)parameter);
    }

    #region ICommand Members

    /// <summary>
    /// 
    /// </summary>
    public event EventHandler CanExecuteChanged;

    #endregion
}

class DropDownViewModel: NotificationObject
{
    private bool _canperformaction = true;

    public DropDownViewModel()
    {
        ClickCommand = new DelegateCommand<object>(ClickAction, CanPerformClickAction);
    }
    public bool CanPerformAction
    {
        get
        {
            return _canperformaction;
        }
        set
        {
            _canperformaction = value;
            this.ClickCommand.RaiseCanExecuteChanged();
            this.RaisePropertyChanged("CanPerformAction");
        }
    }

    private bool CanPerformClickAction(object parameter)
    {
        return CanPerformAction;
    }

    public DelegateCommand<object> ClickCommand { get; set; }

    private void ClickAction(object parameter)
    {
        MessageBox.Show(parameter.ToString() + " dropdown menu item has been clicked");
    }
}

{% endhighlight %}
{% endtabs %}

N> View [sample](https://github.com/SyncfusionExamples/wpf-split-button-examples/blob/master/Samples/Command-Binding) in GitHub. This sample showcases how to provide command binding for `SplitButtonAdv` control.
