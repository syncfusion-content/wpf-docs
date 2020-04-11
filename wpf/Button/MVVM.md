---
layout: post
title: Command Binding | ButtonAdv | WPF | Syncfusion
description: This section explores how to provide command binding for button control to perform any action while pressing the Button.
platform: WPF
control: ButtonAdv
documentation: ug
---

# MVVM in WPF Button (ButtonAdv)

The command and command parameter properties allow to execute any action on clicking the button control.

## Command

The [Command](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommandsource.command?view=netframework-4.8) property accept all commands derived from interface [ICommand](https://docs.microsoft.com/en-us/dotnet/api/system.windows.input.icommand?view=netframework-4.8).

The Command can be binded as follows:

{% tabs %}
{% highlight xaml %}

    <syncfusion:ButtonAdv SizeMode="Large" LargeIcon="Employee-WF.png" Command="{Binding Button_Command}"/>

{% endhighlight %}
{% highlight c# %}


    public class Button_Command : ICommand
    {        
        Action<Object> execute;

        Func<object, bool> canexecute;

        public Button_Command(Action<Object> execute,Func<object, bool> canexecute)
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

    public class ViewModel
    {   
        public ViewModel()
        {
            Button = new Button_Command(Execute, CanExecute);
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

    <Label x:Name="Mylabel" Content="Hello"/>
    <syncfusion:ButtonAdv SizeMode="Large" LargeIcon="Employee-WF.png" Command="{Binding Button_Command}" CommandParameter="{Binding Path=Label, ElementName=Mylabel}"/>

{% endhighlight %}
{% highlight c# %}

    public  class ViewModel
    {
        public ViewModel()
        {
            Button = new Button_Command(Execute, CanExecute);
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