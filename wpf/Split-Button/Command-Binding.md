---
layout: post
title: Command Binding | Split Button Control | WPF | Syncfusion
description: This section explores how to provide command binding for both split button and dropdown menu items to perform any action while clicking the same.
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Command binding in WPF Split Button (SplitButtonAdv)

The command and command parameter properties allow to execute any action on clicking either button or dropdown menu items.

## Command

The [Command](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.SplitButtonAdv~Command.html) property accept all commands derived from interface [ICommand](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8).

{% tabs %}
{% highlight xaml %}
    
    <Window x:Class="SplitButton_Sample.MainWindow"
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
            <local:SplitViewModel x:Key="SplitViewModel"/>
        </Window.Resources>
        <Grid>
            <syncfusion:SplitButtonAdv SizeMode="Large" Command="{Binding SplitCommand, Source={StaticResource SplitViewModel}}" LargeIcon="Employee-WF.png">
                <syncfusion:DropDownMenuGroup >
                    <syncfusion:DropDownMenuItem Header="India" Command="{Binding MenuItemCommand, Source={StaticResource SplitViewModel}}"/>
                </syncfusion:DropDownMenuGroup >
            <syncfusion:SplitButtonAdv/>
        </Grid>
    </window>
{% endhighlight %}
{% highlight c# %}

    public  class SplitButton_Command : ICommand
    {     
        Action<Object> execute;

        Func<object, bool> canexecute;

        public SplitButton_Command(Action<Object> execute,Func<object, bool> canexecute)
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

    public  class SplitViewModel
    {
        public SplitButton_Command SplitCommand { get; set; }
        public SplitButton_Command MenuItemCommand { get; set; }

        public SplitViewModel()
        {
            SplitCommand = new SplitButton_Command(Execute, CanExecute);
            MenuItemCommand= new SplitButton_Command(ExecuteMenuItem, CanExecuteMenuItem);
        }
        public bool CanExecute(object parameter)
        {
            return true;
        }

        public void Execute(object parameter)
        {
            MessageBox.Show("Split Button Clicked");
        }

        public bool CanExecuteMenuItem(object parameter)
        {
            return true;
        }

        public void ExecuteMenuItem(object parameter)
        {
            MessageBox.Show("Drop down menu item Clicked");
        }
    }

{% endhighlight %}
{% endtabs %}

## Command Parameter

The [CommandParameter](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.SplitButtonAdv~CommandParameter.html) property allows the user to provide additional data required in the command handler in-order to perform any operation.

{% tabs %}
{% highlight xaml %}

    <Window x:Class="SplitButton_Sample.MainWindow"
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
                <local:SplitViewModel x:Key="SplitViewModel"/>
            </Window.Resources>
        <Grid>
            <Syncfusion:Label x:Name="Mylabel" Content="Hello"/>
            <Syncfusion:Label x:Name="Menuitem" Content="Menuitem Clicked"/>
            <syncfusion:SplitButtonAdv SizeMode="Large" Command="{Binding SplitCommand, Source={StaticResource SplitViewModel}}" CommandParameter="{Binding Path=Label, ElementName=Mylabel}"/> LargeIcon="Employee-WF.png">
                <syncfusion:DropDownMenuGroup>
                    <syncfusion:DropDownMenuItem  HorizontalAlignment="Left" Header="India" Command="{Binding MenuItemCommand, Source={StaticResource SplitViewModel}}" CommandParameter="{Binding Path=Label, ElementName=Menuitem}"/>
                </syncfusion:DropDownMenuGroup >
            <syncfusion:SplitButtonAdv/>
        </Grid>
    </window>

{% endhighlight %}
{% highlight c# %}

    public  class SplitViewModel
    {
        public SplitButton_Command SplitCommand { get; set; }
        public SplitButton_Command MenuItemCommand { get; set; }

        public SplitViewModel()
        {
            SplitCommand = new SplitButton_Command(Execute, CanExecute);
            MenuItemCommand= new SplitButton_Command(ExecuteMenuItem, CanExecuteMenuItem);
        }

        public bool CanExecute(object parameter)
        {
            return true;
        }

        public void Execute(object parameter)
        {
            MessageBox.Show(parameter.ToString());
        } 

        public bool CanExecuteMenuItem(object parameter)
        {
            return true;
        }

        public void ExecuteMenuItem(object parameter)
        {
            MessageBox.Show(parameter.ToString());
        } 
    }
    

{% endhighlight %}
{% endtabs %}