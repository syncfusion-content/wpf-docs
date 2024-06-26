---
layout: post
title: MVVM in WPF Button control | Syncfusion
description: Learn here all about MVVM support in Syncfusion WPF Button (ButtonAdv) control, its elements and more details.
platform: wpf
control: ButtonAdv
documentation: ug
---

# MVVM in WPF Button (ButtonAdv)

The command and command parameter properties allow to execute any action on clicking the button control.

* **Command** - The [Command](https://learn.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.command?view=netframework-4.8) property accept all commands derived from interface [ICommand](https://learn.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8). 
* **CommandParameter** - The [CommandParameter](https://learn.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.commandparameter?view=netframework-4.8) property allows the user to provide additional data required in the command handler in-order to perform any operation. 

{% tabs %}
{% highlight xaml %}

<Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Buttonadv_Mvvm"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="Buttonadv_Mvvm.MainWindow"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
        <Window.DataContext>
            <local:ButtonViewModel/>
        </Window.DataContext>
    <Grid VerticalAlignment="Center">
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="200"/>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <CheckBox IsChecked="{Binding CanPerformAction}" Grid.Column="0" Content="Can perform action in button"/>
            
        <syncfusion:ButtonAdv SizeMode="Large" LargeIcon="image\userlarge.png" Label="Log in"  
                            Command="{Binding ClickCommand}" 
                            Grid.Column="1"
                            CommandParameter="Action completed" 
                            Height="68"  Width="78"/>
    </Grid>
</Window>
    

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

public class ButtonViewModel : NotificationObject
{
    private bool _canperformaction = true;
        

    public ButtonViewModel()
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
        MessageBox.Show(parameter.ToString());
    } 
}
   
{% endhighlight %}
{% endtabs %}

N> View [sample](https://github.com/SyncfusionExamples/wpf-button-examples/blob/master/Samples/MVVM) in GitHub. This sample showcases how to bind commands to the `ButtonAdv` control.
