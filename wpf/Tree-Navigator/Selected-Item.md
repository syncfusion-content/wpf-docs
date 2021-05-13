---
layout: post
title: Selected Item in WPF Tree Navigator control | Syncfusion
description: Learn here all about Selected Item support in Syncfusion WPF Tree Navigator (SfTreeNavigator) control and more.
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Selected Item in WPF Tree Navigator (SfTreeNavigator)

The SelectedItem property of SfTreeNavigator can be used to get or set the SelectedItem in SfTreeNavigator.

Please find the code example for the same from below:

{% tabs %}

{% highlight XAML %}

<Grid>
<!--Binding the selecteditem for TreeNavigator-->
<navigation:SfTreeNavigator Header="MailBox" x:Name="TreeNavigator" Width="500" Height="300" SelectedItem="{Binding SelectedItem, Mode=TwoWay}">
<navigation:SfTreeNavigatorItem Header="Mail"/>
<navigation:SfTreeNavigatorItem Header="Favorite Folders"/>
<navigation:SfTreeNavigatorItem  Header="Contacts">
<navigation:SfTreeNavigatorItem  Header="Task"/>
</navigation:SfTreeNavigatorItem>
<navigation:SfTreeNavigatorItem  Header="Notes"/>
</navigation:SfTreeNavigator>
</Grid>

{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : ChromelessWindow
{
    public MainWindow()
    {
        InitializeComponent();
        this.DataContext = new ViewModel();
//Set the selecteditem
        (this.DataContext as ViewModel).SelectedItem = TreeNavigator.Items[1];
    }
}
//Initiate the viewmodel class
    public class ViewModel
    {
        private object selecteditem;
        public object SelectedItem
        {
// Get the selecteditem
            get 
            { 
                return selecteditem;
            }
            set
            {
//Set the selecteditem
                selecteditem = value;
            }
        }
    }
}

{% endhighlight %}

{% highlight VB %}

'Initiate the viewmodel class
Partial Public Class MainWindow
Inherits ChromelessWindow
Public Sub New()
InitializeComponent()
Me.DataContext = New ViewModel()
(TryCast(Me.DataContext, ViewModel)).SelectedItem = TreeNavigator.Items(1)
End Sub
Public Class ViewModel
Private selecteditem As Object

'Get the selecteditem
Public Property SelectedItem As Object
Get
Return SelectedItem
End Get

'Set the selecteditem
Set(ByVal value As Object)
selecteditem = value
End Set
End Property
End Class

{% endhighlight %}

{% endtabs %}

![Selected_img2](Populating-Items_images/Selected_img2.png)

Fig i: Shows the Item has been selected in SfTreeNavigator
