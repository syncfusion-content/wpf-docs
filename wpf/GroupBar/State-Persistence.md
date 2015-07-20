---
layout: post
title: State-Persistence
description: state persistence
platform: wpf
control: GroupBar
documentation: ug
---

# State Persistence

The bar state can be persisted in the GroupBar control using the bar state methods available. You can set three different state persistence in the GroupBar. The three state persistence are as follows.

* Save State – Saves the state persisted for the current GroupBar location. This can be done using the SaveBarState method.
* Load State – Loads the state that is persisted. This can be done using the LoadBarState method.
* Reset State – Resets the state that is persisted. This can be done using the ResetBarState method.

You can set the state persistence using the following code.



[C#]



// Save State

myGroupBar.SaveBarState();



// Load State

myGroupBar.LoadBarState();

resgisterEvents(myGroupBar);



// Reset State

myGroupBar.ResetBarState();

resgisterEvents(myGroupBar);



The ResetBarState method is used to register the events. The following code illustrates this.



[C#]



public void registerEvents(Syncfusion.Windows.Tools.Controls.GroupBar groupBar)

{

if (groupBar != null)

{

    foreach (GroupBarItem tab in groupBar.Items)

    {

        SubscribeToTabEvents(tab);

        if (tab.Content is GroupView)

        {

            GroupView view = tab.Content as GroupView;

            if (view != null)

            {

                foreach (GroupViewItem item in view.Items)

                {

                    SubscribeToItemEvents(item);

                }

            }

        }

    }

}

}



You can also save the state persisted on loading the GroupBar. By using the SaveOriginalState property, you can enable the saving the state on loading. This dependency property sets the value indicating whether to save the state persisted on loading the GroupBar. 

Use the below code snippet to set this property.



<table>
<tr>
<td>
[XAML]&lt;!-- Adding GroupBar --&gt;&lt;syncfusion:GroupBar Height="200" Width="230" SaveOriginalState="True" Name="groupBar"&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem" Header="GroupBarItem" IsSelected="True"&gt;    &lt;!-- Adding content for GroupBar item using panel --&gt;    &lt;StackPanel Orientation="Vertical"&gt;      &lt;TextBlock Text="GroupBar Orientation" Margin="4,4,2,2"/&gt;      <RadioButton IsChecked="True" Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton Margin="4,2,2,2">Vertical</RadioButton>      &lt;TextBlock Text="GroupView Orientation" Margin="4,4,2,2"/&gt;      <RadioButton Margin="4,2,2,2">Horizontal</RadioButton>      <RadioButton IsChecked="True" Margin="4,2,2,2">Vertical</RadioButton>    &lt;/StackPanel&gt;  &lt;/syncfusion:GroupBarItem&gt;  &lt;!-- Adding GroupBarItem --&gt;  &lt;syncfusion:GroupBarItem Name="groupBarItem1" HeaderImageSource="Label.gif" Header="General"&gt;    &lt;!-- Adding content for GroupBar item using GroupView --&gt;    &lt;syncfusion:GroupView Name="groupView" IsListViewMode="True"&gt;      &lt;syncfusion:GroupViewItem Text="List View"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ContextMenu"/&gt;      &lt;syncfusion:GroupViewItem Text="Show ToolTip"/&gt;    &lt;/syncfusion:GroupView&gt;  &lt;/syncfusion:GroupBarItem&gt;&lt;/syncfusion:GroupBar&gt;</td></tr>
<tr>
<td>
[C#]//Enable the save state propertygroupBar.SaveOriginalState = true;  </td></tr>
</table>


