---
layout: post
title: Command Binding in WPF Breadcrumb control | Syncfusion
description: Learn here all about Command Binding support in Syncfusion WPF Breadcrumb (HierarchyNavigator) control and more.
platform: wpf
control: Breadcrumb
documentation: ug
---

# Command Binding in WPF Breadcrumb (HierarchyNavigator)

The HierarchyNavigator control enables command binding when a selected item is changed. There are two properties that occur when this happens.

The steps to listen to the command binding are as follows:

1. Create a DelegateCommand class inherited from ICommand, which will be used in the ViewModel sample class.

{% tabs %}
{% highlight c# %}

public class DelegateCommand : ICommand
{
	private Predicate<object> _canExecute;
	private Action<object> _method;
	public event EventHandler CanExecuteChanged;
	public DelegateCommand(Action<object> method)
	: this(method, null)
	{
		_method = method;
	}
	public DelegateCommand(Action<object> method, Predicate<object> canExecute)
	{
		_method = method;
		_canExecute = canExecute;
	}
	public bool CanExecute(object parameter)
	{
		if (_canExecute == null)
		{
		return true;
		}
		return _canExecute(parameter);
	}
	public void Execute(object parameter)
	{
    	_method.Invoke(parameter);
	}
}

{% endhighlight %}
{% endtabs %}

2. Create the ViewModel sample class, to bind the command in the sample WPF application.

{% tabs %}
{% highlight c# %}

public class ViewModel : INotifyPropertyChanged
{
	public event PropertyChangedEventHandler PropertyChanged;
	private DelegateCommand _myCommand1;
	private string _lastCommand = "Syncfusion";
	public string LastCommand
	{
		get
		{
            return _lastCommand;
		}
		private set
		{
    		_lastCommand = value;
    		PropertyChanged(this, new PropertyChangedEventArgs("LastCommand"));
		}
	}
	public DelegateCommand SelectedItemCommand
	{
    	get
		{
    		if (_myCommand1 == null)
    		_myCommand1 = new DelegateCommand(MyCommand1Method);
    		return _myCommand1;
		}
	}
	private void MyCommand1Method(object parameter)
	{
		if(parameter as Syncfusion.Windows.Tools.Controls.HierarchyNavigatorItem != null)
		LastCommand = (parameter as Syncfusion.Windows.Tools.Controls.HierarchyNavigatorItem).Content.ToString();
	}
}

{% endhighlight %}
{% endtabs %}

1. Bind the command in the HierarchyNavigator control.
2. To do this, create a new instance of the ViewModel sample class and set DataContext for the parent StackPanel. This will reflect changes in the children. Whenever the selected item changes, the TextBox Text value will change.

{% tabs %}
{% highlight xaml %}

<StackPanel Name="CommandBindingStackPanel">
<StackPanel.DataContext>
<local:ViewModel />
</StackPanel.DataContext>
<syncfusion:HierarchyNavigator Name="hierarchyNavigator1" 
        VerticalAlignment="Center" 
		Command="{Binding SelectedItemCommand}"
		Items="{StaticResource NavigationSampleData}" />
<TextBlock Text="Selected Item" VerticalAlignment="Center" FontWeight="Bold" />
<TextBox Text="{Binding LastCommand}" Height="50" IsReadOnly="True" Margin="2" />
</StackPanel>

{% endhighlight %}
{% endtabs %}
