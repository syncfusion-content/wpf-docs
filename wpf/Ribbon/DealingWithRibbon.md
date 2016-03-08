---
layout: post
title: Dealing with Syncfusion Ribbon control
description: This topic deal with RibbonState and ContextTabGroup
platform: wpf
control: Ribbon
documentation: ug
---
# Dealing With Ribbon

Ribbon can be changed into three different states such as `Normal`, `Hide` and `Adorner`

## Three types of RibbonState


**Normal** – Ribbon control displays the RibbonTab content and the window content is arranged below the Ribbon. This is the default state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Normal" VerticalAlignment="Top" x:Name="_ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img1.jpeg)

**Hide** - RibbonTab content gets hidden in this state

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Hide" VerticalAlignment="Top" x:Name="_ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img2.jpeg)


**Adorner** – In this state, RibbonTab content adorned above the window content

{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  RibbonState="Adorner" VerticalAlignment="Top" x:Name="_ribbon" >

<syncfusion:RibbonTab  Caption="Folder" IsChecked="False" >

<syncfusion:RibbonBar  Header="Acions">

<syncfusion:RibbonButton SizeForm="Small"  Label="Copy Folder"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Move Folder"/>

<syncfusion:SplitButton  Label=" Split1 "   SizeForm="Large" >

<syncfusion:RibbonButton SizeForm="Small"  Label="Mark to Download"/>

<syncfusion:RibbonButton SizeForm="Small"  Label="UnMark to Download"/>

</syncfusion:SplitButton>

</syncfusion:RibbonBar>

<syncfusion:RibbonBar Header="Properties">

<syncfusion:RibbonButton SizeForm="Small" Label="Policy"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Properties"/>

<syncfusion:RibbonButton SizeForm="Small" Label="Folder Permissions"/>

</syncfusion:RibbonBar>

</syncfusion:RibbonTab>

</syncfusion:Ribbon>

{% endhighlight %}

{% endtabs %}

![C:/Users/SUGAPR~1/AppData/Local/Temp/SNAGHTML7d9bdf5.PNG](ThreetypesofRibbonState_images/ThreetypesofRibbonState_img3.jpeg)

## How to change the RibbonState in run time?

Ribbon State can also be changed at the Runtime.In the below code, Ribbon State has been changed dynamically in the button click event

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Normal

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Hide

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner;

{% endhighlight %}

{% highlight VB %}

_ribbon.RibbonState = Syncfusion.Windows.Tools.RibbonState.Adorner

{% endhighlight %}

{% endtabs %}

# Grouping RibbonTabs using ContextTabGroups

ContextualTabGroups are used to group the RibbonTabs for easy Navigation. This ContextTabGroups appear when a user enable their context. 

## Creating ContextTabGroup 


This ContextTabGroup can also be kept hidden and shown while required cases like in Word Document’s TABLETOOLS ContextTabGroups which gets displayed automatically, while selecting the table.  The following code snippet used to create a ContextTabGroup

{% tabs %}
 
{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table tools" IsGroupVisible="True" BackColor="Green">

<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img1.jpeg)


## Multiple ContextTabs

To differentiate one ContextTabGroup with one another, change its `BackColor` property of the ContextTabGroup , Since a ContextTabGroup Support to have multiple context Tab.
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table Tools" BackColor="Green" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

<syncfusion:ContextTabGroup Label="Table Grid" BackColor="Red" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="False" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}

{% endtabs %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img2.jpeg)


## ContextTabGroup Heading

The `Label` property of the ContextTabGroup is used to define the Heading for the ContextTabGroup. 
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup Label="Table tools" BackColor="Green" IsGroupVisible="True">

<syncfusion:RibbonTab Caption="Tables" IsChecked="True" />

<syncfusion:RibbonTab Caption="Design" IsChecked="False" />

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>

{% endhighlight %}
 
{% endtabs %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img3.jpeg)




## Changing the visibility at run time

ContextTabGroup visibility can also be changed at the runtime. To change the visibility, enable `IsGroupVisible` property of the ContextTabGroup
 
{% tabs %}

{% highlight XAML %}

<syncfusion:Ribbon  VerticalAlignment="Top" >

<syncfusion:Ribbon.ContextTabGroups>

<syncfusion:ContextTabGroup x:Name="_contextTabGroup" Label="Table tools" BackColor="Red"  >

<syncfusion:RibbonTab Caption="Tables" IsChecked="True" >

</syncfusion:RibbonTab>

<syncfusion:RibbonTab Caption="Design" IsChecked="False" >

</syncfusion:RibbonTab>

</syncfusion:ContextTabGroup>

</syncfusion:Ribbon.ContextTabGroups>

</syncfusion:Ribbon>

{% endhighlight %}
 
{% endtabs %}
 
{% tabs %}

{% highlight C# %}

private void Button_Click(object sender, RoutedEventArgs e)

{

_contextTabGroup.IsGroupVisible = true;

}

{% endhighlight %}

{% highlight VB %}
 
Private Sub Button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)


_contextTabGroup.IsGroupVisible = True

End Sub

{% endhighlight %}
 
{% endtabs %}

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img4.jpeg)


After the Button is clicked, the ContextTabGroup visibility changes as follows

![](GroupingRibbonTabsusingContextTabGroups_images/GroupingRibbonTabsusingContextTabGroups_img5.jpeg)


