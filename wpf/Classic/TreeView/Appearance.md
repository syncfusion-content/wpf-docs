---
layout: post
title: WPF TreeView Appearance | Syncfusion
description: This section describes how to customize the appearance of Syncfusion WPF TreeView(TreeViewAdv) in various scenarios.
platform: wpf
control: TreeViewAdv
documentation: ug
---
# Appearance in WPF TreeView (TreeViewAdv)

This section deals with the appearance of TreeViewAdv control and contains the following topics:

## Customizing the appearance of the TreeViewAdv

The TreeViewAdv appearance is customized by using the appearance properties available in the control. You can set the color for the Foreground, Background, Selected Item Foreground, Selected Item Background, MouseOver Foreground and MouseOver Background of TreeViewAdv control.

* **SelectedBackground:** Gets or sets the background color of the selected treeview item
* **SelectedForeground:** Gets or sets the foreground color of the selected treeview item
* **MouseOverForeground:** Gets or sets the foreground color of the treeview item over which the mouse pointer moves
* **MouseOverBackground:** Gets or sets the background color of the treeview item over which the mouse pointer moves
* **SelectionUnfocussedBackground:** Gets or sets the background color of the selected treeview item when the item loses focus

The following code example illustrates the above property settings.

{% tabs %} 
{% highlight XAML %}
<!-- Adding TreeViewAdv With Brushes -->
<syncfusion:TreeViewAdv MouseOverBackground="Aqua" MouseOverForeground="Magenta" Name="treeViewAdv" SelectedBackground="Orange" SelectedForeground="Red" SelectionUnfocussedBackcolor="Gold">
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information"/>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

// Set MouseOverBackground property
treeViewAdv.MouseOverBackground = Brushes.Aqua;

// Set MouseOverForeground property
treeViewAdv.MouseOverForeground = Brushes.Magenta;

// Set SelectedBackground property
treeViewAdv.SelectedBackground = Brushes.Orange;

// Set SelectedForeground property
treeViewAdv.SelectedForeground = Brushes.Red;

// Set SelectionUnfocussedBackcolor property
treeViewAdv.SelectionUnfocussedBackcolor = Brushes.Gold;

{% endhighlight %}

{% highlight VB %}

' Set MouseOverBackground property
treeViewAdv.MouseOverBackground = Brushes.Aqua

' Set MouseOverForeground property
treeViewAdv.MouseOverForeground = Brushes.Magenta

' Set SelectedBackground property
treeViewAdv.SelectedBackground = Brushes.Orange

' Set SelectedForeground property
treeViewAdv.SelectedForeground = Brushes.Red

' Set SelectionUnfocussedBackcolor property
treeViewAdv.SelectionUnfocussedBackcolor = Brushes.Gold

{% endhighlight %}

{% endtabs %}  

![Applied back and fore color on selected item in WPF TreeView](Appearance_images/Appearance_img1.jpeg)


## Theme

TreeViewAdv supports various built-in themes. Refer to the below links to apply themes for the TreeViewAdv,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

   ![Setting theme to WPF TreeViewAdv](Getting_Started_images/Theme.png)
  
## Customizing root lines

You can customize the Root lines color and pen of the TreeViewAdv.

### Line color

The color of the root lines, which connect different nodes in a TreeViewAdv control is changed by using the LineBrush property. Use the following code example to set the color of the root lines.

{% tabs %}

{% highlight XAML %}

<!-- Adding TreeViewAdv With show root lines and line brush -->
<syncfusion:TreeViewAdv Name="treeViewAdv" LineBrush="Red" ShowRootLines="True">
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information"/>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight C# %}

// Show root lines
treeViewAdv.ShowRootLines = true;

// Set line brush
treeViewAdv.LineBrush = Brushes.Red;

{% endhighlight %}

{% highlight VB %}

' Show root lines
treeViewAdv.ShowRootLines = True

' Set line brush
treeViewAdv.LineBrush = Brushes.Red

{% endhighlight %}

{% endtabs %}  

![Applied color to root line and line brush in WPF TreeView](Appearance_images/Appearance_img16.jpeg)


### Line pen

The root lines which connect different nodes in a TreeViewAdv control are customized by using the LinePen property. This property specifies the pen color for a node line. To set the LinePen property, refer the below code

{% tabs %}

{% highlight XAML %}

<!-- Adding TreeViewAdv With show root lines and line pen -->
<syncfusion:TreeViewAdv Name="treeViewAdv" ShowRootLines="True">
<syncfusion:TreeViewAdv.LinePen>
<Pen Brush="Red" Thickness="1"/>
</syncfusion:TreeViewAdv.LinePen>
<!-- Adding TreeViewItemAdv -->
<syncfusion:TreeViewItemAdv Header="Marital Status">
<syncfusion:TreeViewItemAdv Header="Single"/>
<syncfusion:TreeViewItemAdv Header="Married"/>
<syncfusion:TreeViewItemAdv Header="Married with Children"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Baby Vaccines">
<syncfusion:TreeViewItemAdv Header="Hepatitis B"/>
<syncfusion:TreeViewItemAdv Header="Tetanus"/>
<syncfusion:TreeViewItemAdv Header="Polio"/>
<syncfusion:TreeViewItemAdv Header="Measles"/>
</syncfusion:TreeViewItemAdv>
<syncfusion:TreeViewItemAdv Header="Country Information"/>
</syncfusion:TreeViewAdv>

{% endhighlight %}

{% highlight c# %}

// Show root lines
treeViewAdv.ShowRootLines = true;

// Set line Pen
treeViewAdv.LinePen = new Pen(Brushes.Red, 1);

{% endhighlight %}

{% highlight VB %}

' Show root lines
treeViewAdv.ShowRootLines = True

' Set line Pen
treeViewAdv.LinePen = New Pen(Brushes.Red, 1)

{% endhighlight %}

{% endtabs %}  
![Applied color to root line and line pen in WPF TreeView](Appearance_images/Appearance_img17.jpeg)
