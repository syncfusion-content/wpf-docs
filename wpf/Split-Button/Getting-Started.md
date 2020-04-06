---
layout: post
title: Getting Started | Split Button | WPF | Syncfusion
description: Learn here about how to add WPF Split Button control to an application and its basic functionality.
platform: wpf
control: SplitButtonAdv
documentation: ug
---

# Getting Started

This section provides an overview of how to work with Split Button control. It describes the control structure, the control initialization and the image setting for the control and add items to the control.

## Control structure

![Control-Structre](Getting-Started_images/Getting-Started_img1.png)

Control Structure
{:.caption}

## Assembly deployment

Refer [SplitButtonAdv](https://help.syncfusion.com/wpf/control-dependencies#splitbutton) control dependencies section to get the list of assemblies or [NuGet package](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) needs to be added as reference to use the SplitButtonAdv control in any application.

## Creating simple application with SplitButton

In this walk through, you will create WPF application that contains Split Button control. By the following ways, one can add the controls:

1. [Adding control via designer](#Adding-control-via-designer)

2. [Adding control manually in XAML](#Adding-control-manually-in-XAML)

3. [Adding control manually in C#](#Adding-control-manually-in-C#)

### Adding control via designer

Split Button control can be added to the application by dragging **SplitButtonAdv** from toolbox and dropping it in designer view. After dropping the controls in designer view, the assemblies such as **Syncfusion.Shared.WPF** gets added into the project automatically. The following code snippets will be added into the XAML.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv x:Name="splitButtonAdv" Label="Split Button"/>

{% endhighlight %}
{% endtabs %}

![Getting Started](Getting-Started_images/Getting-Started_img2.png)

N> **syncfusion** in XAML is an auto generated namespace.

### Adding control manually in XAML

In order to add the control manually in XAML, follow the below steps.

1. Add the below required assembly reference to the project.

    * Syncfusion.Shared.WPF

2. Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in XAML page.

3. Declare SplitButtonAdv control in XAML page.

{% tabs %}
{% highlight xaml %}

  <Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
         xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
         xmlns:local="clr-namespace:SplitButtonadv_GetStart_Sample"
         xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
         xmlns:Syncfusion="http://schemas.microsoft.com/netfx/2009/xaml/presentation"
         mc:Ignorable="d"
         Title="MainWindow" Height="450" Width="800">
    <Grid>
        <syncfusion:SplitButtonAdv Height="44"  VerticalAlignment="Center" HorizontalAlignment="Center" Width="162"/>
    </Grid>
</Window>
{% endhighlight %}
{% endtabs %}

### Adding control manually in c#

In order to add control manually in c#, do the below steps.

1. Add the below required assembly references to the project.

    * Syncfusion.Shared.WPF

2. Import the **Syncfusion.Windows.Tools.Controls** namespace.

3. Create ButtonAdv control instance and add it to the window.


{% tabs %}
{% highlight xaml %}
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
         xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
         xmlns:local="clr-namespace:SplitButtonadv_GetStart_Sample"
         xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
         xmlns:Syncfusion="http://schemas.microsoft.com/netfx/2009/xaml/presentation"
         mc:Ignorable="d"
         Title="MainWindow" Height="450" Width="800">
        <Grid Root>
        </Grid>
</Window>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.Windows.Tools.Controls;
namespace ButtonSample
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SplitButtonAdv splitButtonAdv = new SplitButtonAdv();
            splitButtonAdv.Height=44;
            splitButtonAdv.Width=31;
            Root.Childran.Add(splitButtonAdv);
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Setting label

The label on the button is a text that explains its action to the end-user. Apply the text by using the [Label](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~Label.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv Label="Split Button"/>

{% endhighlight %}

{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Split Button";

{% endhighlight %}
{% endtabs %}

![Label](Getting-Started_images/Getting-Started_img4.png)

## Setting size mode

Size mode is used to render Split Button control in different pre-defined sizes based on application demand. Apply the size mode by setting the [SizeMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~SizeMode.html) property.

The **SizeMode** is an enumeration which contains the following values:

* Small
* Normal
* Large

### Small mode

When the mode is set to **Small**, the control is displayed without the label. Only icon will be present in it.

{% tabs %}

{% highlight xaml %}

<syncfusion:SplitButtonAdv SizeMode="Small" Label="Split Button"/>

{% endhighlight %}

{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Split Button";
button.SizeMode = SizeMode.Small;

{% endhighlight %}
{% endtabs %}


![Size-Mode-Small](Getting-Started_images/Getting-Started_img3.png)

### Normal mode

In a normal size button, a small image with the text on the side will be displayed.

{% tabs %}

{% highlight xaml %}

<syncfusion:SplitButtonAdv SizeMode="Normal" Label="Split Button"/>

{% endhighlight %}

{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Split Button";
button.SizeMode = SizeMode.Normal;

{% endhighlight %}
{% endtabs %}

### Large mode

In a large size button, a large image along with the text at the bottom will be displayed.

{% tabs %}

{% highlight xaml %}

<syncfusion:SplitButtonAdv SizeMode="Large" Label="Split Button Large"/>

{% endhighlight %}
{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Split Button Large";
button.SizeMode = SizeMode.Large;

{% endhighlight %}

{% endtabs %}

![Size-Mode-Large](Getting-Started_images/Getting-Started_img5.png)

## Setting image

The image option helps to provide picotrial representation of the button. Image can be added either using the [SmallIcon](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~SmallIcon.html) or [LargeIcon](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~LargeIcon.html) property.

**SmallIcon** — This property will be used to set the image when size mode is **Normal** or **Small**.
**LargeIcon** — This property will be used to set the image when size mode is **Large**.

### Setting small icon

The **SmallIcon** property can be set as follows:

{% tabs %}

{% highlight xaml %}

<syncfusion:SplitButtonAdv SizeMode="Small" Label="Syncfusion" SmallIcon="syncfusion logo.png"/>

{% endhighlight %}

{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Syncfusion";
button.SizeMode = SizeMode.Small;
button.SmallIcon = new BitmapImage(new Uri("syncfusion logo.png"));

{% endhighlight %}

{% endtabs %}

![Small Image](Getting-Started_images/Getting-Started_img6.png)

The **SmallIcon** property can be set even when the sizeMode is **Normal**:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Normal" SmallIcon="Syncfusion  logo.png" Label="Syncfusion"/>

{% endhighlight %}


{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Syncfusion";
button.SizeMode = SizeMode.Normal;
button.SmallIcon = new BitmapImage(new Uri("syncfusion logo.png"));

{% endhighlight %}

{% endtabs %}

![Small Image](Getting-Started_images/Getting-Started_img7.png)

### Setting large icon

The **LargeIcon** property can be set as follows:

{% tabs %}

{% highlight xaml %}

<sync:SplitButtonAdv SizeMode="Large" LargeIcon="Syncfusion logo.png" Label="Syncfusion"/>

{% endhighlight %}

{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Syncfusion";
button.SizeMode = SizeMode.Large;
button.LargeIcon = new BitmapImage(new Uri("syncfusion logo.png"));

{% endhighlight %}

{% endtabs %}

![Large Image](Getting-Started_images/Getting-Started_img8.png)

## Setting icon width and height

Icon width and icon height can be set using [IconWidth](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~IconWidth.html) and [IconHeight] (https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Tools.Controls.DropDownButtonAdv~IconHeight.html) properties respectively.

{% tabs %}
{% highlight xaml %}

<syncfusion:SplitButtonAdv SizeMode="Normal" IconHeight="20" IconWidth="20"  Label="Syncfusion"  SmallIcon ="Syncfusion logo.png"  />

{% endhighlight %}
{% highlight c# %}

SplitButtonAdv button = new SplitButtonAdv();
button.Label = "Syncfusion";
button.IconWidth=20;
button.IconHeight=20;

{% endhighlight %}
{% endtabs %}

![Icon Size Image](Getting-Started_images/Getting-Started_img10.png)

![Icon Size](Getting-Started_images/Getting-Started_img9.png)

## Adding items to SplitButtonAdv

The DropDownMenuGroup acts as a container for the DropDownButtonAdv control. It provides options to add menu items and also options like header name, resizing and scrollbar.

{% tabs %}

{% highlight xaml %}

<shared:SplitButtonAdv Label="Hello World" x:Name="button" SizeMode="Normal" SmallIcon="Letter.png">
<shared:DropDownMenuGroup>
<shared:DropDownMenuItem Header="Menu Item 1"/>
<shared:DropDownMenuItem Header="Menu Item 2"/>
<shared:DropDownMenuItem Header="Menu Item 3"/>
</shared:DropDownMenuGroup>
</shared:SplitButtonAdv>

{% endhighlight %}

{% highlight c# %}

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

![Drop-Down-item](Getting-Started_images/Getting-Started_img11.png)