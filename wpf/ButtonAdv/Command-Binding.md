---
layout: post
title: Command Binding | ButtonAdv | wpf | Syncfusion
description: command binding
platform: wpf
control: ButtonAdv
documentation: ug
---

# Command Binding

The ButtonAdv control supports Commanding. The Command and Command Parameter properties, enables the user to execute any action on clicking the instance.

The Command can be binded as follows:

{% tabs %}
{% highlight xaml %}


<sync:ButtonAdv SizeMode="Large" LargeIcon="Employee-WF.png" Command="{Binding CustomCommand}" CommandParameter="{Binding Path=Label, ElementName=Custom}"/>

{% endhighlight %}
{% highlight c# %}

 CustomCommand = new DelegateCommand(Execute, CanExecute);

public ICommand CustomCommand { get; set; }

private bool CanExecute(object arg)

{
    
    return true;
}

private void Execute(object obj)
  
{
 
    MessageBox.Show(obj.ToString());
}

{% endhighlight %}
{% endtabs %}
