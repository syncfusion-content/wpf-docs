---
layout: post
title: Getting Started | SplitButton | wpf | Syncfusion
description: getting started
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Getting Started

This section guides you on getting started with the SplitButtonAdv control. It describes you about the control structure, basic settings, implementation and members.

## Control structure

![](Getting-Started_images/Getting-Started_img1.png)

## Adding SplitButtonAdv control to an application

The SplitButtonAdv control is available in the following assembly:

*  Syncfusion.Shared.WPF

### Setting label


The following code explains how to declare a SplitButtonAdv control using XAML:

{% tabs %}
{% highlight xaml %}

<sync:SplitButtonAdv Label="Hello World"/>

{% endhighlight %}
{% endtabs %}

The SplitButtonAdv control can be created through C# as follows:

{% tabs %}
{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img2.png)



### Setting size mode

The size mode of the SplitButtonAdv control can be easily changed using the property SizeMode. The SizeMode comprises the following values:

* Small
* Normal
* Large



#### Small mode

When the SizeMode is set to Small, the icon of the DropDownButtonAdv control is displayed without the label.

Use the following code snippet to set the SizeMode to Small:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Small" Label="Hello World"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";
button.SizeMode = SizeMode.Small;

{% endhighlight %}

{% endtabs %}


![](Getting-Started_images/Getting-Started_img3.png)



#### Normal mode

The DropDownButtonAdv control retains the default appearance, when the SizeMode is set to Normal, 

Use the following code snippet to set the SizeMode to Normal:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Normal" Label="Hello World"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";
button.SizeMode = SizeMode.Normal;

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img4.png)



#### Large mode

When the SizeMode is set to Large, the DropDownButtonAdv control is displayed with large icon and provides multiline support.

Use the following code snippet to set the SizeMode to Large:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Large" Label="Hello World"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";
button.SizeMode = SizeMode.Large;

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img5.png)



### Setting image

The Image displayed in the control can be set using two properties:

* SmallIcon – To set image when SizeMode is Normal or Small.
* LargeIcon – To set image when SizeMode is Large.



The SmallIcon property can be set as follows:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Small" Label="Hello World" SmallIcon="employee.png"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";
button.SizeMode = SizeMode.Small;
button.SmallIcon = new BitmapImage(new Uri("employee.png"));

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img6.png)



The SmallIcon property can be set even when the SizeMode is Normal:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Normal" SmallIcon="employee.png" Label="Hello World"/>

{% endhighlight  %}


{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv()
button.Label = "Hello World";
button.SizeMode = SizeMode.Normal;
button.SmallIcon = new BitmapImage(new Uri("employee.png"));

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img7.png)


The LargeIcon property can be set as follows:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Large" LargeIcon="employee.png" Label="Hello World"/>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Hello World";
button.SizeMode = SizeMode.Large;
button.LargeIcon = new BitmapImage(new Uri("employee.png"));

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img8.png)



### Adding items to SplitButtonAdv

The DropDownMenuGroup acts as a container for SplitButtonAdv, which provides customization such as Resizing, Header and Scrollbar support.

#### Adding DropDownMenuItems to DropDownButtonAdv:


{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="employee.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}

{% highlight C# %}

SplitButtonAdv button = new SplitButtonAdv();
DropDownMenuGroup menu = new DropDownMenuGroup();
DropDownMenuItem menuItem1 = new DropDownMenuItem();
DropDownMenuItem menuItem2 = new DropDownMenuItem();
DropDownMenuItem menuItem3 = new DropDownMenuItem();
menu.Items.Add(menuItem1);
menu.Items.Add(menuItem2);
menu.Items.Add(menuItem3);
button.Content = menuItem1;

{% endhighlight %}


{% endtabs %}
![](Getting-Started_images/Getting-Started_img9.png)



## SplitButtonAdv members

### Properties



Property Table

<table>
<tr>
<th>
Name</th><th>
Type</th><th>
Value it accepts</th><th>
Description</th><th>
Default Value</th><th>
Reference Link</th></tr>
<tr>
<td>
Label</td><td>
String</td><td>
String</td><td>
The Label Property of this element can be set to any string value</td><td>
Null</td><td>
Label</td></tr>
<tr>
<td>
SizeMode</td><td>
SizeMode</td><td>
Normal,Small,        Large</td><td>
Represents the Size of the element, which may be Normal, Small or Large</td><td>
Normal</td><td>
SizeMode</td></tr>
<tr>
<td>
SmallIcon</td><td>
ImageSource</td><td>
Image URL</td><td>
Represents the Image displayed in the element, when size form is Small or Normal</td><td>
-</td><td>
SmallIcon</td></tr>
<tr>
<td>
LargeIcon</td><td>
ImageSource</td><td>
Image URL</td><td>
Represents the Image displayed in the element, when size form is Large</td><td>
-</td><td>
LargeIcon</td></tr>
<tr>
<td>
IsMultiline</td><td>
Boolean</td><td>
True or False</td><td>
Value which represents whether the Label displayed in two line or not.</td><td>
True</td><td>
IsMultiline</td></tr>
</table>


### Events



Events Table

<table>
<tr>
<th>
Name</th><th>
Event Type</th><th>
Event Args Parameter</th><th>
Description</th><th>
Reference Link</th></tr>
<tr>
<td>
DropDownOpened</td><td>
RoutedEventHandler</td><td>
RoutedEvent Args</td><td>
Occurs after DropDown is opened .</td><td>
DropDownOpened</td></tr>
<tr>
<td>
DropDownOpening</td><td>
CancelEventHandler</td><td>
CancelEventArgs</td><td>
Occurs before DropDown is opened.</td><td>
DropDownOpening</td></tr>
<tr>
<td>
DropDownClosed</td><td>
RoutedEventHandler</td><td>
RoutedEvent Args</td><td>
Occurs after DropDown is closed.</td><td>
DropDownClosed</td></tr>
<tr>
<td>
DropDownClosing</td><td>
CancelEventHandler</td><td>
CancelEventArgs</td><td>
Occurs before DropDown is closed.</td><td>
DropDownClosing</td></tr>
<tr>
<td>
Click</td><td>
RoutedEventHandler</td><td>
RoutedEventArgs</td><td>
Occurs when the element is pressed.</td><td>
Click</td></tr>
</table>


