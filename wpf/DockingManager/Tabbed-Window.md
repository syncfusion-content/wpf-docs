---
layout: post
title: Tabbed Window of Syncfusion DockingManager control for WPF
description: Learn how to change the tab alignments and closing behaviour of Tabbed Window
platform: wpf
control: DockingManager
documentation: ug
---
# Tabbed Window

Child window can be arranged as Tabbed windows by setting TargetName and side value as `Tabbed` using the property `SideInDockedMode`.

![](TabbedWindow_images/TabbedWindow_img1.jpeg)


##  Tab alignments

The tabs of the Docked window are placed at the bottom, by default. To place the tabs of the docked window at different sides set the property `DockTabAlignment` with desired values such as Top, Bottom, Left and Right. 

* DockTabAlignment as `Bottom`

![](TabbedWindow_images/TabbedWindow_img2.jpeg)


* Setting DockTabAlignment as `Left`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Left">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="Content1" />
	
<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/> 

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();
			
//Set the tabs of the docked window at different sides

dock.DockTabAlignment = Dock.Left;
						
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Name = "Content1";

content2.Name = "Content2";

//Set Header

DockingManager.SetHeader(content1, "Item1");

DockingManager.SetHeader(content2, "Item2");

//Tabbed Window

DockingManager.SetSideInDockedMode(content2, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content2, "Content1");

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}


![](TabbedWindow_images/TabbedWindow_img3.jpeg)


* Setting DockTabAlignment as `Right`

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Right">

<ContentControl syncfusion:DockingManager.Header="Item1"  x:Name="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>
				
</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();
			
//Set the tabs of the docked window at different sides

dock.DockTabAlignment = Dock.Right;
						
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Name = "Content1";

content2.Name = "Content2";

//Set Header

DockingManager.SetHeader(content1, "Item1");

DockingManager.SetHeader(content2, "Item2");

//Tabbed Window

DockingManager.SetSideInDockedMode(content2, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content2, "Content1");

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}


![](TabbedWindow_images/TabbedWindow_img4.jpeg)


* Setting DockTabAlignment as `Top`


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Top">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="Content1"/> 

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();
			
//Set the tabs of the docked window at different sides

dock.DockTabAlignment = Dock.Top;
						
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

content1.Name = "Content1";

content2.Name = "Content2";

//Set Header

DockingManager.SetHeader(content1, "Item1");

DockingManager.SetHeader(content2, "Item2");

//Tabbed Window

DockingManager.SetSideInDockedMode(content2, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content2, "Content1");

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

//Adding control to the window

Content = dock;

{% endhighlight %}


{% endtabs %}

![](TabbedWindow_images/TabbedWindow_img5.jpeg)


## Closing a Tabbed window

Tabbed window provides two different closing behaviors. They are CloseActive and CloseAll modes of `CloseTabs` property.

`CloseActive` – Used to close the active element of Tabbed window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseActive">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" />  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="Content3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//To close the active element of Tabbed window.

dock.CloseTabs = CloseTabsMode.CloseActive;
						
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

ContentControl content3 = new ContentControl();

content1.Name = "Content1";

content2.Name = "Content2";

content3.Name = "Content3";

//Set Header

DockingManager.SetHeader(content1, "Item1");

DockingManager.SetHeader(content2, "Item2");

DockingManager.SetHeader(content3, "Item3");

//Tabbed Window

DockingManager.SetSideInDockedMode(content2, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content2, "Content1");

DockingManager.SetSideInDockedMode(content3, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content3, "Content1");

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

dock.Children.Add(content3);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}

 `CloseAll` – Used to close all the Tabbed window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseAll">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="Content3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Creating instance of DockingManager
			
DockingManager dock = new DockingManager();

//To close all the Tabbed window.

dock.CloseTabs = CloseTabsMode.CloseAll;
						
//Create the instance of ContentControl

ContentControl content1 = new ContentControl();

ContentControl content2 = new ContentControl();

ContentControl content3 = new ContentControl();

content1.Name = "Content1";

content2.Name = "Content2";

content3.Name = "Content3";

//Set Header

DockingManager.SetHeader(content1, "Item1");

DockingManager.SetHeader(content2, "Item2");

DockingManager.SetHeader(content3, "Item3");

//Tabbed Window

DockingManager.SetSideInDockedMode(content2, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content2, "Content1");

DockingManager.SetSideInDockedMode(content3, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(content3, "Content1");

//Add content controls to child of DockingManager

dock.Children.Add(content1);

dock.Children.Add(content2);

dock.Children.Add(content3);

//Adding control to the window

Content = dock;

{% endhighlight %}

{% endtabs %}
