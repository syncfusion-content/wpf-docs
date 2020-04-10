---
layout: post
title: Command Binding | Dropdown Button Control | WPF | Syncfusion
description: This section explores how to provide command binding support for dropdown menu items to perform any action while clicking the same.
platform: WPF
control: DropDownButtonAdv
documentation: ug
---

# Command binding for menu items in WPF Dropdown Button (DropDownButtonAdv)

The command and command parameter properties allow to execute any action on clicking the dropdown menu items.

## Command

The [Command](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.command?view=netframework-4.8) property accept all commands derived from interface [ICommand](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8).

{% tabs %}
{% highlight xaml %}

    <Window x:Class="DropDownButton_Sample.MainWindow"
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
        <Window.Resources>
            <local:DropDownViewModel x:Key="dropdownViewModel"/>
        </Window.Resources>
        <Grid>
            <syncfusion:DropDownButtonAdv SizeMode="Large" LargeIcon="Employee-WF.png" >
                <syncfusion:DropDownMenuGroup>
                    <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="India" Command="{Binding DropDownCommand, Source={StaticResource dropdownViewModel}}"/>
                </syncfusion:DropDownMenuGroup >
            <syncfusion:DropDownButtonAdv/>
        </Grid>
    </window>

{% endhighlight %}
{% highlight c# %}

    public class DropDownButton_Command : ICommand
    {     
        Action<Object> execute;

        Func<object, bool> canexecute;

        public DropDownButton_Command(Action<Object> execute,Func<object, bool> canexecute)
        {
            this.execute = execute;
            this.canexecute = canexecute;
        }

        public bool CanExecute(object parameter)
        {
            return true;
        }

        public void Execute(object parameter)
        {
            execute(parameter);
        }

        public event EventHandler CanExecuteChanged;
    }

    public class DropDownViewModel
    {
        public DropDownButton_Command DropDownCommand { get; set; }

        public ViewModel()
        {
            DropDownCommand = new DropDownButton_Command(Execute, CanExecute);
        }
        public bool CanExecute(object parameter)
        {
            return true;
        }

        public void Execute(object parameter)
        {
            MessageBox.Show("Button Clicked");
        }
    }

{% endhighlight %}
{% endtabs %}

## Command Parameter

The [CommandParameter](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.commandparameter?view=netframework-4.8) property allows the user to provide additional data required in the command handler in-order to perform any operation.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="DropDownButton_Sample.MainWindow"
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
        <Window.Resources>
            <local:DropDownViewModel x:Key="dropdownViewModel"/>
        </Window.Resources>
        <Grid>
            <Syncfusion:Label x:Name="Mylabel" Content="Hello"/>
            <syncfusion:DropDownButtonAdv SizeMode="Large" LargeIcon="Employee-WF.png" >
                <syncfusion:DropDownMenuGroup >
                    <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="India" Command="{Binding DropDownCommand, Source={StaticResource dropdownViewModel}}" CommandParameter="{Binding Path=Label, ElementName=Mylabel}"/>
                </syncfusion:DropDownMenuGroup >
            <syncfusion:DropDownButtonAdv/>
        </Grid>
    </window>

{% endhighlight %}
{% highlight c# %}

    public class DropDownViewModel
    {
        public DropDownButton_Command DropDownCommand { get; set; }
        public ViewModel()
        {
            DropDownCommand = new DropDownButton_Command(Execute, CanExecute);
        }

        public bool CanExecute(object parameter)
        {
            return true;
        }

        public void Execute(object parameter)
        {
            MessageBox.Show(parameter.ToString());
        }
    }

{% endhighlight %}
{% endtabs %}