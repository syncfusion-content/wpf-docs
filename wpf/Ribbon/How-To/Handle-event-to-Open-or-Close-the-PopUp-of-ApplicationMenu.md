---
 layout: post
title: Handle PopUp opening and Closing event in ApplicationMenu| Ribbon | Wpf | Syncfusion
description: handle event to detect the opening and closing of applicationmenu
platform: wpf
control: Ribbon
documentation: ug
---

# Handle Pop-Up Opening and Closing Event in ApplicationMenu

To perform the action based on opening and closing of the ApplicationMenu, make use of `IsPopupOpenChanged` event.

{% tabs %}

{% highlight XAML %}

<syncfusion:ApplicationMenu Name="_applicationMenu" Width="38" Height="38"  ApplicationButtonImage="Resources/App.ico" IsPopupOpenChanged="_applicationMenu_IsPopupOpenChanged">

{% endhighlight %}

{% highlight c# %}

private void _applicationMenu_IsPopupOpenChanged(DependencyObject d, DependencyPropertyChangedEventArgs e)
{
    if((d as ApplicationMenu).IsPopupOpen)
    {
        newMenuButton.IsEnabled = false;
    }
    else
    {
        newMenuButton.IsEnabled = true;
    }
}

{% endhighlight %}

{% highlight vb %}

Private Sub _applicationMenu_IsPopupOpenChanged(ByVal d As DependencyObject, ByVal e As DependencyPropertyChangedEventArgs)
If(TryCast(d, ApplicationMenu)).IsPopupOpen Then
newMenuButton.IsEnabled = False
Else
newMenuButton.IsEnabled = True
End If
End Sub

{% endhighlight %}
{% endtabs %}