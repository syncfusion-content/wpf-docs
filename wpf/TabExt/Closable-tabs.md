---
layout: post
title: Behavior of TabItemExt's CloseButton in Syncfusion TabControlExt
description: Explains about the behavior of TabItem's CloseButton in TabControlExt of WPF
platform: wpf
control: TabControlExt
documentation: ug
---

# Closable TabItem

## Visibility of close button in TabItem and TabPanel

The display mode of the Close button is specified by using the CloseButtonType property. This dependency property sets the display mode for the Close button.

The following Close button modes are supported by the TabControlExt.

* Common–close button is displayed commonly for all tab items in the TabControlExt control
* Individual–close button is displayed individually for each tab item in the TabControlExt control
* Both–close button is displayed commonly for all tab items and also individually for each tab item in TabControlExt control
* Hide–close button is hidden in the TabControlExt control
* IndividualOnMouseOver – close button is displayed when the mouse hovers over the tab item in the TabControlExt control



The following code snippet illustrates how to set the "Both" Close button mode in the TabControlExt control.

{% tabs %}

{% highlight xaml %}

<!-- Adding TabcontrolExt with CloseButtonType is Both -->

<syncfusion:TabControlExt Margin="20" Name="tabControlExt" CloseButtonType="Both">

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt1" Header="TabItemExt1"/>

    <!-- Adding TabItemExt -->

    <syncfusion:TabItemExt Name="tabItemExt2" Header="TabItemExt2"/>

</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

// Creating instance of the TabControlExt control

TabControlExt tabControlExt = new TabControlExt();

//Creating the instance of StackPanel

StackPanel stackPanel = new StackPanel();

//Creating instance of the TabItemExt 

TabItemExt tabItemExt1 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt1.Header = "TabItemExt1";

//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt1);

//Creating instance of the TabItemExt2 

TabItemExt tabItemExt2 = new TabItemExt();

// Setting header of the TabItemExt

tabItemExt2.Header = "TabItemExt2";

//Adding TabItemExt to TabControlExt

tabControlExt.Items.Add(tabItemExt2);           

//Setting CloseButtonType property as Both

tabControlExt.CloseButtonType = CloseButtonType.Both;

//Adding control to the StackPanel

stackPanel.Children.Add(tabControlExt); 

{% endhighlight %}


{% endtabs %}


![Display close button in both TabItem and TabPanel](Closable-tabs-images/Closable-tabs-images3.jpeg)


## Show/Hide the close button for speicfic TabItem

The visibility of the TabItem's CloseButton is handled using the [CloseButtonState](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~CloseButtonState.html) property. The [CloseButtonState](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~CloseButtonState.html) is effective only when the `CloseButtonType` property of TabControlExt is set to one among individual, extended, or both.

<table>
<tr>
<td>
<b> CloseButtonState </b> <br/><br/></td><td>
<b> Description </b> <br/><br/></td></tr>
<tr>
<td>
Visible<br/><br/></td><td>
The close button of TabItemExt is visible<br/><br/></td></tr>
<tr>
<td>
Collapsed<br/><br/></td><td>
The close button of TabItemExt is collapsed<br/><br/></td></tr>
<tr>
<td>
Hidden<br/><br/></td><td>
The close button of TabItemExt is hidden<br/><br/></td></tr>
</table>

{% tabs %}
{% highlight XAML %}
<syncfusion:TabControlExt x:Name="Tab" CloseButtonType="Individual"
                                      >
                <syncfusion:TabItemExt Header="Beijing" CloseButtonState="Visible" />
            
            <syncfusion:TabItemExt Header="Madagascar" CloseButtonState="Collapsed"/>
            
            <syncfusion:TabItemExt Header="New York" CloseButtonState="Hidden"/>
            <syncfusion:TabItemExt Header="London"/>
            </syncfusion:TabControlExt>
{% endhighlight %}
{% endtabs %}

![Items of TabControl is rendered with different values of CloseButtonState](Closable-tabs-images/Closable-tabs-images2.png)


N> "Beijing" TabItem has CloseButtonState as visible, "Madagascar" TabItem has CloseButtonState as Collapsed, and "New York" TabItem has CloseButtonState as Hidden.


## Restrict TabItem closing through closing event

The closure of TabItem can now be restricted by setting e.Cancel to true in OnCloseButtonClick delegate. “e” represents the event argument CloseTabEventArgs for OnCloseButtonClick event. The default value of e.Cancel is false.

The following code illustrates the same.

{% tabs %}

{% highlight xaml %}

  <syncfusion:TabControlExt OnCloseButtonClick="TabControlExt_OnCloseButtonClick">

            <syncfusion:TabItemExt Header="Tab1"/>
            
            <syncfusion:TabItemExt Header="Tab2"/>
            
            <syncfusion:TabItemExt Header="Tab3"/>
            
</syncfusion:TabControlExt>

{% endhighlight %}

{% highlight c# %}

 private void TabControlExt_OnCloseButtonClick(object sender, CloseTabEventArgs e)
 
 {

            if (e.TargetTabItem.Header.ToString() == "Tab1")
                e.Cancel = true;
 }

{% endhighlight %}

{% endtabs %}

## Restrict closing of TabItem using the CanClose property

Users can restrict the closing functionality of TabItem using the [CanClose](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~CanClose.html) property of TabItemExt. When the [CanClose](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.TabItemExt~CanClose.html) property is set to false, the corresponding TabItem will be non-closable. The default value of this property is true. 

The following code sample illustrates restricting the closing functionality of TabItem.

{% tabs %}
{% highlight XAML %}
<syncfusion:TabControlExt x:Name="Tab" CloseButtonType="Individual"
                                      >
                <syncfusion:TabItemExt Header="Beijing" CanClose="false"/>
            
            <syncfusion:TabItemExt Header="Madagascar"/>
            
            <syncfusion:TabItemExt Header="New York"/>
            <syncfusion:TabItemExt Header="London"/>
            </syncfusion:TabControlExt>
{% endhighlight %}
{% endtabs %}

![Beijing tabitem is non-closable](Closable-tabs-images/Closable-tabs-images1.png)

